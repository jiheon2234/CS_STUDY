# <span style="font-size:3em;">async & await</span>
2022-09-14 10:49
### TAG  : #js #비동기
[Promise](Promise.md) <-에서 이어지는 내용

---
## async, await이란?
	promise 위에 좀더 간편한 api를 제공

---
## 1. async
promise를 반환함
```js
async function fetchUser(){ //async를 쓰면 자동으로 promise로 바뀜
return 'ellie'
}
const user=fetchUser();
user.then(console.log)
console.log(user)
```
---
## 2.await
delay가 끝날때까지 기다려줌
```js
function delay(ms){
return new Promise(resolve=>setTimeout(resolve,ms))
}
async function getApple(){
await delay(1000)
// throw 'error';
return 'apple'
}
async function getBanana(){
await delay(2000)
return 'banana'
}
async function pickFruits(){
const apple=await getApple()
const banana = await getBanana()
return `${apple}+${banana}`
}
pickFruits().then(console.log)
```
---
## 3. 문제점 해결
위의 코드는, apple을 받아오고, 그다음 바나나를 받아옴
그래서 총 3초가 거림
이를 병렬적으로 받아오려면

```js
function pickAllFruits(){
return Promise.all([getApple(),getBanana()])
.then(frunits=>frunits.join('+'))
}
pickAllFruits().then(console.log)
function pickOnlyOne(){
return Promise.race([getApple(),getBanana()])
}
pickOnlyOne().then(console.log)
```

- Promise.all
	`병렬적으로 한번에 받아옴`
- Promise.race
	`가장 먼져 들어오는 1개만 받아옴`
	
	
---
## 참고
[드림코딩](https://www.youtube.com/watch?v=aoQSOZfz3vQ&t=505s)
