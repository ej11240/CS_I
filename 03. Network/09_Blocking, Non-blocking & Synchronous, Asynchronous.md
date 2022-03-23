# ****Blocking/Non-blocking & Synchronous/Asynchronous****

[https://camo.githubusercontent.com/b7b28ae739c50d5ed8a4594f52f24e671aeeae234befd0991e5230561ba303bf/68747470733a2f2f696d67312e6461756d63646e2e6e65742f7468756d622f523132383078302f3f73636f64653d6d746973746f72793226666e616d653d6874747073253341253246253246626c6f672e6b616b616f63646e2e6e6574253246646e25324664613530597a2532466274713044736a65345a562532466c47653848386e5a676442646746766f3749637a5330253246696d672e706e67](https://camo.githubusercontent.com/b7b28ae739c50d5ed8a4594f52f24e671aeeae234befd0991e5230561ba303bf/68747470733a2f2f696d67312e6461756d63646e2e6e65742f7468756d622f523132383078302f3f73636f64653d6d746973746f72793226666e616d653d6874747073253341253246253246626c6f672e6b616b616f63646e2e6e6574253246646e25324664613530597a2532466274713044736a65345a562532466c47653848386e5a676442646746766f3749637a5330253246696d672e706e67)

# **Blocking/Non-blocking**

`호출된 함수`가 `호출한 함수`에게 제어권을 건네주는지(바로 리턴하는지)

함수 A, B가 있고, A 안에서 B를 호출했다고 가정 → 호출한 함수 A, 호출된 함수 B. B는 호출되었기에 일을 해야 함. (제어권이 B에게 주어짐)

- **Blocking** : 함수 B는 할 일을 다 마칠 때까지 제어권을 가지고 있음. A는 B가 다 마칠 때까지 기다려야. == 할 일 마치고 제어권 리턴
- **Non-blocking** : 함수 B는 할 일을 마치지 않았어도 A에게 제어권을 바로 넘겨줌(return). A은 B를 기다리면서도 다른 일을 진행 가능 == 일 시작할 때 바로 제어권 리턴

# **Synchronous/Asynchronous**

B의 수행 결과나 종료 상태를 A가 신경쓰고 있는지

- **Synchronous** : 함수 A는 함수 B가 일을 하는 중에 기다리면서, 현재 상태가 어떤지 계속 체크 
== 호출된 함수(B)를 호출한 함수(A)가 신경씀
- **Asynchronous** : 함수 B의 수행 상태를 B 혼자 직접 신경쓰면서 처리. (Callback)
== 호출된 함수(B)를 자기 스스로 신경씀
    
    비동기는 호출시 Callback을 전달하여 작업의 완료 여부를 호출한 함수에게 답함.
    (Callback이 오기 전까지 호출한 함수는 신경쓰지 않고 다른 일을 할 수 있음)
    

## **Case Study : 대표님, 개발자 좀 더 뽑아주세요..**

### **1) Blocking & Synchronous**

- **Blocking** : 함수 B는 할 일을 다 마칠 때까지 제어권을 가지고 있음. A는 B가 다 마칠 때까지 기다려야. == 할 일 마치고 제어권 리턴
- **Synchronous** : 함수 A는 함수 B가 일을 하는 중에 기다리면서, 현재 상태가 어떤지 계속 체크 
== 호출된 함수(B)를 호출한 함수(A)가 신경씀

> 나 : 대표님, 개발자 좀 더 뽑아주세요..
대표님 : 오케이, 잠깐만 거기 계세요!
나 : …?!!
대표님 : (채용 공고 등록.. 지원자 연락.. 면접 진행.. 연봉 협상..)
나 : (과정 지켜봄.. 궁금함.. 어차피 내 일 하러는 못 가고 계속 서 있음)
> 

### **2) Blocking & Asynchronous**

- **Blocking** : 함수 B는 할 일을 다 마칠 때까지 제어권을 가지고 있음. A는 B가 다 마칠 때까지 기다려야. == 할 일 마치고 제어권 리턴
- **Asynchronous** : 함수 B의 수행 상태를 B 혼자 직접 신경쓰면서 처리. (Callback)
== 호출된 함수(B)를 자기 스스로 신경씀

> 나 : 대표님, 개발자 좀 더 뽑아주세요..
대표님 : 오케이, 잠깐만 거기 계세요!
나 : …?!!
대표님 : (채용 공고 등록.. 지원자 연락.. 면접 진행.. 연봉 협상..)
나 : (안 궁금함.. 지나가는 말로 여쭈었는데 붙잡혀버림.. 딴 생각.. 못 가고 계속 서 있음)
> 

### **3) Non-blocking & Synchronous**

- **Non-blocking** : 함수 B는 할 일을 마치지 않았어도 A에게 제어권을 바로 넘겨줌(return). A은 B를 기다리면서도 다른 일을 진행 가능 == 일 시작할 때 바로 제어권 리턴
- **Synchronous** : 함수 A는 함수 B가 일을 하는 중에 기다리면서, 현재 상태가 어떤지 계속 체크 
== 호출된 함수(B)를 호출한 함수(A)가 신경씀

> 나 : 대표님, 개발자 좀 더 뽑아주세요..
대표님 : 알겠습니다. 가서 볼 일 보세요.
나 : 넵!
대표님 : (채용 공고 등록.. 지원자 연락.. 면접 진행.. 연봉 협상..)
나 : 채용하셨나요?
대표님 : 아직요.
나 : 채용하셨나요?
대표님 : 아직요.
나 : 채용하셨나요?
대표님 : 아직요~!!!!!!
> 

### **4) Non-blocking & Asynchronous**

- **Non-blocking** : 함수 B는 할 일을 마치지 않았어도 A에게 제어권을 바로 넘겨줌(return). A은 B를 기다리면서도 다른 일을 진행 가능 == 일 시작할 때 바로 제어권 리턴
- **Asynchronous** : 함수 B의 수행 상태를 B 혼자 직접 신경쓰면서 처리. (Callback)
== 호출된 함수(B)를 자기 스스로 신경씀

> 나 : 대표님, 개발자 좀 더 뽑아주세요..
대표님 : 알겠습니다. 가서 볼 일 보세요.
나 : 넵!
대표님 : (채용 공고 등록.. 지원자 연락.. 면접 진행.. 연봉 협상..)
나 : (열일중..)
대표님 : 한 분 모시기로 했습니다~!
나 : 😍
> 

참고링크

- [https://musma.github.io/2019/04/17/blocking-and-synchronous.html](https://musma.github.io/2019/04/17/blocking-and-synchronous.html)
- [https://github.com/gyoogle/tech-interview-for-developer/blob/master/Computer Science/Network/[Network] Blocking%2CNon-blocking %26 Synchronous%2CAsynchronous.md](https://github.com/gyoogle/tech-interview-for-developer/blob/master/Computer%20Science/Network/%5BNetwork%5D%20Blocking%2CNon-blocking%20%26%20Synchronous%2CAsynchronous.md)