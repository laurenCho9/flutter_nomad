# flutter_nomad
## 07.09
Dart 시작하기 강의 수강 시작!

### 0. 소개 
정리
- 다트는 객체지향 언어다.
- <img width="540" alt="image" src="https://github.com/user-attachments/assets/43b8e12e-02da-481f-b9f5-cdc6c65a2551" />
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
 
### 1. 변수
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
- 다이나믹 타입(타입스크립트의 any 타입 같은 느낌)
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


 






