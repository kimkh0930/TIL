## 입출력 스트림

>네트워크에서 자료의 흐름이 물의 흐름과 같다 하여 유래되었다.
자바는 다양한 입출력 장치에 독립적으로 일관성 있는 입출력을 제공한다.

## 입출력 스트림 구분

* 대상기준 : 입력 스트림 / 출력 스트림
* 자료의 종류 : 바이트 스트림 / 문자 스트림
* 기능 : 기반 스트림 / 보조 스트림


### 입력 스트림 / 출력 스트림

#### 입력 스트림 

>대상으로부터 자료를 읽어 들이는 스트림
`FileInputStream`, `FileReader`, `BufferedInputStream`, `BufferedReader`등이 있으며
보통 이름에 **Input** 혹은 **Reader**등이 붙는다.


#### 출력 스트림 
>대상으로 자료를 출력하는 스트림
`FileOutputStream`, `FileWriter`, `BufferedOutputStream`, `BufferedWriter` 등이 있으며
보통 이름에 **Output **혹은 **Writer**등이 붙는다.


### 바이트 스트림 / 문자 스트림

#### 바이트 스트림

>동영상, 음악, 실행 파일 등의 자료를 읽고 쓰는데 사용한다.
`FileInputStream`, `BufferedInputStream`, `FileOutputStream`, `BufferedOutputStream` 등이 있으며 
보통 이름에 **Stream**이 붙는다.


#### 문자 스트림

>바이트 단위로 자료를 처리하면 문자가 깨지기 때문에 인코딩에 맞게 2바이트 이상으로 처리하는 스트림이다.
`FileReader`, `BufferedReader`, `FileWriter`, `BufferedWriter` 등이 있으며 
보통 **Reader** 혹은 **Writer**가 붙는다.


### 기반 스트림 / 보조 스트림

#### 기반 스트림

>대상에 직접 자료를 읽고 쓰는 기능을 한다.
`FileInputStream`, `FileOutputStream`, `FileReader`, `FileWriter` 등이 있으며
보통 **File**이 앞에 붙는다.

#### 보조 스트림 

>직접 읽고 쓰는 기능이 없어 기반 스트림이나 다른 보조 스트림을 생성자의 매개 변수로 포함하여 추가적인 기능을 더해주는 역할을 한다.
`BufferedInputStream`, `BufferedOutputStream`, `InputStreamReader`, `OutputStreamWriter` 등이 있다.

