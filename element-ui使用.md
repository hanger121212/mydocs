---
title: element-ui使用
date: 2017-12-28 17:20:21
tags: [element-ui,采坑]
---

## element-ui使用
#### 表单验证

> 自定义validator时注意返回必须调用callback(),
> 否则在form验证:this.$refs[ruleForm2].validate()会出错,例:

```javascript
//检验手机号规则
function validator_phone(rule, value, callback) {
  if (value.length != 11 || !/^((13|14|15|17|18)[0-9]{1}\d{8})$/.test(value)) {
  	callback(new Error('请输入正确的手机账户'));
  }else{
  	callback();//
  }
}
```

