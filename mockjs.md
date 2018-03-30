####1、安装
```js
    npm i mockjs --save-dev
```
####2、编辑mock.js
```js   
 import Mock from 'mockjs'
    //Random：存储各种随机函数的对象
    let Random = Mock.Random 

    const data =  () => {
      let arr = []
      for (let i = 0; i < 10; i++) {
        let newArticleObject = {
          title: Random.csentence(5),
          content: Random.cparagraph(5, 7),
          time: Random.date() + ' ' + Random.time(),
          location: Random.city()
        }
        arr.push(newArticleObject)
      }
      return {arr}
    }
    // 第三个参数可以是对象也可以是返回对象的函数
    Mock.mock('/api/data', 'get', data)
```
####3、在main.js中引入
```js
import './mock'
```
####4、在*.vue中使用
```js
methods:{
      click:function(){
        this.$axios({
          url: '/api/data',
          method: 'get',
        }).then((res)=>{
          console.log(res.data)
        })
      }
    }
```
