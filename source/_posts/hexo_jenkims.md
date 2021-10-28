CentOS7 JAVA 환경 변수 설정 하기 

 

자바 위치 확인 하기 

which java을 통해서 자바의 위치를 확인한다. 

그후 readlink -f [which javac에서 나온 경로]을 통해서 실제 위치를 확인해준다. 

 

 

vi /etc/profile을 들어간다. 

 

다음으로 가장 아래에 다음과 같은 코드를 입력한다. 

export JAVA_HOME=[자바 실 경로] 

