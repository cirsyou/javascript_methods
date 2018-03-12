## 常用js方法

* DIR01 倒计时

* 网址校验
```javascript
var reg = /(http|ftp|https):\/\/[\w\-_]+(\.[\w\-_]+)+([\w\-\.,@?^=%&:/~\+#]*[\w\-\@?^=%&/~\+#])?/
if (!reg.test(val)) {
  return false
  }
return true;
```