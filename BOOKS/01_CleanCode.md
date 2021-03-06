**[참고&출처: robinyeon님](https://github.com/robinyeon/TIL/blob/main/BOOKS/%ED%81%B4%EB%A6%B0%20%EC%BD%94%EB%93%9C(Clean%20Code).md)**

# [클린 코드(Clean Code)](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=34083680)

## 목차
0. [추천사 & 들어가면서](#추천사-&-들어가면서)
1. [깨끗한 코드](#1장-깨끗한-코드)
2. [의미 있는 이름](#2장-의미-있는-이름)
3. [함수](#3장-함수)
4. [주석](#4장-주석)
5. [형식 맞추기](#5장-형식-맞추기)
6. [객체와 자료 구조](#6장-객체와-자료-구조)
7. [오류 처리](#7장-오류-처리)
8. [경계](#8장-경계)
9. [단위 테스트](#9장-단위-테스트)
10. [클래스](#10장-클래스)


<br/>
<hr/>
<br/>

## 추천사 & 들어가면서
### 기억하고 싶은 책 내용
- 사소한 곳에서 발휘하는 정직은 사소하지 않다 -덴마크 속담 (p.xxii)
- 품질은 하늘에서 뚝 떨어진 위대한 방법론이 아니라 사심없이 기울이는 무수한 관심에서 얻어진다. (p.xxvii)

### 소감 및 생각
- 새벽에 일어나버려서 본의아니게 일찍 해버렸네..
- [robinyeon님 정리](https://github.com/robinyeon/TIL/blob/main/BOOKS/%ED%81%B4%EB%A6%B0%20%EC%BD%94%EB%93%9C(Clean%20Code).md)가 엄청남!

### 새롭게 배운 개념
- [메타포](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=semisun7021&logNo=70123000137): 익숙한 개념으로 익숙하지 않은 개념을 이해시키기위해 연결하는 것
- [애자일](https://gdtbgl93.tistory.com/127)
  - 스크럼(Scrum)
    - 애자일 방법론에는 스크럼, 칸반, XP 등 여러 방식이 존재하며 각자 다른 목적에 특화되어 있다.
    - 그 중 스크럼은 유지보수 보다는 개발에 초점이 맞추어진 애자일 방법론이다.
  - 백로그(Backlog)
    - 사용자를 조사하여 구현해야 할 사항을 정의한 문서: 제품 백로그 -> 스프린트 백로그
- [린(Lean)](http://www.incodom.kr/%EB%A6%B0_%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4_%EA%B0%9C%EB%B0%9C%EB%B0%A9%EB%B2%95%EB%A1%A0)
  - 낭비에 포커스를 두어 프로그램을 개발하는데 발생할 수 있는 모든 낭비를 최소화하고 결과를 측정, 성과를 분석하여 소프트웨어 가치를 최대화하고자 하는 것을 목표로 둔다.
    - 애자일 방법론 : 개인별 또는 팀 간에 고객과 협업하고 빠른 개발을 수행(고객과 협업)
    - 린 개발 방법론 : 고객 관점에서 전체 프로세스상에서 낭비를 제거하여 고객 가치를 높이는 것에 우선순위(전적으로 고객 관점)

<br/>
<hr/>
<br/>

## 1장. 깨끗한 코드
### 기억하고 싶은 책 내용
- TDD라는 분야는 우리 업계에 심오한 영향을 미치면서 오늘날 가장 근본적인 원칙 중 하나가 되었다. 테스트 케이스가 없는 코드는 깨끗한 코드가 아니다. 아무리 코드가 우아해도, 아무리 가독성이 높아도, 테스트 케이스가 없으면 깨끗하지 않다. (p.12)
- 새 코드를 짜면서 우리는 끊임없이 기존 코드를 읽는다.
- 비율이 이렇게 높으므로 읽기 쉬운 코드가 매우 중요하다. 기존 코드를 읽어야 새 코드를 짜므로 읽기 쉽게 만들면 사실은 짜기도 쉬워진다. (p.18)
- 캠프장은 처음 왔을 때보다 더 깨끗하게 해놓고 떠나라. (p.19)
- 처음 왔을 때보다 더 나은 세상을 만들고 떠나려 노력하라. (p.19)
- **"연습해, 연습!"** (p.20)

### 소감 및 생각
> 헛소리! 앞으로 코드가 사라질 가망은 전혀 없다! 왜? 코드는 요구사항을 상세히 표현하는 수단이니까! (p.2)
- 당장 실직 전망이 아니라 다행인 말이기는 한데, 의미는 알겠지만, 이렇게 단정적으로 말하면 다른 방법은 생각도 안해보고 있는거 같아서 불안하다..
> 대다수의 관리자는 진실을 원한다. 일정에 쫓기더라도 대다수 관리자는 좋은 코드를 원한다. 그들이 일정과 요구사항을 강력하게 밀어붙이는 이유는 그것이 그들의 책임이기 때문이다. 좋은 코드를 사수하는 일은 바로 우리 프로그래머들의 책임이다. (p.7)
- 그런데 관리자를 설득하는게 더 힘들어서 그냥 맞춰주는 경우가 많은듯.. 스스로 확신이 부족해서 그런걸까...

### 새롭게 배운 개념
- 르블랑의 법칙: 나중은 절대 돌아오지 않는다는 법칙
- [메서드 추출](https://armadillo-dev.github.io/book/refactoring-06-composing-methods/#:~:text=1.%20%EB%A9%94%EC%84%9C%EB%93%9C%20%EC%B6%94%EC%B6%9C,Permalink): 가장 많이 사용하는 기법으로, 메서드가 너무 길거나 코드에 주석을 달아야만 의도를 이해할 수 있을 때 그 코드를 별도의 메서드로 만든다. 이 때 메서드 명은 원리가 아닌 기능을 나타내는 이름으로 짓는다.
- [익스트림 프로그래밍(eXtreme Programming)(XP)](https://wooaoe.tistory.com/33#:~:text=%EB%B6%88%EC%96%B4%EB%84%A3%EC%96%B4%20%EC%A4%80%EB%8B%A4%EA%B3%A0%20%EB%A7%90%ED%95%98%EC%98%80%EB%8B%A4.%C2%A0-,eXtream%20Programming(XP),-%3F%C2%A0%C2%A0%0A%EB%AF%B8%EB%9E%98%EC%97%90%20%EB%8C%80%ED%95%9C%20%EC%98%88%EC%B8%A1%EC%9D%84): 미래에 대한 예측을 최대한 하지 않고, 지속적으로 프로토타입을 완성하는 애자일 방법론 중 하나이다. 이 방법론은 추가 요구사항이 생기더라도, 실시간으로 반영할 수 있다.

<br/>
<hr/>
<br/>


## 2장. 의미 있는 이름
### 기억하고 싶은 책 내용
- 이름은 다음과 같은 질문에 모두 답해야 한다. **존재 이유는? 수행 기능은? 사용 방법은?** 따로 주석이 필요하다면 의도를 분명히 드러내지 못했다는 말이다. (p.22)
- 실제 컨테이너가 List인 경우라도 컨테이너 유형을 이름에 넣지 않는 편이 바람직하다. (p.24)
- 클래스, 객체 이름은 명사나 명사구가 적합하다. (p.32)
- 메서드 이름은 동사나 동사구가 적합하다. (p.32)
- Constructor를 Overload할 때는 정적 팩토리 메서드를 사용한다. 메서드는 인수를 설명하는 이름을 사용한다. (p.32)
    ```java
    Complex fulcrumPoint = Complex.FromRealNumber(23.0);
    ```
- 프로그래머는 코드를 최대한 이해하기 쉽게 짜야 한다. 집중적인 탐구가 필요한 코드가 아니라 대충 훑어봐도 이해할 코드 작성이 목표다. (p.34)
- 맥락을 부여한다. 변수가 좀 더 큰 구조에 속한다는 사실이 독자에게는 분명해진다. 물론 Address라는 클래스를 생성하면 컴파일러에게도 분명해진다. (p.35)
- 이름에 불필요한 맥락을 추가하지 않도록 주의한다. (p.37)
- 암기는 도구에게 맡기고, 우리는 문장이나 문단처름 읽히는 코드 아니면 적어도 표나 자료 구조처럼 읽히는 코드를 짜는 데만 집중해야 마땅하다. (p.38)

### 소감 및 생각
- List, -Data, -Info 자주 썼는데... OTL
- 이래저래 영어공부가 필수인가..

### 궁금한 내용, 잘 이해되지 않는 내용
- [VISITOR 패턴](https://dailyheumsi.tistory.com/216) 작업 대상(방문 공간) 과 작업 항목(방문 공간을 가지고 하는 일)을 분리시킨 패턴

<br/>
<hr/>
<br/>

## 3장. 함수
### 기억하고 싶은 책 내용
- if/else, while 등에 들어가는 블록은 한 줄이어야 한다. 대게 거기서 함수를 호출한다. 그러면 enclosing function이 작아질 뿐 아니라, 블록 안에서 호출하는 함수 이름을 적절히 짓는다면, 코드를 이해하기도 쉬워진다.
  이 말은 중첩 구조가 생길만큼 함수가 커져서는 안 된다는 뜻이다. 그러므로 함수에서 들여쓰기 수준은 1단이나 2단을 넘어서면 안 된다. 당연한 말이지만, 그래야 함수는 읽고 이해하기 쉬워진다. (43)
- 단순히 다른 표현이 아니라 의미 있는 이름으로 다른 함수를 추출할 수 있다면 그 함수는 여러 작업을 하는 셈이다. (45)
- 함수가 확실히 '한 가지' 작업만 하려면 함수 내 모든 문장의 추상화 수준이 동일 해야 한다. (45)
- 코드는 위에서 아래로 이야기처럼 읽혀야 좋다. 한 함수 다음에는 추상화 수준이 한 단계 낮은 함수가 온다. 나는 이것을 내려가기 구칙이라 부른다. (46)
- 서술적인 이름을 사용하라! (49)
- 서술적인 이름을 사용하면 개발자 머릿속에서도 설계가 뚜렷해지므로 코드를 개선하기 쉬워진다. (49)
- 함수에서 이상적인 인수 개수는 0개다. (50)
- 부수 효과를 일으키지 마라! 많은 경우 시간적인 결합 temporal coupling 이나 순서 종속성 order dependency를 초래한다. (54)
- 오류 처리도 한 가지 작업이다. (59)

### 소감 및 생각, 궁금한 내용, 잘 이해되지 않는 내용
- 그런데 가끔 함수를 엄청 쪼개놨는데, 이름으로 어떤 함수인지 바로 파악이 안되면, 쪼갠 함수 일일히 들어가서 확인하고 오느라 파악이 더 오래 걸린다.
- OOP가 아니어도 모두 완벽하게 유효한 조언일까? 맞다면 사례는? 아니라면 어떤면에서?

<br/>
<hr/>
<br/>

## 4장. 주석
### 기억하고 싶은 책 내용
- 주석이 필요한 상황에 처하면 곰곰이 생각하기 바란다. 상황을 역전해 코드로 표현할 방법은 없을까? (68)
- 좋은 주석: 의도를 설명하는 주석 - 때때로 주석은 구현을 이해하게 도와주는 선을 넘어 결정에 깔린 의도까지 설명한다. (71)
- 좋은 주석: 결과를 경고하는 주석 - ex) ~은 스레드에 안전하지 못하여, 각 인스턴스를 독립적으로 생성해야 한다. (73)

### 소감 및 생각, 궁금한 내용, 잘 이해되지 않는 내용
- 주석 싫어하는 사람들이 많아서, todo 말고 다 지우고 커밋했었는데, 필요한 주석이 있기는 있었구나... todo랑 경고주석은 남겨둘걸 그랬나..

<br/>
<hr/>
<br/>

## 5장. 형식 맞추기
### 기억하고 싶은 책 내용
- 오랜 시간이 지나 원래 코드의 흔적을 더 이상 찾아보기 어려울 정도로 코드가 바뀌어도 맨 처음 잡아놓은 구현 스타일과 가독성 수준은 유지보수 용이성과 확정성에 계속 영향을 미친다. (96)
- 일련의 행 묶음은 완결된 생각 하나를 표현한다. (98)
- 시스템이 무엇을 하는지 이해하고 싶은데, 이 조각 저 조각이 어디에 있는지 찾고 기억하느라 시간과 노력을 소모한다. (101)
- 변수는 사용하는 위치에 최대한 가까이 선언한다. (101)
- 반면, 인스턴스 변수는 클래스 맨 처음에 선언한다. (103)

### 소감 및 생각, 궁금한 내용, 잘 이해되지 않는 내용
> 한 함수가 다른 함수를 호출한다면 두 함수는 세로로 가까이 배치한다. 또한 가능하다면 호출하는 함수를 호출되는 함수보다 먼저 배치한다. 그러면 프로그램이 자연스럽게 읽힌다. (104)
- 앞에 놔야하나 뒤에 놔야하나 우왕좌왕했는데, 이제 금방 정할 수 있겠다.

### 새롭게 배운 개념
- 일반적으로 C++ 에서는 모든 [인스턴스 변수](https://bit.ly/3s8Rv98)를 클래스 마지막에 선언한다는 [소위 가위규칙(scissors rule)](http://kastalien.org/wp/?p=128)을 적용한다.

<br/>
<hr/>
<br/>

## 6장. 객체와 자료 구조
### 기억하고 싶은 책 내용
- 변수를 private으로 선언하더라도 각 값마다 get 함수와 set 함수를 제공한다면 구현을 외부로 노출하는 셈이다. (118)
- 변수 사이에 함수라는 계층을 넣는다고 구현이 저절로 감춰지지는 않는다. 추상 인터페이스를 제공해 사용자가 구현을 모른 채 자료의 핵심을 조작할 수 있어야 진정한 의미의 클래스다. (119)
- 자료를 세세하게 공개하기보다는 추상적인 개념으로 표현하는 편이 좋다. 인터페이스나 get/set 함수만으로는 추상화가 이뤄지지 않는다. 개발자는 객체가 포함하는 자료를 표현 할 가장 좋은 방법을 심각하게 고민해야 한다. (119)
- 객체와 자료 구조 사이에 벌어진 차이를 보여준다. 객체는 추상화 뒤로 자료를 숨긴 채 자료를 다루는 함수만 공개한다. 자료 구조는 자료를 그대로 공개하며 벌댜른 함수는 제공하지 않는다. (119)
- (자료 구조를 사용하는) 절차적인 코드는 기존 자료 구조를 변경하지 않으면서 새 함수를 추가하기 쉽다. 반면, 객체 지향 코드는 기존 함수를 변경하지 않으면서 새 클래스를 추가하기 쉽다. (122)
- ctxt가 객체라면 **뭔가를 하라고** 말해야지 속을 드러내라고 말하면 안 된다. (125)
- 자료 구조체(자료 전달 객체, Data Transfer Object, DTO)의 전형적인 형태는 공개 변수만 있고 함수가 없는 클래스다. DB와 통신하거나, 소켓에서 받은 메시지의 구문을 분석할 때 유용하다. (126)
- 점 더 일반적인 형태는 'Bean'구조다. 빈은 private 변수를 get/set 함수로 조작한다. 일종의 사이비 캡슐화로, 일부 OO순수주의자나 만족시킬 뿐 별다른 이익을 제공하지 않는다. (126)
- 활성 레코드는 DTO의 툭수한 형태다. 활성 레코드는 자료 구조로 취급한다. 비지니스 규칙을 담으면서 내부 자료를 숨기는 객체는 따로 생성한다. (127)
- **객체**는 동작을 공개하고 자료를 숨긴다. 그래서 기존 동작을 변경하지 않으면서 새 객체 타입을 추가하기는 쉬운 반면, 기존 객체에 새 동작을 추가하기는 어렵다. **자료 구조**는 별다른 동작 없이 자료를 노출한다. 그래서 기존 자료 구조에 새 동작을 추가하기는 쉬우나, 기존 함수에 새 자료 구조를 추가하기는 어렵다. (127)
- 시스템을 구현할 때, 새로운 자료 타입을 추가하는 유연성이 필요하면 객체가 더 적합하다. 다른 경우로 새로운 동작을 추가하는 유연성이 필요하면 자료 구조와 절차적인 코드가 더 적합하다. (128)

### 소감 및 생각, 궁금한 내용, 잘 이해되지 않는 내용
- 노련한 객체 지향 설계자는 VISITOR 혹은 Dual-Patch 등과 같이 잘 알려진 기법을 사용해 이 문제를 해결한다. 하지만 이들 기법 역시 대가가 따르며, 일반적으로 절차적인 프로그램에서 볼 수 있는 구조를 반환한다. (옮긴이) VISITOR 패턴은 주로 상속 없이 클래스에 메서드를 효과적으로 추가하기 위해 사용한다. 하지만 합성 객체의 내부 구조가 VISITOR에 열리게 되므로 캡슐화를 위반한다는 문제점이 생긴다. (121)
- **디미터 법칙**은 잘 알려진 heuristic으로, 모듈은 자신이 조작하는 객체의 속사정을 몰라야 한다는 법칙이다. 좀 더 정확히 표현하자면, 디미터 법칙은 "클래스 C의 메서드 f는 다음과 같은 객체의 메서드만 호출해야 한다"고 주장한다.
  - 클래스 C
  - f가 생성한 객체
  - f 인수로 넘어온 객체
  - C 인스턴스 변수에 저장된 객체 (123)
- train wreck 예) final String outputDir = ctxt.getOptions().getScratchDir().getAbsolutePath(); (123)

### 새롭게 배운 개념
- [디미터 법칙](https://tecoble.techcourse.co.kr/post/2020-06-02-law-of-demeter/): 객체 간 관계를 설정할 때 객체 간의 결합도를 효과적으로 낮출 수 있는 유용한 지침 중 하나.
  - 다른 객체들과의 협력을 통해 프로그램을 완성해나가는 객체지향 프로그래밍에서 객체들의 협력 경로를 제한하면 결합도를 효과적으로 낮출 수 있다

<br/>
<hr/>
<br/>

## 7장. 오류 처리
### 기억하고 싶은 책 내용, 소감 및 생각, 궁금한 내용, 잘 이해되지 않는 내용
- 얼마 전까지만 해도 예외를 지원하지 않는 프로그래밍 언어가 많았다. 오류 플래그를 설정하거나 호출자에게 오류 코드를 반환하는 방법이 전부였다. (130)
    > 요즘 쓰는 golang 도 예외 없는데! 예외가 오류보다 우월하다는게 정설일까? 논의를 알아보고 싶다.
- 확인된 예외는 Open Closed Principle(OCP)를 위반한다. 메서드에서 확인된 예외를 던졌는데 catch 블록이 세 단계 위에 있다면 그 사이 메서드 모두가 선언부에 해당 예외를 정의해야 한다. 즉, 하위 단계에서 코드를 변경하면 상위 단계 메서드 선언부를 전부 고쳐야 한다는 말이다. (134)
- 때로는 확인된 예외도 유용하다. 아주 중요한 라이브러리를 작성한다면 모든 예외를 잡아야 한다. 하지만 일반적인 애플리케이션은 의존성이라는 비용이 이익보다 크다. (135)
- 예외를 던질 때는 전후 상황을 충분히 덧붙인다. 그러면 오류가 발생한 원인과 위치를 찾기가 쉬워진다. 자바는 모든 예외에 호출 스택을 제공한다. 하지만 실패한 코드의 의도를 파악하려면 호출 스택만으로 부족하다.
오류 메시지에 정보를 담아 예외와 함께 던진다. 실패한 연산 이름과 실패 유형도 언급한다. 애플리케이션이 로깅 기능을 사용한다면 catch 블록에서 오류를 기록하도록 충분한 정보를 넘겨준다. (135)
- 메서드에서 null을 반환하고픈 유혹이 든다면 그 대신 예외를 던지거나 특수 사례 객체를 반환한다. (139: null을 반환하지 마라)
    > golang 에서는 error 반환이 많아서, return nil을 매우 자주 쓰는데... 당연히 확인도 자주하고....
- 깨끗한 코드는 읽기도 좋아야 하지만 안정성도 높아야 한다. 이 둘은 상충하는 목표가 아니다. 오류 처리를 프로그램 논리와 분리해 독자적인 사안으로 고려하면 튼튼하고 깨끗한 코드를 작성할 수 있다. 오류 처리를 프로그램 논리와 분리하면 독립적인 추론이 가능해지며 코드 유지보수성도 크게 높아진다. (142: 결론)

### 새롭게 배운 개념
- 특수 사례 패턴(SPECIAL CASE PATTERN)이라 부른다. 클래스를 만들거나 객체를 조작해 특수 사례를 처리하는 방식이다. 그러면 클라이언트 코드가 예외적인 상황을 처리할 필요가 없어진다. 클래스나 객체가 예외적인 상황을 캡슐화해서 처리하므로. (138)


<br/>
<hr/>
<br/>

## 8장. 경계
### 기억하고 싶은 책 내용, 소감 및 생각, 궁금한 내용, 잘 이해되지 않는 내용
- 경계 인터페이스를 이용할 때는 이를 이용하는 클래스나 클래스 계열 밖으로 노출되지 않도록 주의한다. Map 인스턴스를 공개 API의 인수로 넘기거나 반환값으로 사용하지 않는다. (146)
- 외부 패키지를 호출하는 코드를 가능한 줄여 경계를 관리하자. 새로운 클래스로 경계를 감싸거나 아니면 ADAPTER 패턴을 사용해 우리가 원하는 인터페이스를 패키지가 제공하는 인터페이스로 변환하자. 어느 방법이든 코드 가독성이 높아지며, 경계 인터페이스를 사용하는 이관성도 높아지며, 외부 패키지가 변했을 때 변경할 코드도 줄어든다. (152)

<br/>
<hr/>
<br/>

## 9장. 단위 테스트 
### 오늘 TIL 3줄 요약
#### TDD 법칙 세 가지 (155)
1. 실패하는 단위 테스트를 작성할 때까지 실제 코드를 작성하지 않는다.
2. 컴파일은 실패하지 않으면서 실행이 실패하는 정도로만 단위 테스트를 작성한다.
3. 현재 실패하는 테스트를 통과할 정도로만 실제 코드를 작성한다

### 책에서 기억하고 싶은 내용을 써보세요.
- 그러므로 실제 코드를 점검하는 자동화된 단위 테스트 슈트는 설계와 아키텍처를 최대한 깨끗하게 보존하는 열쇠다. 테스트는 유연성, 유지보수성, 재사용성을 제공한다. 테스트 케이스가 있으면 **변경**이 쉬워지기 때문이다. (157)
- 깨끗한 테스트 코드를 만들려면? 세 가지가 필요하다. 가독성, 가독성, 가독성. (158)
- BUILD-OPERATE-CHECK 패턴이 위와 같은 테스트 구조에 적합하다. 각 테스트는 명확히 세 부분으로 나눠진다. 첫 부분은 테스트 자료를 만든다. 두 번째 부분은 테스트 자료를 조작하며, 세 번째 부분은 조작한 결과가 올바른지 확인한다. (161)
- 숙련된 개발자라면 자기 코드를 좀 더 간결하고 표현력이 풍부한 코드로 리팩터링해야 마땅하다. (161)
- 깨끗한 테스트의 다섯가지 규칙: Fast, Indenpendent, Repeatable, Self-validating(return bool), Timely (167) 
- Timely: 테스트는 적시에 작성해야 한다. 단위 테스트는 테스트하려는 실제 코드를 구현하기 직전에 구현한다. 실제 코드를 구현한 다음에 테스트 코드를 만들면 실제 코드가 테스트하기 어렵다는 사실을 발견할지도 모른다. (168)

### 오늘 읽은 소감은? 떠오르는 생각을 가볍게 적어보세요
- 사실 테스트 코드는 golang을 시작하면서 처음 배웠는데, 매우 잘 쓰고 있다. 처음에는 번거로웠는데, 이제는 이거 없이 리팩토링 어떻게 했을까 싶다.
- 확실히 테스트의 가장 큰 필요성은 수정을 쉽게해서 코드를 개선하거나 기능을 추가하기 쉽게 만들어 주는데 있는 것 같다.
- ... 다만 부족하게 작성한 테스트 코드만 의지하다가는.... ㄷㄷㄷ

### 궁금한 내용이 있거나, 잘 이해되지 않는 내용이 있다면 적어보세요.
- BUILD-OPERATE-CHECK 패턴

### 오늘 읽은 다른사람의 TIL
- [Young님의 TIL](https://whyjun.github.io/golang/Enum-in-Golang)
    - clean code TIL 읽다가 맨 앞의 글을 읽었는데, 아아.. 이걸 진작 읽었어야 했다..ㅠㅠ

<br/>
<hr/>
<br/>


## 10장. 클래스
### 오늘 TIL 요약
- 동작하게 만든 다음에는 구조를 계선해서 깨끗하고 체계적인 SW로 만들어야 한다.
- 일부 멤버 변수를 일부 메서드들만 사용한다면, 그것이 클래스 분리의 신호!

### 책에서 기억하고 싶은 내용을 써보세요.
- 클래스를 정의하는 표준 자바 관례에 따르면, 가장 먼저 변수 목록이 나온다. static public 상수가 있다면 맨 처음에 나온다. 다음으로 static private 변수가 나오며, 이어서 private instance 변수가 나온다. <br/> 변수 목록 다음에는 public 함수가 나온다. private 함수는 자신을 호출하는 public 함수 직후에 넣는다. 즉, 추상화 단계가 순차적으로 내려간다. (172)
- 변수나 유틸리티 함수를 protected로 선언해 테스트코드에 접근을 허용하기도 한다. 하지만 그 전에 비공개 상태를 유지할 온갖 방법을 강구한다. 캡슐화를 풀어주는 결정은 언제나 최후의 수단이다. (172)
- __Single Responsibility Principle__ (SRP)은 클래스나 모듈을 변경할 이유가 단 하나 뿐이어야 한다는 원칙이다. (175)
- 문제는 우리들 대다수가 프로그램이 돌아가면 일이 끝났다고 여기는 데 있다. '__깨끗하고 체계적인 소프트웨어__'라는 **다음 관심사**로 전환하지 않는다. 만능 클래스를 단일 책임 클래스 여럿으로 분리하는 대신 다음 문제로 넘어가버린다. (176)
- 일반적으로 메서드가 변수를 더 많이 사용할수록 메서드와 클래스는 응집도가 더 높다. <br/> 응집도가 가장 높은 클래스는 가능하지도 바람직하지도 않다. 그렇지만 응집도가 높다는 말은 클래스에 속한 메서드와 변수가 서로 의존하며 논리적인 단위로 묶인다는 의미이다. (177: Cohesion)
- 경험에 의하면 클래스 일부에서만 사용되는 비공개 메서드는 코드를 개선할 잠재적인 여지를 시사한다. 하지만 실제로 개선에 뛰어드는 계기는 시스템이 변해서라야 한다. Sql 클래스를 논리적으로 완성이라 여긴다면 책임을 분리하려 시도할 필요가 없다. 가까운 장래에 Update 문이 필요하지 않다면 Sql 클래스를 내버려두는 편이 좋다. 하지만 클래스에 손대는 순간 설계를 개선하려는 고민과 시도가 필요하다. (186)

### 오늘 읽은 소감은? 떠오르는 생각을 가볍게 적어보세요
- 아아.. *_test.go 파일들 다른 package에 있어서 public을 써야하는 경우가 슬프다.
- 그외 몇 가지 당장 고쳐야 하나 하다가 미루고 있는데 186 페이지가 약간의 위로가 되기는 한다. 다만, 이제 만들거나 수정하는 test 파일들은 통일성을 깨더라도 미리 본인 package에 만들어 둬야겠다.

### 궁금한 내용이 있거나, 잘 이해되지 않는 내용이 있다면 적어보세요.
- 186페이지의 인용은, 이제까지 이책의 어조와 달리 상당히 타협적인 느낌이다.
- 표준 자바 관례... 표준 고랭 관례도 궁금하다.

### 오늘 읽은 다른사람의 TIL
- [Young님의 9장 TIL](ttps://whyjun.github.io/books/Read-Clean-Code-in-Go-08)
  - 첫번째 소감 대공감ㅠㅠ

<br/>
<hr/>
<br/>


## 11장. 시스템
### 오늘 TIL 3줄 요약

### TIL (Today I Learned) 날짜
- 

### 책에서 기억하고 싶은 내용을 써보세요.
- 

### 오늘 읽은 소감은? 떠오르는 생각을 가볍게 적어보세요
- 
### 궁금한 내용이 있거나, 잘 이해되지 않는 내용이 있다면 적어보세요.
- 

### 오늘 읽은 다른사람의 TIL
- 

<br/>
<hr/>
<br/>


<hr/>



### 오늘 TIL 3줄 요약
- 좋은 코드는 좋은 소설처럼 
- 깨끗한 코드는 주의 깊게 작성한 코드다
- 독자를 생각하며 코드를 쓰자
### TIL (Today I Learned) 날짜
- 2022.02.04

### 오늘 읽은 범위
- 1장. 깨끗한 코드

### 책에서 기억하고 싶은 내용을 써보세요.
- 깨끗한 코드는 주의 깊게 작성한 코드다.

### 오늘 읽은 소감은? 떠오르는 생각을 가볍게 적어보세요
- 읽었을 때 무슨말인지 모르겠는 코드, 쓰면서 찜찜한 코드는 쓰지말자!

### 궁금한 내용이 있거나, 잘 이해되지 않는 내용이 있다면 적어보세요.
- 단위 테스트? 인수 테스트?

### 오늘 읽은 다른사람의 TIL
- 00님의 TIL (url 링크)

<br/>

#노마드클럽 #북클럽 #노개북


**[참고&출처: robinyeon님](https://github.com/robinyeon/TIL/blob/main/BOOKS/%ED%81%B4%EB%A6%B0%20%EC%BD%94%EB%93%9C(Clean%20Code).md)**