# 2Week
# 06장 분기 구문과 논리 연산자

**if 구문**<br>
if 구문은 특정한 행동을 수행할 것인지 말 것인지 선택 할 때 사용한다.<br>
if 구문은 if와 if else 두 가지가 있으며 중첩해서 사용 가능하다.<br>
아래는 if else문 코드 예시이다.
```cpp
int Sample = 0;
cin >> Sample;
if(Sample > 10)
  cout << "입력한 값이 10보다 큽니다."
if else(Sample < 5)
  cout << "입력한 값이 5보다 작습니다."
else
  cout << "입력한 값이 5보다 크고 10보다 작습니다."
```
또한 중첩 if 문은 아래와 같이 사용할수 있다.
```cpp
if(Sample > 10)
  if(Sample <20)
    cout << "입력한 값이 20보다 작고 10보다 큽니다."
  else
    cout << "입력한 값이 20보다 큽니다."
else
  cout << "입력한 값이 10보다 작습니다."
```
위 코드를 후에 배울 논리연산자를 통해 아래와 같이 변형할수도 있다.
```cpp
if(Sample > 10 && Sample < 20)
  cout << "입력한 값이 20보다 작고 10보다 큽니다."
else
  cout << "입력한 값이 20보다 크거나 10보다 작습니다."
```
**논리 연산자**<br>
하나 이상의 조건을 검사해야 하는 경우에 사용하는 연산자 이다.<br>
논리 연산자에는 세 가지가 있는데 논리합(||), 논리곱(&&), 논리부정(!) 이다.<br>
아래의 예제들과 함께 설명하도록 하겠다.<br>
**논리합(||)** <br>
대체 표기로는 or을 사용하는 연산자이다.<br>
```cpp
cin >> a
if(a > 5 || a < 2) // if(a > 5 or a < 2) 으로 변환하여 사용 가능
  cout << "True";
else
  cout << "False";
```
만약 위 코드에서 **6** 를 입력하게 된다면 아래와 같은 출력 결과가 나온다.
```
True
```
만약 **3** 을 입력하게 된다면 아래와 같은 출력 결과가 나온다.
```
False
```
위 예제로 알수 있듯이 논리합(||) 연산자는 두개의 조건중 하나의 조건이라도 만족한다면 True로 동작한다<br>

<br>**논리곱(&&)** <br>
대체 표기로는 and를 사용하는 연산자이다.<br>
```cpp
cin >> a
if (a < 5 && a > 3) // if(a < 5 and a > 3) 으로 변환하여 사용 가능
  cout << "True"
else
  cout << "False"
```
만약 위 코드에서 **2** 를 입력하면 아래와 같은 출력 결과가 나온다.
```
False
```
이유는 두개의 조건중 a < 5 의 조건에만 성립하기 때문이다.<br>
그렇다면 두개의 조건을 모두 만족하는 **4** 를 넣는다면 어떤 출력 결과가 나올까?
```
True
```
위 출력 결과로 알수있듯 논리곱(&&) 연산자는 두개의 조건이 모두 만족해야 True로 동작한다<br>

<br>**논리부정(!)** <br>
대체 표기로는 not를 사용하는 연산자이다.<br>
```cpp
bool Sample = True;
if(!Sample)
  cout << "True"
else
  cout << "False"
```
위 코드를 실행시키면 아래와 같은 출력 결과가 나온다.
```
False
```
출력 결과를 보면 알수있듯 논리 부정은 수식의 결과값이 False일 경우 True로 동작한다.<br>
이해를 돕기 위해 아래의 예제를 추가하였다.
```cpp
if(a != 2) //a가 2가 아닐경우
if(!a) // a가 True가 아닐경우
if(!(a > 3)) // a가 3보다 크지 않을 경우
```
예제와 같이 수식의 결과값이 False일 경우 True 로 동작한다.<br>

<br> **?: 연산자** <br>
:? 연산자는 if else 구문 대신에 사용할수 있는 연산자이다. **조건연산자** 라고 부른다.<br>
작동 방식은 아래와 같다
```cpp
a > b ? a : b; // a > b 가 True 라면 a False 라면 b
```
즉 아래와 같이 활용할수 있다.
```cpp
int a,b;
cout << "두 개의 정수를 입력하십시오 :";
cin >> a >> b;
int sample = a > b ? a:b
cout << "입력하신 정수중 더 큰 정수는" << sample << "입니다.";
```
아래와 같이 중첩해서 사용할수도 잇다.
```cpp
sample = ((i < 2) ? !i ? a : b : c)
```
위 조건 연산자의 작동방식은 아래와 같다.
```
1. i 가 2보다 작은지 판별한다
  i 가 2보다 작을경우
    2. i가 0이 맞는지 판별한다
      3. 0이 맞다면 a를 틀리다면 b를 sample에 대입한다.
  i 가 2보다 크거나 같을경우
    2. c를 sample에 대입한다.
```
단 이렇게 중첩해서 사용하면 코드를 이해하기 어려워 질수도 있다.

