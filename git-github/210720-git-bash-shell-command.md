##Git bash shell 명령어 정리(Window ver)

###ls

 list segment의 약어 파일/폴더 등을 보여준다.

  \*ls -l – line by line으로 수정시간까지 보여준다.
  
  \*ls -a – 숨김 파일까지 포함하여 모든 파일을 보여준다.

###cd

 change directory의 약어 위치를 이동하는데 쓰인다.

###mkdir
 
 make directory의 약어 directory를 생성하는데 쓰인다.

###touch 
 
 파일을 생성하는데 쓰인다.

###mv

 파일을 이동시키는데 쓰인다. / 파일의 이름을 바꿀 때도 쓰인다.

###cp 

 파일을 복사하는데 쓰인다.

###rm 

 파일을 삭제하는데 쓰인다.
 
 \*rm -rf – directory를 삭제한다 directory는 물리적인 개념이 아닌 path의 개념이라 삭제를 위해 -r을 추가한다 f는 force의 약어로 강제로 삭제한다는 의미 


##Git 환경설정 명령어

```
 $ git config --global user.name "깃허브유저네임"
 $ git config --global user.email "깃허브메일주소"
 $ git config --global core.editor "vim"
 $ git config --global core.pager "cat"
 $ git config --global init.defaultBranch "main"
```

 \* 확인은 $ git config --list
 \* 수정은 $ vi ~/.gitconfig


##Git clone 명령어

### git clone 레포지토리 주소

 github에서 repository를 로컬로 받아오는 과정

### git add 파일이름

 파일을 수정 후 stage area에 모아두는 역할 commit 하지 않는다면 최종적으로 올라가진 않는다.

### git commit 파일이름

 수정된 파일을 최종적으로 local내에 저장하는 기능을한다.
 이 때 커밋 제목을 쓰게되는데 prefix를 유의하도록 한다.
  \+feat: 기능개발
  \+docs: 문서
  \+fix: 버그등의 수정
  \+test, refactor, ci, build, perf등이 존재

### git push origin branch이름

 해당 branch의 변경사항을 github에 저장하는 역할을 한다.
 main branch가 아닐 경우 origin 앞에 -u를 붙인다.
 

