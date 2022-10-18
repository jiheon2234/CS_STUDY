# <span style="font-size:3em;">Promise</span>
2022-09-13 22:46
### TAG  : #js #비동기
---
## Promise란?
	js에서 비동기를 간편하게 처리할 수 있는 Object
---
## 1.Producer
```js
// when new Promise is created, the executor runs automatically
const promise = new Promise((resolve, reject) => {
//doing some heavy work()
console.log("doing something.....");
setTimeout(() => {
resolve("ellie");
// reject(new Error('no network'))
}, 2000);
}); //만드는 순간 executor 실행됨
```
무언가를 하다가,  잘 마무리되면 r**esolve**함수를 호출
실패하면 **reject** 호출
---
## 2. then, catch, finally
```js
promise
.then((value) => {
//정상적으로 수행이 되었을 때
console.log(value);
})
.catch((error) => {
console.log(error);
})
.finally(() => {
console.log("finally");
});
```
- then
>resolve를 통한 콜백함수가 파라미터로 전달됨
- catch
> 에러가 발생할 때 어떻게 처리할지
- finally
>  성공하든 실패하든 무조건 마지막에 호출됨

---
## 3. Promise chaining
```js
const fetchNumber = new Promise((resolve, rejct) => {
setTimeout(() => resolve(1), 1000);
});
fetchNumber
.then((num) => num * 2)
.then((num) => num * 3)
.then((num) => {
return new Promise((resolve, reject) => {
setTimeout(() => resolve(num - 1), 1000);
});
})
.then((num) => console.log(num));
```
**then은 또다른 Promise를 전달해도 됨**

---
## 4.Error Handling
``` js
const getHen = () =>
new Promise((resolve, reject) => {
setTimeout(() => resolve("🕊"), 1000);
});
const getEgg = (hen) =>
new Promise((resolve, reject) => {
setTimeout(() => resolve(`${hen}=>🥚`), 1000);
});
const cook = (egg) =>
new Promise((resolve, reject) => {
setTimeout(() => resolve(`${egg}=>🍳`), 1000);
});

//////////////////////////////////////////////////
getHen()
.then(getEgg)
.catch((error) => {
return "bread";
})
.then(cook)
.then(console.log)
.catch(console.log); 
```
 **콜백함수를 전달할때,  받아오는 값을 다른 함수로 호출하는 경우엔 생략 가능**
 `(meal=>console.log(meal))` === `(console.log)`
 
 
---
참고자료
[유튜브](https://www.youtube.com/watch?v=JB_yU6Oe2eE&t=852s)
 
 