# 함수 : C++의 프로그래밍 모듈
**함수 매개변수와 값으로 전달하기** <br>
C++은 함수 매개변수를 값으로 전달한다. 아래의 예제를 통해 알아보겠다.
```cpp
double sample(double x)
{
  ...
}
```
만약 위와 같이 선언된 함수를 아래와 같이 선언했다고 가정해보자.
```cpp
double test = 1;
sample(test);
```
함수는 호출될때 double 형태의 x라는 변수를 생성하여 그곳에 test라는 값을 대입한다.<br>
즉 원본 데이터가 아닌 test의 복사본을 가지고 작업하기 때문에 sample 함수에서 어떤 작업을 하든 main 함수의 test에 영향을 주지 않는다.<br>

<br> **함수와 배열** <br>
만약 학생들의 점수의 총 합을 구해야하는 함수가 필요한 상황이라고 가정을 해보자.<br>
학생들의 점수가 배열에 입력이 되어 있을것이다. 하지만 함수를 사용할때 아래와 같이 함수를 코딩하는 경우가 있을것이다.<br>
```cpp
const int Max = 5;

int Sum_score(int x[])
{
  int total = 0;
  for(int i = 0; i < (sizeof(x)/sizeof(int)); i++)
  {
    total += x[i];
  }
  return total;
}

void main()
{
  int score[Max] = {5, 4, 3, 2, 1};
  cout << "학생들의 점수 합은 :" << Sum_score(score) << "입니다.";
}
```
위와 같이 코드를 작성하고 실행시 아래와 같은 결과가 나온다.
```
학생들의 점수 합은 : 9 입니다.
```
분명 socre 의 합은 15인데 0번째와 1번째 인덱스만 더해진 9가 출력된게 된다.<br>
그 이유는 매개변수로 배열 전달시 배열이 주소값을 넘겨줌으로 메서드 안에서 sizeof 함수를 사용하면 포인터의 길이를 넘겨주기 때문이다.<br>
C++ 에서는 **Call by Value(값에 의한 전달 방식)** 의 한계를 극복하기 위해 **Call by Address(주소에 의한 전달 방식)** 을 사용하기 때문이다.<br>
즉 배열을 매개변수로 넘겨주어 그 배열을 합을 구하기 위해서는 같이 그 배열의 길이를 넘겨주어야 한다.
```cpp
const int Max = 5;

int Sum_score(int x[], int len)
{
  int total = 0;
  for(int i = 0; i < len; i++)
  {
    total += x[i];
  }
  return total;
}

void main()
{
  int score[Max] = {5, 4, 3, 2, 1};
  cout << "학생들의 점수 합은 :" << Sum_score(score,Max) << "입니다.";
}
```
위 코드를 실행하면 아래와 같이 정상적으로 실행된다
```
학생들의 점수 합은 : 15 입니다.
```
또한 위 코드에서 함수원형 부분을 아래와 같이 수정해도 정삭적으로 작동한다.
```cpp
int Sum_score(int *x, int len)
```
*arr, int arr[] 두개 모두 int 형을 지시하는 포인터를 의미하기 때문이다. <br>
단 int arr[] 은 배열의 **첫 번째 원소를 지시**하기 때문에 다른 상황에서 서로 다른 의미를 가질수 있다는 것을 기억해야 한다.<br>
만약 함수에 2차원 배열을 매개변수로 받고 싶다면 아래와 같이 선언하면 된다.<br>
```cpp
함수타입 함수이름(배열타입 *(배열이름[크기], int 배열길이);
아래는 예시이다.
int Sample(int *(array)[4], int size);
또는
int Sample(int array[][4], int size);
```

<br> **함수와 구조체** <br>
아래는 코드 예시이다.
```cpp
struct sample
{
  int t1;
  int t2;
}

sample Function_Sample(sample s1, sample s2)
{
  return ((s1.t1 + s2.t1) / (s1.t2 + s2.t2))
}

void main()
{
  sample Test1 = {10,30};
  sample Test2 = {20,30}
  cout << Function_Sample(Test1,Test2);
}
```
결과값은 아래와 같다.
```
0.5
```
위와 같이 함수원형 자체를 구조체 형태로 선언하여 사용할수 있다.
만약 구조체의 주소만 넘겨 공간과 시간을 절약하고 싶다며 아래와 같은 방식을 사용할수 있다.
```cpp
struct sample
{
  int t1;
}

void SampleF(sample * s1)
{
  cout << s1->t1;
}

void main()
{
  sample x = 3;
  SampleF(&x);
}
```
결과값은 아래와 같다.
```
3
```

