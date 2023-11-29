## git
+ 리눅스 운영체제를 만든 리누스 토발즈 라는 사람이 만들었음
+ git은 버전 관리 프로그램, github는 원격 저장소
+ 버전 관리, 동시 협업, 다른 컴퓨터에 보내기등 가능
<br>

### git의 영역
git의 영역은 3가지가 존재
> `working directory`, `staging area`, `repository`
>> `working directory`: 작업을 하는 프로젝트 디렉토리   
>> `staging area`: git add를 한 파일들이 존재하는 영역   
>> `repository`: working directory의 변경 이력들이 저장되어 있는 영역
>
>![image](https://github.com/chlangus/about-frontend/assets/139041897/25924ab1-1728-4e1b-b73a-095659332a4e)
<br>

### git의 상태
git으로 관리되는 파일은 일종의 `상태` 를 가짐   
일반 파일들은 `Untracked` `Tracked` 두개의 상태를 가지게 되고 `Tracked` 상태는 다시 세개의 `상태`를 가지게 됨   
> `Untracked`: 파일을 새로 생성한 뒤 한번도 git add 해 주지 않았다면 이 상태   

> `Tracked`: git add를 하고 나서 git에 의해 파일의 변동사항이 추적되고 있는 상태   
>> `Staged`: 파일을 수정하고 나서 git add를 하면 이 상태
>> `Unmodified`: 현재 파일의 내용이 최신 커밋의 내용과 차이가 없을때 그 파일은 Unmodified 상태, 커밋을 하고 난 working directory 안의 모든 파일들은 이 상태가 됨   
>> `Modified`: 최신 커밋의 내용과 비교했을때 바뀐 내용이 있다면 Modified 상태       
