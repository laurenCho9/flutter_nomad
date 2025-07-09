# flutter_nomad
## 07.09
Dart 시작하기 강의 수강 시작!

### 0. 소개 
정리
- 다트는 객체지향 언어다.
- <img width="240" alt="image" src="https://github.com/user-attachments/assets/43b8e12e-02da-481f-b9f5-cdc6c65a2551" />
- 다트는 UI에 최적화 되어있다.
- 생산적인 개발 환경을 가지고 있다.
- 모든 플랫폼에서 빠르다.
- 다트는 두 개의 컴파일러를 가지고 있는데, 다트 웹과 다트 네이티브다.
  - 다트 웹은 다트=>자바스크립트로 변환해주는 컴파일러
  - 다트 네이티브는 여러 CPU의 아키텍쳐에 맞게 변환해주는데, ARM32 등에 맞게 변환할 수 있다.
    - 이는 iOS, 안드로이드, 윈도우, 리눅스, 맥으로 컴파일 할 수 있다는 것을 의미한다.
    - 더 작은 전력의 아키텍쳐로도 변환이 가능하기 때문에 사물인터넷을 만드는데도 사용된다.
  - <img width="540" alt="image" src="https://github.com/user-attachments/assets/e48ee8b8-0440-4397-94e2-8b4614836a25" />
