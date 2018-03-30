#### [官网](https://vuex.vuejs.org/zh-cn/installation.html)
### npm
```js
npm i vuex --save
```
### 引入并使用
```js
import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)
```
### 创建实例并在实例中使用
```js
const store = new Vuex.Store({
	state: {
		index: 0
	},
	mutations: {
		add(state){
			state.index ++
		}
})

new Vue({
  el: '#app',
  store,
  router,
  components: { App },
  template: '<App/>'
})
```
### 获取
```js
this.$store.state.index //获取值
this.$store.commit('add') //调用函数