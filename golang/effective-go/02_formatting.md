# Formatting

포맷팅 이슈는 가장 논쟁거리이지만 가장 중요하지 않다. 사람들은 다른 포맷팅 스타일에 적응할 수 있지만 그렇지 않다면 더 좋으며, 모두가 같은 스타일을 고수한다면 이 주제에 할애하는 시간이 줄어들 것이다. 문제는 긴 규범적인 스타일 가이드 없이 어떻게 이 유토피아에 접근할 수 있는가이다.

Go에서 우리는 흔치 않은 접근법을 택하여 대부분의 포맷팅 이슈를 기계가 처리하게 한다.  `gofmt`프로그램(`go fmt`로도 가능, 소스 파일이 아닌 패키지 레벨에서 실행됨)은 Go 프로그램을 읽고 표준 스타일의 들여쓰기와 수직 정렬, 유지 그리고 필요한 경우 주석을 재포맷팅한 소스를 내놓는다. 새 레이아웃 상황을 처리하는 법을 알고 싶다면, `gofmt`를 실행해보라. 답이 올바르지 않다면, 프로그램을 재조정하라.

예를 들어, 구조체의 필드에 주석을 배열하는 데 시간을 소비할 필요가 없다. `Gofmt`가 해줄 것이다. 아래와 같이 선언이 주어진다면,

```go
type T struct {
	name string // name of the object
	value int // its value
}
```

`gofmt`는 컬럼을 정렬할 것이다.

```go
type T struct {
    name    string // name of the object
    value   int    // its value
}
```

표준 패키지에 있는 모든 Go 코드는 `gofmt`로 포맷팅 되어 있다.

몇 가지 포맷팅 상세 내용이 남아 있는데, 짧게 보면 다음과 같다.

- 들여쓰기
    - 들여쓰기로서 탭을 사용하고, `gofmt`는 기본값으로 탭을 사용한다. 꼭 사용해야 하는 경우에만 스페이스를 사용하라.
- 라인 길이
    - Go는 라인 길이에 제한이 없다. 길이가 길어지는 것에 대해 걱정하지 않아도 된다. 라인이 너무 길다고 느낀다면, 감싸고 별도의 탭으로 들여쓰기 하라.
- 괄호
    - Go는 C, Java에 비해 적은 수의 괄호가 필요하다. 제어 구조체(`if`, `for`, `switch`)는 문법에서 괄호가 없다. 또한, 연산자 우선순위 계층이 짧고 명확하며,

    ```go
    x<<8 + y<<6
    ```

    다른 언어와 다르게 스페이싱이 함축하는 것을 의미한다.