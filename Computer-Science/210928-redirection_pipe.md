### 표준 입출력

> Command로 실행되는 프로세스는 세 가지 스트림을 가지고 있다.

 * 표준 입력 스트림 stdin
 * 표준 출력 스트림 stdout
 * 오류 출력 스트림 stderr


### 리다이렉션 (redirection)

> 표준 스트림 흐름을 바꿔줄 수 있다.
<, > 을 사용하여 주로 명령어 표준 출력을 화면이 아닌 파일에 쓸 때 사용한다.

```
Ex) 

   ls > files.txt
   Ls로 출력되는 표준 출력 스트림의 방향을 files.txt로 바꿔준다.

   Head < files.txt
   Files.txt의 파일 내용이 head 라는 파일의 처음부터 10라인까지 출력해주는 명령으로 넣어진다.

   Head < files.txt > files2.txt
   Files.txt의 파일 내용이 head로 들어가서, files.txt의 앞 10라인을 출력한다.
   Head의 출력 스트림은 다시 files2.txt로 들어간다
   Head는 files.txt 내용을 출력하지 않고, 해당 출력 내용이 다시 files2.txt에 저장된다.
  
  기존 파일에 추가는 >> 또는 <<를 사용한다.
```

### 파이프(pipe)

> 두 프로세스 사이에서 한 프로세스의 출력 스트림을 또 다른 프로세스의 입력 스트림으로 사용할 때 사용된다.

```
Ex)  ls | grep files.txt
   Ls 명령을 통한 출력 내용이 grep 명령의 입력 스트림으로 들어간다. (grep은 입력 받은 키워드를 갖는 데이터를 찾는 명령어이다.) 즉 files.txt를 포함하는 데이터를 ls로 전부 출력하는 예제이다.
```