<br> **재귀호출** <br>
재귀 호출은 함수가 자기 자신을 호출하는것을 말한다. 단 C와 다르게 C++은 main 함수가 자기 자신을 호출하는걸 허용하지 않는다.<br>
카운트다운 함수로 예시를 들어보겠다.
```cpp
void count(int n)
{
  cout << "카운트다운 " << n << endl;
  if (n > 0)
    count(n-1);
}

void main()
{
  count(3);
}
```
결과는 아래와 같다.
```
카운트다운 3
카운트다운 2
카운트다운 1
카운트다운 0
```
또한 아래와 같이 재귀호출을 중복으로 할수 있다.
```cpp
```
# 08장 함수의 활용

<br> **인라인 함수** <br>
인라인 함수는 수학의 치환과 비슷한 개념이다. <br>
아래는 인라인 함수의 예시이다.
```cpp
inline int Sum(int x, int y) { return x + y }

void main()
{
  int a = 3;
  int b = 4;

  cout << Sum(a,b);
}
```
만약 위 실행코드를 실행시키면 컴파일러는 아래와 같이 코드를 변형하여 컴파일한다.
```cpp
inline int Sum(int x, int y) { return x + y }

void main()
{
  int a = 3;
  int b = 4;

  cout << 3 + 4;
}
```
예제와 같이 컴파일 되기 때문에 인라인함수는 함수 호출부분 없이 바로 계산된다.

<br> **참조 변수** <br>
참조 변수는 C++에서 제공하는 세 번째 변수 타입이다. 한 객체가 다른 객체를 연결하는 수단으로 사용한다.<br>
참조 변수의 생성 방법은 아래와 같다.
```
변수타입 & 참조 변수 이름 = 참조할 변수;
```
참조 변수를 사용할때는 아래와 같은 주의사항을 지켜야 한다.
```cpp
const int num = 10;
const int a = 1;
int & refer; // 오류 : 참조 변수는 선언과 동시에 초기화 되어야 한다.
int & refer2 = num; // 오류 : const로 선언된 변수는 const로 선언하여 참조해야 한다.
int& refer3 = NULL; // 오류 : null값을 참조할 수 없다.
refer4 = a; // 오류 : 한번 참조한 변수는 재참조 불가능 하다.
```
참조 변수는 함수의 매개변수로 활용하여 원본 데이터의 수정을 가능하게 할수 있다.<br>
아래는 예시이다.
```cpp
void swap(int& a, int& b)
{
  int temp = a;
  a = b;
  b = temp;
}
void main()
{
  int x = 1;
  int y = 2;

  cout << "x : " << x << " , y : " << y << endl;
  swap(x,y);
  cout << "x : " << x << " , y : " << y << endl;
}
```
코드를 실행시켜 보면 아래와 같이 원본이 변경되 있는걸 확인할수 있다.
```
x : 1 , y : 2
x : 2 , y : 1
```
또한 컴파일러는 내부적으로 참조 변수를 사용할때 포인터를 이용하여 접근한다.<br>
```
int num = 5;
int* ptr = &num;
int& ref = num;

cout << *ptr << endl;
cout << ref << endl;
```
실행 결과는 아래와 같다.
```
5
5
```
따라서 *ptr 과 ref는 동일 취급된다.<br>
또한 선언 동시에 초기화 및 null로 초기화 불가하고 참조할수 없음으로 포인터보다 안전하게 취급받는다.<br>

<br> **디폴트 매개변수** <br>
디폴트 매개변수는 매개변수의 값이 기본적으로 지정되있는 값이다.<br>
즉 매개변수를 2개를 받는 함수에 1개의 값만 입력해도 나머지 한개의 값이 디폴트 매개변수이면 작동한다는 소리이다.<br>
아래는 예시이다.
```cpp
void Sample(int x, int y = 3);

void main()
{
  cout << Sample(2);
}

void Sample(int x, int y)
{
  return (x + y);
}
```
만약 위 코드를 실행시키면 아래와 같은 결과값이 출력된다.
```
5
```
디폴트 매개변수를 사용할때는 꼭 오른쪽에서 왼쪽 순서로 첨가해야한다.

<br> **함수 오버로딩** <br>
