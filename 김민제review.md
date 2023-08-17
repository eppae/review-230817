## 리뷰
제가 직접 해보기 전까지는 이해가 느려서 
질문을 많이 못해보는게 너무 아쉽네요 

1. 프로젝트 초기 설정

### 로컬에서 처음 시작하기
```bash
git init
```

### 원격 저장소 프로젝트로 시작하기
```bash
git clone [url]
```


> git init 확인은 커맨드창 `(main)` 으로 확인 가능

2. 버전 기록할 때 
```bash
git add
git commit -m '커밋메세지'
```

- git status로 파일 상태 확인 해보기
```bash
git log 
git log --oneline -10
```
- 원격 저장소 최초 설정할떄
```bash
git remote add origin [url]
```
## 원격 저장소 활용

### push
```bash
git pull origin main
```

- `origin` : 원격저장소의 이름

- `main` : 브랜치의 이름

## 브랜치 활용
```bash
git branch # 브랜치 목록
git branch 브랜치이름 # 브랜치 생성
git checkout 브랜치이름 #브랜치 이동
git branch -d 브랜치이름 # 브랜치 삭제
```

```bash
git merge 브랜치이름
```

- github.io 라는 repository 만들고 그안에 html이나 css를 넣어놓으면 실행

- **clone**
repository 복제

**clone 으로 복제해서 작업하지 않고 zip으로 받을 경우 .git이 없어서 log가 생성되어있지 않다. -> 즉 커밋을 바로 할 수 없다.**

3. pull push
- 원격저장소에 push
```bash
git push [원격저장소] [브랜치]
```

- 원격저장소부터 pull
```bash
git pull [원격저장소] [브랜치]
```

4. .gitignore
> 별도로 git으로 관리하고싶지 않은 파일,디렉토리를 여기에 입력
경로, 혹은 파일등이 git.log 에 보이지 않게 된다.

```python
/__cache__
*.exe
```

5. `merge`

두 branch를 합칠 때 
-main이 되는 branch에서
-git merge [합쳐지는 branch] 


- merge 시에 merge commit 발생
- 같은 파일 동시 수정시 merge할때 충돌 발생
> 이 경우 합치는 주 파일(main) 에서 원하는 방식으로 수정하고 merge -> add -> commit

## 기타 명령어

### git add를 취소
```bash
git reset [file]    ##해당경로의 파일을 언스테이징
git reset HEAD  ##전체 파일 언스테이징
```
### 커밋 메시지를 변경
```bash
git commit --amend
git push origin <branch-name> --force   #이미 원격 저장소에 푸시했을 경우 --force 옵션 사용 
```
### 커밋을 취소 

```bash
git reset --soft HEAD^  #가장 최근의 커밋만 취소
git reset --hard HEAD^  #커밋 취소 + 스테이징 영역 변경 사항까지 취소 
```