# js 正则验证

## 常用字符

### 验证手机号

```javascript
//以 ^1 开头， 第二位[3,4,5,7,8]， 3~11位任意数字
export function isPhone(phone) {
  const reg = /^[1][3,4,5,7,8][0-9]{9}$/;
  return reg.test(phone);
}
```

### 验证邮箱

```javascript
export function isPhone(phone) {
  const reg =
    /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
  return reg.test(phone);
}
```

### 判断 url 是否是 http 或 https

```javascript
/**
 * 判断url是否是http或https
 * @param {string} path
 * @returns {Boolean}
 */
export function isHttp(url) {
  return url.indexOf("http://") !== -1 || url.indexOf("https://") !== -1;
}
```

### 判断是不是 url

```javascript
/**
 * @param {string} url
 * @returns {Boolean}
 */
export function validURL(url) {
  const reg =
    /^(https?|ftp):\/\/([a-zA-Z0-9.-]+(:[a-zA-Z0-9.&%$-]+)*@)*((25[0-5]|2[0-4][0-9]|1[0-9]{2}|[1-9][0-9]?)(\.(25[0-5]|2[0-4][0-9]|1[0-9]{2}|[1-9]?[0-9])){3}|([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.(com|edu|gov|int|mil|net|org|biz|arpa|info|name|pro|aero|coop|museum|[a-zA-Z]{2}))(:[0-9]+)*(\/($|[a-zA-Z0-9.,?'\\+&%$#=~_-]+))*$/;
  return reg.test(url);
}
```

### 判断是不是全小写

```javascript
/**
 * @param {string} str
 * @returns {Boolean}
 */
export function validLowerCase(str) {
  const reg = /^[a-z]+$/;
  return reg.test(str);
}
```

### 判断是不是全大写

```javascript
/**
 * @param {string} str
 * @returns {Boolean}
 */
export function validUpperCase(str) {
  const reg = /^[A-Z]+$/;
  return reg.test(str);
}
```

### 判断 str 是不是全字母

```javascript
/**
 * @param {string} str
 * @returns {Boolean}
 */
export function validAlphabets(str) {
  const reg = /^[A-Za-z]+$/;
  return reg.test(str);
}
```

### 判断 str 是不是字符串

```javascript
/**
 * @param {string} str
 * @returns {Boolean}
 */
export function isString(str) {
  if (typeof str === "string" || str instanceof String) {
    return true;
  }
  return false;
}
```

### 匹配是否有中文字符

```javascript
export function valid(str) {
  const reg = /[\u4e00-\u9fa5]/gm;
  return reg.test(str);
}
```

### 只能整数

```javascript
export function validNumber(str) {
  const reg = /^\d+$/;
  return reg.test(str);
}
```

### n 个整数

```javascript
export function validNumber(str, n) {
  const reg = `/^\d{${n}}$/`;
  return reg.test(str);
}
```

### 判断身份证号码

```javascript
export function validIDCard(str) {
  const reg =
    /^(^[1-9]\d{7}((0\d)|(1[0-2]))(([0|1|2]\d)|3[0-1])\d{3}$)|(^[1-9]\d{5}[1-9]\d{3}((0\d)|(1[0-2]))(([0|1|2]\d)|3[0-1])((\d{4})|\d{3}[Xx])$)$/;
  return reg.test(str);
}
```

### 验证邮政编码

```javascript
export function validPostcode(str) {
  const reg = /^[1-9]\d{5}(?!\d)$/;
  return reg.test(str);
}
```

### 验证 IP

```javascript
export function validIp(str) {
  const reg =
    /^((?:(?:25[0-5]|2[0-4]\d|[01]?\d?\d)\.){3}(?:25[0-5]|2[0-4]\d|[01]?\d?\d))$/;
  return reg.test(str);
}
```

## 浏览器或者设备验证

### 从 UA 判断是不是移动端

```javascript
export function validMobile(str) {
  const reg =
    /(nokia|iphone|android|ipad|motorola|^mot\-|softbank|foma|docomo|kddi|up\.browser|up\.link|htc|dopod|blazer|netfront|helio|hosin|huawei|novarra|CoolPad|webos|techfaith|palmsource|blackberry|alcatel|amoi|ktouch|nexian|samsung|^sam\-|s[cg]h|^lge|ericsson|philips|sagem|wellcom|bunjalloo|maui|symbian|smartphone|midp|wap|phone|windows ce|iemobile|^spice|^bird|^zte\-|longcos|pantech|gionee|^sie\-|portalmmm|jig\s browser|hiptop|^ucweb|^benq|haier|^lct|opera\s*mobi|opera\*mini|320x320|240x320|176x220)/i;
  return reg.test(str);
}
```

### 从 UA 判断是不是 windows 平台

```javascript
export function validWindows(str) {
  const reg = /windows/i;
  return reg.test(str);
}
```

### 从 UA 判断是不是 Mac Os 平台

```javascript
export function validMacOs(str) {
  const reg = /macintosh/i;
  return reg.test(str);
}
```

### 从 UA 判断是不是 Android 平台

```javascript
export function validAndroid(str) {
  const reg = /android/i;
  return reg.test(str);
}
```

### 从 UA 判断是不是 IPhone 平台

```javascript
export function validIPhone(str) {
  const reg = /iphone/i;
  return reg.test(str);
}
```
