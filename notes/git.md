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
> `Untracked`: 파일을 새로 생성한 뒤 한번도 git add 해 주지 않은 상태   
>   
> `Tracked`: git add를 하고 나서 git에 의해 파일의 변동사항이 추적되고 있는 상태      
>> `Staged`: 파일을 새로 생성하거나 수정하고 난 후 git add를 한 상태   
>> `Unmodified`: 현재 파일의 내용이 최신 커밋의 내용과 차이가 없을때 그 파일은 Unmodified 상태, 커밋을 하고 난 working directory 안의 모든 파일들의 상태    
>> `Modified`: 최신 커밋의 내용과 비교했을때 바뀐 내용이 있다면 Modified 상태   
>
> ![image](https://github.com/chlangus/about-frontend/assets/139041897/b1609d39-5868-4bc5-a0fa-38166b4dbd0a)

### git 명령어   
+ `git status`: 파일의 상태 확인하기   
+ `git reset`: staging area에 올렸던 파일 다시 내리기   
+ `git log`: 커밋 히스토리 출력, 자주쓰이는 옵션 `--pretty=oneline`: 커밋 히스토리 한줄로 출력   
+ `git show` + `커밋id` or `태그 name` : 커밋의 변경사항 출력
+ `git commit --amend`: 최신 커밋을 수정하여 새 커밋으로 만듦
+ `git config alias` + `별명` `커맨드`: 명칭을 입력하면 명령어를 실행하게 함
+ `git diff` + `커밋id 커밋id`: 두 커밋 사이의 변화 출력
+ `git reset` + `--hard` or `--mixed` or `--soft` + `커밋id` or `HEADcommand`: 지정한 커밋id를 HEAD가 가리키게 하며 working directory도 HEAD가 가리키는 커밋으로 재구성, 뒤에 HEADcommand를 사용해서 커밋을 지정 가능 HEADcommand는 `HEAD^`, `HEAD~`+숫자 로 사용하며 `HEAD^`는 바로 이전 커밋, `HEAD~` + 숫자는 숫자만큼 전에 있는 커밋을 나타냄   
  > reset의 옵션 세가지    
  > ![image](https://github.com/chlangus/frontend-note/assets/139041897/8debdd5d-d39f-42dc-9cfb-92736fc7e757)   
+ `git tag` + `태그name` + `커밋id`: 커밋id에 태그를 달아줌
+ `git branch` + `브랜치name`: `git branch`만 사용할 경우 새 브랜치를 생성
+ 
