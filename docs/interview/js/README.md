
## let 和 var 的区别

| 性质 | let | var |
| ----------- | ----------- |-----|
| 声明提升 | 是 | 否 |
| 局部(块级)作用域 | 是 | 否 |
| 重复声明 | 否 | 是 |

## 生拷贝 和 浅拷贝 的区别
- **基本数据类型赋值为深拷贝，引用数据类型赋值为浅拷贝**

- **引用数据类型拷贝，只拷贝一层为浅拷贝，拷贝所有为深拷贝**

| 方法 | 拷贝类型 | 局限 |
| ----------- | ----------- |-----|
| ...(解构) | 浅拷贝 |
| JSON.parse(JSON.stringify(obj))| 深拷贝 | 不能拷贝方法 |
| Object.assin({},obj)| 浅拷贝 |  |

- **深拷贝代码**
  
```
function deepClone(obj) {
    if (typeof obj !== 'object') {
      return obj
    }
    const resultObj = Array.isArray(obj) ? [] : {}
    for (const key in obj) {
      if (Object.hasOwnProperty.call(obj, key)) {
        const element = obj[key];
        if (typeof obj !== 'object') {
          resultObj[key] = element
        } else {
          resultObj[key] = deepClone(element)
        }
      }
    }
    return resultObj
}
```
<br>

- **使用lodash**
  
```
  import {deepClone} from 'lodash'
  const copyobj = deepClone(obj)
```