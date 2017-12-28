---
title: placeholder兼容
date: 2017-12-25 17:25:20
tags: [浏览器兼容,placeholder]
---

## placeholder兼容

> ie9下,input中placeholder不起作用,原生js不用任何第三方库,代码如下:

```javascript
export default function () {
    if (!('placeholder' in document.createElement('input'))) {
        // 将返回的nodeList对象转为数组
        var nodes = Array.prototype.slice.call(document.querySelectorAll('[placeholder]'))
        nodes.forEach(function (item, index) {
            if (item.getAttribute("fixplaceholder") != "true") {
                item.setAttribute("fixplaceholder", "true")
                item.addEventListener('focus', function () {
                    this.nextSibling.style.display = 'none'
                })
                item.addEventListener('blur', function () {
                    if (!this.value) {
                        this.style.display = 'none'
                        this.nextSibling.style.display = 'inline'
                    }
                })
                var cloneNode = item.cloneNode()
                // 如果[type='password']类型，则转为text
                if (cloneNode.getAttribute('type').toLowerCase() === 'password') {
                    cloneNode.setAttribute('type', 'text')
                }
                cloneNode.setAttribute('value', cloneNode.getAttribute('placeholder'))
                cloneNode.style.display = 'none'
                item.insertAdjacentHTML('afterend', cloneNode.outerHTML)
                item.nextSibling.addEventListener('focus', function () {
                    this.style.display = 'none'
                    this.previousSibling.style.display = 'inline'
                    this.previousSibling.focus()
                })
                if (!item.value) {
                    item.style.display = 'none'
                    item.nextSibling.style.display = 'inline'
                }
            }
        })
    }
}
```

