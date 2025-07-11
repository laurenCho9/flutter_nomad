# flutter_nomad
## 07.09
Dart 시작하기 강의 수강 시작!

### 0. 소개 
정리
- 다트는 객체지향 언어다.
- <img width="400" alt="image" src="https://github.com/user-attachments/assets/43b8e12e-02da-481f-b9f5-cdc6c65a2551" />
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
  - <img width="453" alt="image" src="https://github.com/user-attachments/assets/496dc7b3-34d2-4b99-9180-6bf6c1b4f812" />
  - <img width="496" alt="image" src="https://github.com/user-attachments/assets/209e0707-e966-4091-976e-b052cdd10faf" />
  - 그리고 다른 방식으로 같은 값을 얻는 문법
  - (위 방식이 더 편리하다. 다트의 편의성/장점)
  - <img width="444" alt="image" src="https://github.com/user-attachments/assets/ca7223b7-6dd2-4cc3-92b0-3fe0c763495a" />
  - <img width="500" alt="image" src="https://github.com/user-attachments/assets/21ddf406-2157-4939-826a-7764a7d6a1b2" />
- maps: 객체 타입(키 밸류들 나열 된 거.)
  - <img width="302" alt="image" src="https://github.com/user-attachments/assets/d9f6b4e3-7851-4b08-b976-bc5b5be7282e" />
  - <img width="674" alt="image" src="https://github.com/user-attachments/assets/8fb751fe-a3e3-4e28-a69d-f33184c53ec8" />
  - <img width="533" alt="image" src="https://github.com/user-attachments/assets/701468ff-0473-430e-9365-fa4f04b0ecd6" />
  - 이 변수형의 자료형은 Map<String, Object>인데,
    - 그 이유는 key와 value로 이루어진 자료구조 Map을 만들었다는 것.
    - key는 String타입, value를 Object타입이라고 한다.
  - 왜 value가 Object야?
    - 다트에서는 모든게 객체로부터 생겨서 Object는 기본적으로 어떤 자료형이든지 될 수 있다.
    - ❗️Object타입을 타쓰의 any라고 보면 된다.
    - (말 그대로 어떤 것이든지 올 수 있는 것.)
  - ‼️근데 Map타입은 왠만하면 쓰지말고 class쓰는 게 훨 좋다. Map 방식은 "지양"해라.
- sets: 객체{}에 키 밸류 없이 값만 넣는 것.
  - <img width="284" alt="image" src="https://github.com/user-attachments/assets/555f096e-580a-44f6-b76c-a4c9a349b9d0" />
  - <img width="141" alt="image" src="https://github.com/user-attachments/assets/ca005274-0032-4e44-89e1-1a238ee1b63a" />
  - <img width="690" alt="image" src="https://github.com/user-attachments/assets/d5fe30ca-6659-42a7-8278-c3472dd6d40c" />
  - 이게 끝이다.
  - 추가적인 특징으로는
    - set 안의 값은 각각 유일하다.
      - <img width="285" alt="image" src="https://github.com/user-attachments/assets/720b4a5c-f805-4599-8b77-296ee751ed70" />
      - <img width="177" alt="image" src="https://github.com/user-attachments/assets/b927027f-86dc-4620-83a1-72834a228367" />
      - 1을 두번 추가, 5를 한번 추가했는데 1이 여전히 하나임
      - (❗️각각 유일한 값이므로, 중복되니까 추가 안된거임)
  - 만약에 list타입을 썼으면 1을 세번 추가했을 때 전부 뒤에 추가된 게 보임
    - <img width="646" alt="image" src="https://github.com/user-attachments/assets/97f3447b-fc3d-421f-8a35-f1d029d52562" />
    - <img width="685" alt="image" src="https://github.com/user-attachments/assets/fa47c8c9-abed-4916-88e9-e9555ee4d91e" />
  - 그럼 list랑 set은 각각 언제 써야해?
    - 요소가 항상 하나씩만 있어야 되면 set을 써주면 돼.
    - 그게 아니라면 list를 써야겠지.
  - 다트에서
    - list는 파이썬의 list와 같고(자스의 배열 array)
    - set은 파이썬의 tuple과 같다는데..(자스의 걍 객체object임)
  - 자스에도 Set이 있어! 라는데 다른 방식일 걸..
    - 찾아봄.
    - <img width="824" alt="image" src="https://github.com/user-attachments/assets/18778772-668d-479e-b0a8-65f57ea10ac7" />
    - <img width="731" alt="image" src="https://github.com/user-attachments/assets/2034b7d5-6d4a-42aa-b458-6ebd86761a6b" />

### 함수 종류
- 함수의 정의
  - 플러터의 함수 표기 방법
  - <img width="553" height="104" alt="image" src="https://github.com/user-attachments/assets/f4faafb7-6357-4519-a6e9-220c774b55c5" />
  - <img width="321" height="37" alt="image" src="https://github.com/user-attachments/assets/78ed996b-6d02-4acc-8d95-807b163e2135" />
  - <img width="332" height="106" alt="image" src="https://github.com/user-attachments/assets/b4f4c86d-3ab2-4d08-9345-2a93a83741ae" />
  - <img width="169" height="34" alt="image" src="https://github.com/user-attachments/assets/5d8db630-9e88-476f-bc4a-d8233aced8c5" />
- 이름이 지정된 매개변수(인자)
  - 다트의 함수는 named parameter라는 걸 지원해.(❗️플러터에서 자주 사용되는 개념)
  - 아.. 이거 걍 함수 안에 키 밸류 값 담아서 쏘는 거 잖아..
  - 에러 발생
    - <img width="535" height="132" alt="image" src="https://github.com/user-attachments/assets/69fde0a7-0608-48f6-aacf-745d752fa4b6" />
    - <img width="651" height="420" alt="image" src="https://github.com/user-attachments/assets/a4d27fb7-bd11-44b7-8ea1-9246fb31b173" />
  - 원인은?
    - <img width="774" height="349" alt="image" src="https://github.com/user-attachments/assets/b160d59a-0422-43d2-936a-4dbc335b8cf5" />
    - null safety란?
    - <img width="529" height="139" alt="image" src="https://github.com/user-attachments/assets/7de98834-67e2-4d68-85ce-9accbf6e14cc" />
      - 미리 값을 지정해줘야 한다.
      - 예시1)에러는 막았지만, 나쁜 예시
        - <img width="655" height="135" alt="image" src="https://github.com/user-attachments/assets/48ff6745-7f08-4083-a6c7-f4800b5ec06b" />
        - <img width="419" height="39" alt="image" src="https://github.com/user-attachments/assets/9eb48b0b-8e1b-41c2-8e27-497f493ca610" />
      - 예시2)required 키워드 사용 (추천)
        - 


























       







  







 






