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
<br>
   
### git 명령어   
+ `git status`: 파일의 상태 확인하기   
+ `git reset` + `파일이름`: staging area에 올렸던 파일 다시 내리기(레퍼지토리의 커밋 내용을 staging area 로 가져오기) 
+ `git log`: 커밋 히스토리 출력, 자주쓰이는 옵션 `--pretty=oneline`: 커밋 히스토리 한줄로 출력   
+ `git show` + `커밋id` or `태그 name` : 커밋의 변경사항 출력
+ `git commit --amend`: 최신 커밋을 수정하여 새 커밋으로 만듦
+ `git config alias` + `별명` `커맨드`: 명칭을 입력하면 명령어를 실행하게 함
+ `git diff` + `커밋id 커밋id`: 두 커밋 사이의 변화 출력
+ `git reset` + `--hard` or `--mixed` or `--soft` + `커밋id` or `HEADcommand`: 지정한 커밋id를 브랜치가 가리키게 하며 working directory도 HEAD가 가리키는 커밋으로 재구성, 뒤에 HEADcommand를 사용해서 커밋을 지정 가능 HEADcommand는 `HEAD^`, `HEAD~`+숫자 로 사용하며 `HEAD^`는 바로 이전 커밋, `HEAD~` + 숫자는 숫자만큼 전에 있는 커밋을 나타냄   
  > reset의 옵션 세가지    
  > ![image](https://github.com/chlangus/frontend-note/assets/139041897/8debdd5d-d39f-42dc-9cfb-92736fc7e757)   
+ `git tag` + `태그name` + `커밋id`: 커밋id에 태그를 달아줌
+ `git branch` + `[option]` + `[브랜치name]`:   
  +  `git branch`만 사용할 경우 브랜치 목록 출력   
  +  `git branch` + `[브랜치name]`을 사용할 경우 새로운 브랜치를 생성   
  +  `option`에 `-d`를 사용하면 그 브랜치 삭제 
+ `git checkout` + `[option]` + `브랜치name` or `커밋Id`: HEAD가 브랜치나 커밋id를 직접 가르키게 함   
  +  `-b` 옵션을 사용 할 경우 브랜치를 생성 후 바로 이동   
+ `git merge` + `브랜치name`: 현재 위치의 브랜치에 대상 브랜치 합치기   
  +  브랜치끼리 conflict가 발생 시 파일로 가서 수정할 내용을 고친 후 커밋
  +  confilct가 발생 시 merge하기 전 상태로 돌아오려면 `git merge` + `--abort` 커맨드 실행
+ `git push origin master:premium`: 리모트 레포지토리인 origin의 master브랜치에 local의 premium 브랜치의 내용을 push
+ `git pull`: 리모트 레퍼지토리의 내용을 가져와 자동으로 merge를 해줌, 리모트 레포지토리의 브랜치를 검토 없이 바로 합치고 싶을 때
+ `git fetch`: 리모트 레퍼지토리의 내용을 가져와 확인 하거나, 자신의 코드를 비교해서 검토 해야 할 때 필요 가져온내용은 show나 diff로 확인 가능   
+ `git blame` + `파일이름`: 어떤 파일의 특정 코드를 누가 작성했는지 찾아내기 위한 커맨드
+ `git revert` + `커밋id`: 커밋한 내용을 취소하기위해 사용 
  + `git revert` + `커밋id..커밋id`: 앞의 커밋id 이후의 커밋부터 뒤의 커밋id까지의 작업을 취소
+ `git reflog`: 헤드가 이때까지 가리켜 왔던 로그를 출력
+ `git rebase` + `커밋id`: 베이스 브랜치에 대상 브랜치의 현재까지 커밋사항들을 합침, 히스토리를 깔끔하게 만들기 위해 사용
+ `git stash`: stack에 작업물을 저장하는 커맨
  + `git stash` + `list`: stack에 저장된 작업물들을 확인
  + `git stash` + `apply` + `[stashid]`: stack에 저장된 작업물들을 다시 working directory로 가져와서 적용
  + `git stash` + `drop` + `[stashid]`: stack에 저장된 작업물을 삭제
  + `git stash` + `pop` + `[stashid]`: apply와 drop을 한번에 해주는 명령어
+ `git cherry-pick` + `[커밋id]`: 가져오고 싶은 커밋 id를 가져와 base branch에 적용 
<br>   
   
