<chapter 4>
===========
### <Introduction> ###  

**프로그래밍 언어를 구현하는 세가지 방법**  
**1. compilation(컴파일 방법)** : 컴파일러를 통해 고급 언어를 기계 코드로 번역 ex) C++, COBOL  
**2. pure interpretation(순수 해석)** :  해석기에 의해서 원래 형태에서 번역되지 않고 해석 ex) JavaScript (실행효율x)  
**3. hybrid implementation(혼합형 구현)** : 고급 언어를 중간 형태로 **번역**하고 **해석**. 컴파일보다 느림 ex) Java, Perl  
**4. JIT 컴파일러(Just-In-Time)** : 중간 코드를 기계 코드로 번역, 혼합형을 지연된 컴파일러 시스템으로 변환 ex) Java, .NET  
  
구문 분석기(Parser)는 CFG, **BNF** 형식에 기반한다.  
BNF로 구문을 기술하면 **좋은점**  
1. 인간이나 소프트웨어 시스템에게 **분명하고 간명**하다.  
2. 구문 분석기에 대한 직접적인 **기반**으로 사용된다.
3. 모듈 기반 작성으로 **유지보수**하기에 상대적으로 쉽다.  
  
위의 모든 구현 방법은 어휘 분석기(Scanner)와 구문 분석기(Parser)로 구문 분석 작업  
**Lexcial analyzer**(어휘 분석기)는 이름과 수치 리터럴과 같은 **작은 규모의 언어 구조**를 다루고,  
**Syntax analyzer**(구문 분석기)는 식, 문장, 프로그램 단위와 같은 **큰 규모의 언어 구조**를 다룬다.  
  
**구문 분석에서 어휘 분석를 분리하는 이유**  
1. **단순성** : 어휘 분석 기법은 구문 분석 기법보다 덜 복잡하므로 분리될 경우 더 단순해진다.
2. **효율성** : 어휘 분석은 컴파일 시간에 큰 비중을 차지하기 때문에 분리하여 선택적으로 최적화를 할 수 있다.  
3. **이식성** : 어휘 분석은 입력 프로그램 파일을 읽는 등 입력 버퍼를 포함하기 때문에 플랫폼에 종속적이다.
*****
### <Lexical Analyzer> ###  
  
> * Lexical analyzer(어휘 분석기)는 입력 문자열로부터 패턴에 맞게 문자들을 논리적인 그룹(lexemes = 어휘항목)으로 구분하고  
토큰(token)을 생성한다.
  
   * 주석과 공백을 제거한다.  
  
   * 사용자 정의 이름에 대한 어휘항목들을 심볼 테이블에 저장한다.  
  
   * 부동소수점과 같은 토큰 상의 오류를 탐지한다.  
  
   * 어휘분석기는 구문분석기가 다음 토큰을 알기 위해 호출되는 부프로그램이다.

**어휘 분석기를 구성하는 세가지 방법**
1. Regular Expression (정규 표현식)과 관련된 기술을 사용하여 분석기 구성  
2. State Transition Diagram (상태 전이도)을 설계하고 이를 프로그램으로 구현  
3. State Transition Diagram (상태 전이도)을 설계하고 Table_driven implementation (테이블 구동 구현)을 구성  


  
