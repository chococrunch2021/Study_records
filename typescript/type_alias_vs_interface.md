### Type alias와 Interface 공통점 

- type alias 보다 더 많은 것을 할 수 있어 interface가 권장된다.
- 현재 interface와 type 둘 다 extends와 implements 구문을 사용할 수 있지만 
`객체 타입` 이나 `객체 타입 간 곱 타입`, 즉 정적으로 모양을 알 수 있는 객체 타입에만 동작한다.

### Type alias와 Interface 차이점

- interface는 선언 병합이 가능하지만 type alias는 그렇지 않다.
- 선언 병합(Declaration merging)은 동일한 이름으로 여러 번 선언해도 컴파일 시점에  합칠 수 있다.


```
    interface Window {
        title: string;
    }

    interface Window {
        ts: import("typescript");
    }

    declare function getWindow(): Window;

    const window = getWindow();
    const src = 'const a = "Hello World"';
    window.ts.transpileModule(src, {});    // transpileModule() 메서드 사용 가능
```

### Typescript 팀의 의도 
- 개방-폐쇄 원칙에 따라 확장에 열려있는 javascript 객체의 동작 방식과 비슷하게 연결하도록 Interface를 설계하였다.

- 가능한 interface를 사용하도록 권장하고 합 타입이나 튜플 타입을 반드시 써야되는 상황에 Type alias를 사용하도록 권장하고 있다.

+ 외부에 공개할 API는 Interface 사용 권장 (선언 병합을 위해서)

### 출처

- [https://medium.com/humanscape-tech/type-vs-interface-%EC%96%B8%EC%A0%9C-%EC%96%B4%EB%96%BB%EA%B2%8C-f36499b0de50](https://medium.com/humanscape-tech/type-vs-interface-%EC%96%B8%EC%A0%9C-%EC%96%B4%EB%96%BB%EA%B2%8C-f36499b0de50)