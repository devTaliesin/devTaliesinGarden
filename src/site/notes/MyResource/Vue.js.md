---
{"tags":null,"dg-publish":true,"permalink":"/my-resource/vue-js/","dgPassFrontmatter":true,"created":"2023-12-13T17:50:08.607+09:00","updated":"2023-12-15T13:18:22.083+09:00"}
---

# Dependency
## [[MyResource/Node.js\|Node.js]] latest version

# How To Install Vue
## npm init vue@latest
### Project name: ... {projectName}
 - 프로젝트 이름 설정
### Package name: ... {projectName}
 - 프로젝트 패키지 이름 설정
### Add TypeScript? ... No / Yes
 - TypeScript 사용:  정적 타입 검사를 통한 코드 안정성 향상
### Add JSX Support? ... No / Yes
 - JSX 지원: Vue 컴포넌트 내에서 JavaScript와 HTML을 함께 사용
### Add Vue Router for Single Page Application development? ... No / Yes
 - Vue Router 추가: 라우팅 및 페이지 네비게이션 관리 도구
### Add Pinia for state management? ... No / Yes
 - Pinia를 추가: Vue의 State 관리 라이브러리
### Add Vitest for Unit Testing? ... No / Yes
 -  Vitest 추가: Vue 컴포넌트 등을 위한 단위 테스트 도구
### Add an End-to-End Testing Solution? » No / Yes
 - End-to-End 테스트 솔루션 추가: 프론트엔드에서부터 백엔드까지의 통합된 시스템을 테스트할 수 있는 기능을 제공
### Add ESLint for code quality? ... No / Yes
 - ESLint 추가: 코드 스타일 및 오류를 체크하는 도구
### Add Prettier for code formatting? ... No / Yes
 - Prettier 추가: 코드를 자동으로 정리해주는 포맷터
# Extensions
## HTML CSS Support
## Vue 3 Snippets
# How To Use Vue
## cd {projectName}
 - 생성된 프로젝트 폴더 진
## npm install
 - 프로젝트의 종속 항목인 패키지들을 설치
## npm run format
 - Prettier나 다른 코드 포맷터를 사용하여 코드를 일관된 형식으로 정리
## npm run dev
 -  개발 서버를 시작
# Grammar
## Script
## Template
## Style
# Assets
# Components
# Router
# Stores
## What is Pinia
 - Vue3에서 필요한 최신 State 관리 라이브러리
## Pinia Cheat Sheet
### Initialize Pinia for your app
```js  
/*
src/main.js
*/

import { createPinia } from 'pinia' createApp(App).use(createPinia()).mount('#app')
```
### Define the store
``` js
/*
src/stores/ProductStore.js
*/
import { defineStore } from 'pinia' 
										/*a unique name*/
export const useProductStore = defineStore('product', {
	state: () => ({
					/*state 초기화*/
		products: [ /*Product, Product, Product*/] 
	}), 
	getters: {  /*parameter를 통해 state 접근*/
		productCount(state) { 
			return state.products.length 
		}, 
		productsCheaperThan(state) { 
			return (price) => ( /*인수를 받을 수 있지만 대신 함수를 반환*/
				state.products.filter(product => 
					product.price < price 
				) 
			) 
			} 
	}, 
	actions: { /*actions을 사용해 state 변경*/
		addProduct(/*Product*/) { 
			<access the state with this>
			this.products.push(Product) 
		} 
	} 
})t
```
### Use the Store (Composition API)
```vue
/*
src/App.vue
*/
<script setup>
import { useProductStore } from './stores/ProductStore'

const store = useProductStore() /*store instance 생성*/
</script>

<template>
	<ul>
		<li v-for="product in store.products"> /*store 경로 접근*/
		...
		</li>
	</ul>
	<p>{{ store.productCount }}</p>
	<ul>
		<li v-for="product in store.productsCheaperThan(10)">
		...
		</li>
	</ul>
	 <button @click="store.addProduct(Product))">Add
	...
```
# Views

# Structure of Vue.js
``` 
VueProject 
├── node_modules
│   ├──  ...
├── public
│   ├──	favicon.ico
├── src
│   ├── assets
│   │	├── base.css
│   │	├── logo.svg
│   │	└── main.css
│   ├── components
│   │	└── ...
│   ├── router
│   │	└── index.js
│   ├── stores
│   │	└── counter.js
│   ├── views
│   │	└── ...
│   ├── App.vue
│   └── main.js
├── .gitignore
├── .prettierrc.json
├── index.html
├── jsconfig.json
├── package-lock.json
├── package.json
├── README.md
└── vite.config.js
```