- [DartPad.Dev 다트 전용 코드플레이그라운드](https://dartpad.dev/)
  - 함수명은 main()이어야 하고,
  - {}가 자바스크립트와는 다르게 반드시 있어야 하고,
  - 세미콜론;이 없으면 에러 발생
 
### 1. 변수 종류
정리
- void main() {}
  - main 함수는 모든 다트 프로그램의 엔트리 포인트라서 없으면 안된다.
  - 실제로 동작하는 코드는 반드시 main 함수 안에 넣어줘야 작동한다.
  - 파이썬이랑 똑같은데 세미콜론; 유무 차이
  - <img width="200" alt="image" src="https://github.com/user-attachments/assets/7d3ab1b1-0926-4625-89d7-9846bdd78611" />
- 다트에는 변수는 var, 상수는 const로 딱 두 종류만 있다.
- var 예시
  - var 변수 선언 방식
    - 다트는 var를 선언해도 자동으로 이 타입이 string type 이라는 걸 안다.
    - <img width="175" alt="image" src="https://github.com/user-attachments/assets/e6e0e828-18ad-4137-bc61-f6000fe8dc47" />
  - 직접 어떤 타입이라고 지정하는 방식(명시적으로 변수의 타입을 지정하는 방식)
    - <img width="202" alt="image" src="https://github.com/user-attachments/assets/7b41902b-3108-4632-a6a4-6af1d3d457f6" />
  - 그럼 언제 어떤 걸 쓰느냐?
    - var
      - 관습적으로 함수나 메소드 내부에 지역 변수를 선언할 때
      - ❗️즉, 함수 안에서 지역변수를 선언하거나
        - 메소드 안에서 지역변수를 선언하는 상황이라면
        - var를 사용하는 게 다트 스타일가이드에서 권장하는 방식이다.
        - (컴파일러가 어차피 name의 타입이 문자열 타입이란 걸 알기 때문.)
        - <img width="194" alt="image" src="https://github.com/user-attachments/assets/162ec8fa-3939-4c73-acf5-cfe646e32ebd" />
    - 타입 지정(타입 명시)
      - 클래스에서 변수나 프로퍼티를 선언할 때
- 다이나믹 타입: 타입스크립트의 any 타입 같은 느낌
  - 사용은 지양해야 하나, var를 선언 혹은 dynamic 이라고 선언하고 값이 안담긴 상태를 의미합니다.
    - <img width="146" alt="image" src="https://github.com/user-attachments/assets/870d2157-d72c-4d1a-83ea-12550c76d626" />
    - <img width="148" alt="image" src="https://github.com/user-attachments/assets/76e4ed60-fd36-42e9-a4e6-d2beb9009cac" />
  - 이런 게 왜 있는 거야?
    - 변수가 어떤 타입일지 알기 어려운 경우(flutter나 json 작업을 하다보면)가 있어서,
    - dynamic 으로 돌아가는 게 유용한 경우가 있기 때문에 존재.
  - dynamic을 쓰면 다트가 보호해준다?고 한다.(걍 타입 애매하면 dynamic쓰란 소리)
    - 추가 활용 예시
      - <img width="195" alt="image" src="https://github.com/user-attachments/assets/b4958456-ced3-4cc8-bb2a-298a4617cc51" />
      - <img width="247" alt="image" src="https://github.com/user-attachments/assets/9e7e651c-fc61-4adf-950f-50336b1ce394" />
    - (근데 진짜 왠만하면 쓰지 마라..)
- null safety(nullable): 이거 걍 옵셔널체이닝 ? 이거임. "없을 수도(null) 있다."니까 같다고 볼 수 있음.
  - 문자열(String) 타입도 되고 값없음(null) 타입도 되었으면 할 때 ? 해주는 거임
  - 예를 들어 문자열 타입 지정을 지정했는데 null 값을 name이라는 변수에 재할당 하면 에러 발생하는데(이미 name은 Strign타입이므로!)
    - <img width="199" alt="image" src="https://github.com/user-attachments/assets/88fdb46b-0af9-499d-b543-7c89afb25837" />
  - 타입 선언(String) 뒤에 ?를 붙여서 에러 해소
    - <img width="215" alt="image" src="https://github.com/user-attachments/assets/edc11094-26d5-4f43-ac87-f55f31a2f7d4" />
  - 어라? 변수(var) 선언에는 적용안된다.
    - <img width="174" alt="image" src="https://github.com/user-attachments/assets/bf63776b-4d3a-48a9-bc7e-2122e96662e6" />
    - <img width="195" alt="image" src="https://github.com/user-attachments/assets/bdeb6536-6026-4d15-85a9-805fcb5d0f38" />
  - 추가 활용 예시
    - name이 null이 아니라면, isNotEmpty 속성을 달라고 요청하는 코드.
    - <img width="232" alt="image" src="https://github.com/user-attachments/assets/b8d31946-b186-4fd0-9caa-fce5681751df" />
- final 변수: javascript나 typescript의 const와 동일하다.
  - 한 번 정의된 변수를 수정할 수 없게 만든다.
  - 타입 변경 방지, 동일한 타입의 값 재할당도 금지.
    - <img width="204" alt="image" src="https://github.com/user-attachments/assets/c0ca7692-75fa-402b-8af9-f0872ad31f11" />
  - final 뒤에 타입 명시하는 방법도 있지만, 타입추론이 되므로 필수가 아니다.(타입 추론 되는 것은 타입 추론되게 두라.)
    - <img width="254" alt="image" src="https://github.com/user-attachments/assets/f168e28a-8719-4ce5-b6da-f775b7b4b300" />
- late 변수
  - 다트에서만 볼 수 있는 독창적 키워드인듯.
  - late는 final이나 var 앞에 붙여줄 수 있는 수식어다.
  - 아하.. late를 앞에 붙여주므로써, final(const와 동일)에 선언만 하고
  - "최초 한 번 재할당이 가능한 구조"로 만들어줌.
  - 선언한 name이라는 변수명에 "하윤"까지만 재할당이 되는 것을 확인할 수 있음.(이후 재할당 되는 건 전부 에러남)
    - <img width="240" alt="image" src="https://github.com/user-attachments/assets/e27b476c-2a56-4e69-9580-78c59a929c1b" />
    - <img width="240" alt="image" src="https://github.com/user-attachments/assets/8987ac54-8009-403a-bde9-f932353dc319" />
  - 그리고 값을 넣기 전에 print 등으로 접근하려고 하면 에러난다.
    - ❗️선언만 한 상태에서 값에 접근하려고 해서는 안된다.(변수에 값이 할당이 된 채로 접근해야 에러가 안난다.)
    - <img width="255" alt="image" src="https://github.com/user-attachments/assets/1a47ffe1-77cc-497e-9c19-e1c88d354c1b" />
    - <img width="252" alt="image" src="https://github.com/user-attachments/assets/6579e2af-a0a0-4a3a-944b-a29e58bb317b" />
  - 이것도 부득이할 때만 쓰는 거야. const를 권장하는 것과 같아.
  - 주로 API 호출할 때 쓴다.
- const 상수: ❗️다트에서의 const는 자바스크립트/타입스크립트의 const와 다른 것이라고 한다. !!
  - 자바스크립트/타입스크립트의 const는 dart의 final과 비슷함.
  - dart의 const는 compile-time constant(컴파일 타임 상수)를 만들어준다.(이건 또 뭐냐..)
  - 자, 그럼 다트에서 final과 const의 차이가 뭐냐.. 뭐가 다른 거냐
    - ❗️const는 compile-time(컴파일 타임)에 알고 있는 값이어야 한다는 거다.
    - 예를 들어, API키가 있다고 치면 컴파일러는 API의 변수 값을 몰라!
      - <img width="256" alt="image" src="https://github.com/user-attachments/assets/cd9a3d61-4d57-4f65-9812-f0c7e1b45f38" />
    - 즉, 이때는 final이 맞는 거.
      - <img width="253" alt="image" src="https://github.com/user-attachments/assets/8c824bf5-5702-438d-9395-a28d04257ee0" />
    - const 컴파일 할 때 알고 있는 값에 사용하는 것.
    - 풀어서 설명하자면, 앱스토어에 앱을 올리기 전에 알고 있는 값이어야 한다는 것(하드코딩 된 값 같은 것들)
  - ‼️요약(언제 어떤 변수를 사용해야하는지)
    - const
      - 앱 스토어에 앱을 올리기 전에 값을 알고 있는 값일 때.(하드코딩 된 값이면 해도 됌.)
    - ‼️final, var
      - ‼️어떤 값인지 모르고,
      - ‼️그 값이 API로 부터 페칭되어 온다거나
      - ‼️사용자가 화면에서 입력해야 하는 상호작용이 필요한 값일 때.
  - const도 꽤 쓰인다고 한다.
    - 특히 앱스토어에 올리기 전에 이미 알고 있는 값을 다룰 때.
    - 예를 들어 max_allowed_price 등..
    - ‼️앱에서 사용할 상수들이 있다면 const
      - <img width="281" alt="image" src="https://github.com/user-attachments/assets/97a7b438-6e1f-4cb3-8499-13c61ff894d5" />

### 2. 데이터 타입(자료형) 종류
- 기초 타입 종류
  - String: 문자열 타입
  - bool: 불리언 타입
  - int: 숫자(정수) 타입
  - double: 소수점을 포함한 숫자 타입
    - (❗️이건 정수 넣어도 .00으로 인식하는지 에러가 안나지만, int에 소수점 값 할당하면 에러 나면서 double 쓰라고 안내해준다.)
  - ❗️num: 정수일 수도 있고 소수점이 포함된 숫자 타입 모두에 적용해야할 경우 사용(권장인 듯.)
    - <img width="240" alt="image" src="https://github.com/user-attachments/assets/5520f561-f293-4a47-9ff1-dbb8c42f957c" />
    - <img width="240" alt="image" src="https://github.com/user-attachments/assets/9a19b9e0-b89c-49c3-b21d-25003bf75dd2" />
  - 위 모든 자료형을 포함한 다트의 거의 모든 것은 객체(Object)로 이루어져 있다고 보면 된다.
  - (function도 object니까..)
  - Dart가 객체 지향 언어로 불리는 이유.
- 목록 타입(List Type) 종류
  - 마찬가지로 var로 선언해도 되지만, 타입 선언으로도 가능하다.(둘 다 똑같이 돌아감)
    - <img width="280" alt="image" src="https://github.com/user-attachments/assets/7a2b66b8-74cb-433a-b773-386c7aae086a" />
    - <img width="280" alt="image" src="https://github.com/user-attachments/assets/6e912e11-d44e-4b96-b455-436631974113" />
  - 위에서도 언급했지만,
    - ❗️함수 선언 안에 선언하는 건 var 등의(변수 선언) 방식을 사용하세요.("지향"하셔야 합니다.. 같은데, 음.. 에러는 안나는 부분이니까.. 회사 코드 컨벤션을 따르세요.)
    - ❗️class를 다룰 때 자료형 명시(타입 선언) 방식을 사용하시요.
  - (var 변수 선언 후 마우스 오버 시 어떤 타입인지 알 수 있음)
    - <img width="735" alt="image" src="https://github.com/user-attachments/assets/bfddf809-e933-4f03-be22-81b34561e545" />
  - collection if
    - 다트 언어 등 몇 안되는 언어에 있는 방식으로,
    - if로 존재할 수도 안할 수도 있는 요소를 Lists 안에 추가할 수 있게 해주는 문법이다.
    - <img width="423" alt="image" src="https://github.com/user-attachments/assets/ecf4e6bf-f4d7-455f-a53e-c0d1f414a572" />
    - (와.. 자스/타스 유저가 이런 말하기는 좀 그렇지만 생김새가 ㄹㅇ 괴랄하다.. 배열안에 if문을..😨)
    - 아하, 왜 쓰나 했더니..
      - giveMeFive의 값이 true일 경우,
      - numbers 라는 변수에 담긴 배열 안에
      - 숫자인 5가 추가되는 거라고 한다.
      - 오..
    - 이 코드랑 같은 거라고 한다.
    - <img width="287" alt="image" src="https://github.com/user-attachments/assets/1c8abd03-6454-47da-acf7-2d2f28db94e2" />
      - 확실히 더 편리해보이기는 하네..
    - print로 출력해보면 배열 끝에 5가 추가된 것을 볼 수 있다.
    - <img width="425" alt="image" src="https://github.com/user-attachments/assets/53d9f9b9-1a71-41b0-937d-2ae9c8375638" />
    - <img width="287" alt="image" src="https://github.com/user-attachments/assets/99ca1ca1-3af8-4a5b-9562-8a6e57c291bc" />
    - <img width="100" alt="image" src="https://github.com/user-attachments/assets/6c553d16-5a6e-4429-ae24-f4090e767860" />
- 문자열 보간(String Interpolatio): 자스/타스에서 ${title}이런 식으로 넣던 거랑 같은 거임.
  - 인터폴레이션(interpolation)은 보간법, 즉, 알려진 값들을 이용하여 그 사이의 값을 추정하거나 예측하는 것을 의미.
  - 쉽게 말해 text에 변수를 추가하는 방법이다.
  - 아 이거 변수값 넣는 거 말하는 거네.
  - 예시
    - <img width="631" alt="image" src="https://github.com/user-attachments/assets/e2e5e18e-053c-4fe1-9875-5a63291ea94f" />
    - <img width="463" alt="image" src="https://github.com/user-attachments/assets/31596c77-e730-4f48-97c9-9d77c7fa049a" />
    - 큰 따옴표, 작은 따옴표 아무거나 상관없이 사용 가능
    - 자스/타스에서 $달러사인뒤에 {}중괄호만 뺀 모양새.
  - 변형 예시.. 여기엔 중괄호 붙네?
    - <img width="617" alt="image" src="https://github.com/user-attachments/assets/f9f3b127-86c3-495d-8d41-a22a6fb4bb2d" />
    - <img width="391" alt="image" src="https://github.com/user-attachments/assets/e9748784-67f4-4a3b-a974-eef07d49cb1e" />
    - ...? 아 머야 둘 다 중괄호 붙여도 에러 안남
    - ${age+2}로 + 사이에 띄어쓰기 안해도 에러 안남
    - <img width="617" alt="image" src="https://github.com/user-attachments/assets/01fc0787-a597-4fe3-a54e-db3ca2032607" />
    - 그리구 I'm에 따옴표 있어서 escape 기호(\)사용해줘야한다.(작은 따옴표로 감쌌을 경우, 겹치니까.)
    - 나는 큰 따옴표 써서 상관없었음.(에러 안났음.)
    - <img width="173" alt="image" src="https://github.com/user-attachments/assets/0b027e59-773b-415f-a1d0-622965eee9b8" />
- collection for
  - 뭐 이런 거..
  - <img width="439" alt="image" src="https://github.com/user-attachments/assets/6ac88245-b82e-4e28-abe3-85f4b84e48a9" />
  - <img width="495" alt="image" src="https://github.com/user-attachments/assets/c8fa2492-3ef9-4ef4-9fd3-833bc44b6ad9" />
  - 그리고 다른 방식으로 같은 값을 얻는 문법
  - (위 방식이 더 편리하다. 다트의 편의성/장점)
  - <img width="435" alt="image" src="https://github.com/user-attachments/assets/6cab4650-e278-4f49-a0fc-0cfe59b43acb" />
  - <img width="491" alt="image" src="https://github.com/user-attachments/assets/e8aa5334-e899-4837-843a-9dee1b79b1c3" />
- maps
  - 











       







  







 






