# Stack and Queue

<br/>

## Stack

스택(Stack)은 다음과 같은 성질을 갖는 자료형이다.

- LIFO (Last In First Out) : 나중에 집어넣은 데이터가 먼저 나온다.
- 브라우저의 뒤로 가기, 앞으로 가기를 예로 생각할 수 있다.

```js
class Stack {
  constructor() {
    this.storage = {};
    this.top = 0;
  }
  // stack의 size
  size() {
    return this.top;
  }
  // stack의 마지막에 element 추가, top 증가
  push(element) {
    this.storage[this.top] = element;
    this.top += 1;
  }
  // stack에서 맨 마지막 element(가장 최신의 입력) 삭제, top도 감소
  pop() {
    if (this.size() <= 0) {
      return;
    }
    const result = this.storage[this.top - 1];
    delete this.storage[this.top - 1];
    this.top -= 1;
    return result;
  }
}
```

codestates에서는 이해를 돕기 위해 위와 같은 코드로 배웠으나 아래와 같이 간략화할 수 있다.<br />
위의 코드는 객체를 이용해서 구현했고 아래의 코드는 배열을 통해 구현했다.

```js
class Stack {
  constructor() {
    this._arr = [];
  }
  // 데이터 입력
  push(item) {
    this._arr.push(item);
  }
  // 데이터 추출
  pop() {
    return this._arr.pop();
  }
  // 최신 데이터 확인
  peek() {
    return this._arr[this._arr.length - 1];
  }
}
```

<br />

## Queue

큐(Queue)는 다음과 같은 성질을 갖는 자료형이다.

- FIFO (First In First Out) : 먼저 집어넣은 데이터가 먼저 나온다.
- 먼저 출력 버튼을 누른 문서부터 출력되는 프린터를 예로 생각할 수 있다.
- 컴퓨터 장치들 사이에서 데이터를 주고 받을 때, 각 장치 사이에 존재하는 속도의 차이나 시간 차이를 극복하기 위해 임시 기억 장치의 자료구조로 Queue를 사용하며 이것을 통틀어 버퍼(Buffer)라고 한다.
  <br />

```js
class Queue {
  constructor() {
    this.storage = {};
    this.front = 0;
    this.rear = 0;
  }
  // queue의 size
  size() {
    return this.rear - this.front;
  }
  // queue의 마지막에 element 추가, 마지막의 index인 rear 증가
  enqueue(element) {
    this.storage[this.rear] = element;
    this.rear += 1;
  }
  // queue의 맨 앞의 요소 제거, 맨 앞의 index인 front 증가
  dequeue() {
    if (this.size() === 0) {
      return;
    }
    const result = this.storage[this.front];
    delete this.storage[this.front];
    this.front += 1;
    return result;
  }
}
```

위의 코드에서 객체로 구현하였고 아래의 코드에서 배열을 통해 구현한다.

```js
class Queue {
  constructor() {
    this._arr = [];
  }
  // 데이터 추가
  enqueue(item) {
    this._arr.push(item);
  }
  // 데이터 삭제
  dequeue() {
    return this._arr.shift();
  }
}
```
