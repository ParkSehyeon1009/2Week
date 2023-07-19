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

# 함수 - C++의 프로그래밍 모듈
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
