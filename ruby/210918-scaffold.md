## Scaffold

> rails에서 완성도 높은 CRUD 구현을 위해 사용하는 기능이다.
MVC를 각각 구현하는 것이 아니라 명령어로 더 쉽게 구현하는 방식을 제공한다.
Scaffolding은 뼈대,기반이라는 뜻을 가지고 있으며, CRUD의 뼈대를 만들어 주는 역할을 하기에 지어진 이름이라 볼 수 있다.
 
``` 
Rails new scaffold_app //프로젝트 생성
Cd scaffold_app //이동
Rails g scaffold Post title:string content:text //Post란 이름으로 title과 content를 담아 생성
Rake db:migrate // migrate 생성
```
