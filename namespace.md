[[C++_프로그래밍 기본]]
#개발 #컴퓨터언어 #CPP
![[Pasted image 20220816120644.png]]

- **namespace**
std 라는 그룹에 포함된 객체 console out의 호출을 위해서는 std 다음에 지정연산자 (::) 를 붙여야했는데, 전처리 지시자 하단에 using namespace 를 명시해 줌으로써, 해당 그룹의 객체를 스코프없이 바로 호출가능하다.

대표적인 영상처리 namespace로는 computer vision이 있다. 
> using namespace cv;

처럼 사용한다.

using 지시자를 통해 네임 스페이스에 속한 이름을 모두 가져오는 방법이 존재하고, 
>//using directive
>using namespace std;

> //using declaration
> using std::cout;

std에 속한 cout 객체 하나만 지정 연산자 없이 사용하기 위해 선언하는 방법이 존재한다.



