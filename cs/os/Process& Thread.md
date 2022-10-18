# <span style="font-size:3em;">Process&Thread </span>
2022-09-14 14:48
### TAG  : #os
---
## 개념
>관리의 단위 (os의 연산할거리)
>프로세스 하나당 하나의 흐름이 존재한다(쓰레드)
>>이 흐름이 n개가 된다면, n개의 흐름은 동시에, 개별적으로 작동
>>이를***Multi-Threading***이라고 함
>
>프로세스가 여러개면 ***Multitasking***

---

## 컴퓨터의 세계는
	3개의 모드로 이루어져 있음
|모드| |
|:--:|:--:|
|유저모드| 프로세스 연산 =>cpu+ram(virtual) 필요함|
|커널모드| 전산자원을 일정 단위로 잘라서 프로세스에 할당|
|하드웨어모드|cpu, ram 등의 전산자원 
만일 쓰레드가 존재한다면, 할당된 프로세스만 접근 가능


- Process(작업)은 최소 1개의 Thread 존재
- os는 Virtual Mem을 프로세스에게 할당
- **Process**에 속한 모든 쓰레드는 프로세스의 가상 메모리로 공간 제약
	- Multi - threading 이 나오면, 동시성, 동기화 이슈 발생
---
## **비유**
Process : 한 가구 (virtual mem)
Thread : 가구 안의 세대원 (개별 흐름)
집에서 각자의 방을 쓰지만(Thread local storage : 스택구조)
거실, 부엌 등은 공유함 (Heap)


	


## 

