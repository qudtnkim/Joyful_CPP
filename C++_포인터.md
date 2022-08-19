####### *날짜  2022-08-16 12:55*

태그: #개발 #컴퓨터언어 #CPP #참조 #포인터 #메모리관리

### 9. 참조, 포인터, 메모리 관리
---

- #포인터 자료형은 메모리 위치의 주소를 나타내는 복합 자료형임. 
- ==포인터 변수는 포인터 자료를 갖는 변수이다.==

1KB 의 메모리가 있는 컴퓨터의 바이트는 0x000 부터 0x3ff 까지 표현할 수 있음.

f x 1 + f x 16 + 3 x 16^2

15 + 15 x 16 + 3 x 256 =1,023 임

|저장될 값|0x000|
|----|----|
|저장될 값|0x001|
|저장될 값|0x002|
|저장될 값|0x003|
|저장될 값|...|
|저장될 값|...|
|저장될 값|...|
|저장될 값|...|
|저장될 값|...|
|저장될 값|0x3ff|

1KB 메모리의 주소 할당 구조는 위와 같음

- ==변수의 주소는 변수가 차지하는 첫 번재 바이트의 주소를 의미한다.==
- ==변수의 주소를 추출하려면 주소 연산자(&)를 사용한다.==

- 포인터 자료형과 포인터 변수
포인터 자료형은 리터럴의 값이 주소인 복합 자료형이다. 
> char 포인터 (char 변수의 주소)
> int 포인터 (int 변수의 주소)
> double 포인터 (double 변수의 주소)

bool* //bool에 대한 포인터
int* //int에 대한 포인터
double# //double에 대한 포인터
Circle* //Circle에 대한 포인터

>// 포인터 변수를 초기화할 때는 기존의 있는 변수의 주소로 초기화함.
>bool* pFlag = &flag; // pFlag 를 flag의 주소로 초기화
>int* pScore = &score; //pScore 를 score의 주소로 초기화
>double* pAverage = &average; //pAverage를 average의 주소로 초기화

- ==주소 연산자 & 는 변수를 받아 주소를 반환
- ==간접 참조 연산자(asterisk)는 주소를 받아 값을 반환==\

변수 -> & -> 주소 -> \* -> 값

>//값 추출 직접 참조와 간접 참조
>#include \<iostream\>
>using namespace std;
>int main()
>{
>	int score = 92;
>	int* pScore = &score; // score 변수의 주소를 포인터 자료형에 할당
>	cout << "직접 참조 score" << score <<endl;
>	cout << "간접 참조 score" << \*pScore;
>	return 0;	 
>}


## const 한정자
|경우|데이터 변수|포인터변수|
|-----|-----|-----|
|1|int name = value;|int* pName = &name;|
|2|int name = value;|const int* pName = &name;|
|3|const int name = value;|const int* pName=&name;

case1: 데이터 변수 포인터 변수 (직참 간참)모두 값 변경 가능
case2: 데이터 변수의 값변경은 가능하지만, 포인터 변수로 값의 변경이 불가능함
case3: 둘 다 값변경 불가함. 거의 안 씀.

![[Pasted image 20220818140214.png]]


#passbyvalue #passbyreference #passbypointer
# passbypointer
[[C++_참조]]


![[Pasted image 20220818142513.png]]

참조로 전달은 메모리 위치를 공유하고,
포인터로 전달은 포인터를 복사하여 (4바이트 사용), 값으로 전달과 다르게 #복사비용 이 크지 않음.



- 배열과 포인터
|arr|10|\[0\]|
|---|---|---|
|---|11|\[1\]|
|---|12|\[2\]|
|---|13|\[3\]|
|---|14|\[4\]|

arr 을 그냥 반환하면 arr배열의 0번째 인덱스 요소의 주소를 반환함.

이는 다음과 같은 연산이 이루어짐을 뜻함
> #include \<iostream\>
> using namespace std;
> int main()
> {
> 	int numbers[5] = {10, 11, 12, 13, 14};
> 	cout<<"인덱스로 접근"<<endl;
> 	for (int i = 0 ; i <5 ; i++){
> 		cout<<numbers[i]<< "   "
> 	}
> 	cout << endl;
> 	cout<<"포인터로 접근"<<endl;
> 	for (int i =0; i<5; i++)
> 	{
> 		cout << \*(numbers +i)<<"   ";
> 	}
> }
> //numbers는 주소이고 주소 앞에 포인터 연산자 \* 를 삽입하면 주소가 가지고 있는 값에 접근 할 수 있음. 
> //배열의 형태로 선언된 numbers 메모리 이므로 첫번째 주소에 다음 바이트에 접근하면 배열의 인덱스를 순서대로 출력하게 되는 것임.

## 간접참조
포인터 변수를 선언한 후에, 포인터 변수에 저장된 주소를 활용해서 포인트된 변수의 값에 접근할 수 있으므로 asterisk 기호를 붙여서 주소에 저장된 값을 불러온다.
#indirection_operation




 






### 출처(참고문헌)
- 포르잔 c++ 바이블


### 연결문서

[[객체 지향 프로그래밍]]
[[C++_참조]]
[[메모리]]

