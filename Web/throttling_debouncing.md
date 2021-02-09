- underscore, lodash에서 메소드 제공한다

### 쓰로틀링

> 마지막 함수가 호출되고 일정 시간이 지나기 전에 다시 호출되지 않도록 한다

- ex) 스크롤 이벤트

```

var timer;
document.querySelector('#input').addEventListener('input', function (e) {
  if (!timer) {
    timer = setTimeout(function() {
      timer = null;
      console.log('여기에 ajax 요청', e.target.value);
    }, 200);
  }
});

```

- 만약 ajax 요청이 이뤄지고 있다면 무시하고 없다면 요청을 보낸다

### 디바운싱

> 연이어 호출되는 함수들 중 마지막 함수(혹은 가장 처음)만 호출되도록 하는 것

ex) ajax 검색

- 글자를 칠 때마다 api 요청을 보내는 것은 많은 비용을 발생한다.
- 글자를 다 치거나 일정 이상의 시간 만큼 중 한 번만 요청을 보내고 싶다.
- 200ms 기준이라면 그 동안 새로운 입력이 들어오면 이전 요청을 취소하고 새로운 요청을 다시 보낸다

```
var timer;
document.querySelector('#input').addEventListener('input', function(e) {
  if (timer) {
    clearTimeout(timer);
  }
  timer = setTimeout(function() {
    console.log('여기에 ajax 요청', e.target.value);
  }, 200);
});

```

---

- 출처
  - [https://www.zerocho.com/category/JavaScript/post/59a8e9cb15ac0000182794fa](https://www.zerocho.com/category/JavaScript/post/59a8e9cb15ac0000182794fa)
