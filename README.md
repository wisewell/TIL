# Today I Learned

> 매일매일 배운 것을 기록합니다.

## 2022-09-13

### RPA 1기, 웹프로그래밍 기획과 기본

#### 리눅스 커맨드라인 기초

- `pwd` : print working directory의 약자로 현재 작업 경로를 출력해주는 명령어
- `cd` : change directory의 약자로 현재 작업 경로를 변경할 때 쓰는 명령어
  - 절대 경로는 `/`로 시작함
  - 상위 경로는 `..`으로 나타냄
- `ls` : list의 약자로 현재 작업 경로에 있는 파일이나 디렉터리를 출력해주는 명령어
  - `ls -a`, `ls -l`, `ls -al`과 같은 옵션을 붙일 수 있음
- `history` : 과거에 쳤던 명령어 리스트를 보여줌
  - 123번째 명령어를 복구하고 싶으면 `!123` 입력

#### vim 사용법

- 명령 모드 (`Esc`로 진입)
  - vim 에디터를 열 때는 명령 모드로 진입함
  - 명령 모드에서는 입력이 불가능하다.
  - 입력을 하려면 입력 모드로 바꿔야 한다.
    - 키보드에서 `I` 누름
  - 입력이 끝나고, 저장하고 나오려면 명령 모드로 바꿔야 함
    - 키보드에서 `Esc` 누름
  - 입력 가능한 명령어
    - `:w` (write) : 저장하기
    - `:q` (quit) : 나오기
    - `:wq` (write & quit) : 저장하고 나오기
  - 참고자료 [링크](https://zeddios.tistory.com/122)
- 입력 모드 (`I`로 진입)

- 비정상적으로 종료시 해결 방법
  - vim이 비정상 종료되었을 때 `swp` 파일이 생성됨
    - ATTENTION 문구가 뜨는 경우
      1. 두 프로세스, 두 사람이 동시에 한 파일을 수정하는 경우
      2. crash가 나서 vim이 비정상적으로 닫힌 경우
  - 기존에 입력했던 내용을 복구하고 싶을 때는 `vim -r 파일명`을 입력하거나 Recovery 모드로 진입
  - 정상 종료 후 swp 파일 삭제
    - `rm .789.txt.swp` <-- `rm` 명령어는 remove 약자

#### 마크다운 문법

- 외부 링크 추가

```
사용문법 : [Title](link)
적용예 : [Google](https://google.com, "google link")
```

Link : [Google](https://google.com, "google link")

#### 코드 인용법

```js
const abc = 123;
```

#### 버전 관리 시스템과 git

##### 버전 관리 시스템을 사용하는 이유

1. 실행 취소, 재실행이 가능함
2. 버전간 소스코드 비교가 가능함
3. 협업이 쉬워짐

##### 다양한 버전 관리 방법

이름 변경하기 등의 방법이 있는데, 개발할 때는 git을 주로 사용함

##### 커밋

- 커밋은 논리적 변경이 있을 때 만듦
- 가능하면 커밋 크기가 작을수록 좋음

##### 커밋 이력 보기

```
git log
```

##### 리포지토리

- 정의 : 여러 파일을 하나로 모은 컬렉션

## 2022-09-20

### RPA 1기, 웹프로그래밍 기획과 기본

#### Repository 리포지토리

- 정의 : 여러 파일을 하나로 모은 컬렉션
- 일반 디렉터리와 리포지토리의 차이 : `.git` 디렉터리 유무

#### Repository로 만들기

`git init` (git initialize) : 일반 폴더 → 저장소로 만들기 (.git 숨김폴더 생성됨)

#### Repository 취소

`rm -rf .git` (Remove -Recursive -Force .git) : 저장소로 만든 것 취소 (.git 숨김폴더 삭제)

#### 저장소 상태 파악하기

```
git status
```

#### Git 체크아웃

`git checkout commitID` : 저장소 버전 되돌리기 (+ Git Graph 함께 활용하면 편하게 확인 가능)

이후 `git checkout master`로 처음 상태로 돌아가기

#### Commit 수정

`git rebase -i HEAD~1` : 1개의 최신 커밋을 수정 (edit)

#### 스테이징 영역에 올리기

`git add FileName` : 작업 파일을 스테이징 영역에 추가

#### 스테이징 영역에서 내리기

`git reset FileName` : 파일을 스테이징 영역에서 삭제 (Commit을 작성할 때 포함시키지 않는다.)

#### Commit 작성

`git commit -m "Commit Message"` : Commit 작성

#### Commit 업로드

`git push -u origin main` : 작성한 local branch commits 업로드

#### 브랜치

- 정의 : A branch in Git is simply a lightweight movable pointer to one of these commits.
- 브랜치는 특정한 목표를 가지고 코드를 수정할 때 주로 만듦
  - 이슈 하나당 브랜치 하나를 주로 만듦

#### Git Branch 명령어

1. 브랜치 목록 보기

```
git branch
```

: 현재 생성된 브랜치 확인

2. 브랜치 생성하기

```
git branch BranchName
```

: 브랜치 생성

3. 특정 브랜치로 전환하기

```
git checkout BranchName
git switch BranchName
```

: 작업 브랜치 변경

4. 브랜치 생성과 체크아웃 동시에 하기

```
git checkout -b BranchName
```

: 브랜치 생성 후 바로 작업 브랜치로 지정 (checkout, switch)

#### Branch 병합

먼저 최종적으로 병합할 브랜치로 전환한다.

```
git merge BranchName
```

선택한 브랜치를 가져와 합친다.

## 2022-09-27

### RPA 1기, 웹프로그래밍 기획과 기본

#### Branch 병합시 충돌(conflict) 해결법

1. `git status`
2. vim, Visual Studio Code 등의 에디터로 충돌 부분 직접 수정
3. 수정사항 저장
4. `git add FileName`
5. `git commit` (Merge 기본 메세지가 있으므로 따로 작성할 필요 없음)
6. `git log`로 커밋 이력을 출력하여 병합이 제대로 이루어졌는지 확인

#### Git Branch를 활용한 작업 순서도

1. master/main 브랜치로 전환

```
git checkout main
git switch main
```

2. 원격 저장소의 master/main 브랜치에서 내려받기 (동기화)

```
git pull origin main
```

3. 작업 브랜치 생성

```
git branch BranchName
```

4. 작업 브랜치 변경

```
git checkout BranchName
git switch BranchName
```

5. 소스 코드 수정 후 저장

6. 수정한 파일을 스테이징 영역에 올리기

```
git add FileName
```

7. commit 만들기

```
git commit -m "Commit Message"
```

8. 원격 저장소에 브랜치 생성하고 동기화

```
git push -u origin BranchName
```

9. GitHub 사이트에서 Pull Request 생성

- New pull request
- 병합 방향 설정
- Create pull request
- ...
- 검토 후 Merge

## 2022-10-04

### RPA 1기, 웹프로그래밍 기획과 기본

#### GitHub 오픈소스 프로젝트 클론 코딩

1. GitHub 오픈소스 프로젝트 로컬에 복제하기

```
git clone URL
```

2. 새로운 리포지토리 만들기

3. 프로젝트를 복제한 로컬 저장소와 기존 원격 저장소의 연결 끊기

`git remote` 로 origin 확인.
있다면 기존 원격 저장소와의 연결을 끊어야 한다.

```
git remote remove origin
```

4. origin 삭제 확인

```
git remote
git remote -v
```

5. 로컬 저장소와 나의 원격 저장소를 연결

```
git remote add origin URL
```

6. origin 추가 확인

```
git remote
git remote -v
```

7. (필요시) master 브랜치명을 main으로 변경

```
git branch -M main
```

8. 프로젝트를 (로컬 저장소에서) 원격 저장소에 업로드

```
git push -u origin main
```

#### NPM 설치 및 확인

1. Node.js 설치

2. 터미널에서 설치 여부 및 버전 확인

```
node -v
npm -v
```

3. npm 설치

```
npm install
```

4. 로컬 서버 실행

```
npm run serve
```

## 2022-10-11

### RPA 1기, 웹프로그래밍 기획과 기본

#### Git의 인증 방법

- ID/PW 방식
- 키 방식 (공개키/개인키)
- 토큰 방식 (personal access token)

#### 지금까지 배운 명령어 개념과 함께 복습

- git commit, git branch, git checkout, git checkout -b, git merge, git pull, git push
- 참고 사이트 : https://violet-bora-lee.github.io/git-tutorial/

#### git merge 방식

1. 3-way
2. fast-forward

#### git push시 내부에서 일어나는 일

- (현재 main 브랜치를 체크아웃하고 있다는 가정하에) `git push origin main`을 입력하면 로컬 저장소에 있는 main 브랜치에 있는 모든 커밋이 원격 저장소(origin)에 있는 main 브랜치로 병합되는데, 이때 방식이 fast-forward임.

#### git push가 reject(거절)된 경우 해결법

1. 먼저 `git pull` 해서 원격 저장소의 특정 브랜치에 있는 커밋들을 다 로컬 저장소의 특정 브랜치로 반영한 다음 push하면 리젝트 해결
2. 강제 옵션(--force) 사용해 push

```
git push -f origin main
git push --force origin main
```

※ git push → push가 정상 동작하는 경우에는 내부에서 fast-forward 방식으로 두 브랜치가 싱크가 맞춰진다.

#### Commit Message 변경

```
git commit --amend
```

커밋 메세지 수정 후 `Esc` - `:wq`

#### git reset

`git reset --hard HEAD^` : HEAD 바로 앞의 커밋 삭제(정확히는 HEAD 브랜치가 가리키는 커밋을 바꾼다.), 스테이징 영역에서 내리기, 변경내역 되돌리기

`git reset --mixed HEAD^` : HEAD 바로 앞의 커밋 삭제(정확히는 HEAD 브랜치가 가리키는 커밋을 바꾼다.), 스테이징 영역에서 내리기 (기본 옵션으로 `git reset HEAD^`와 같다.)

`git reset --soft HEAD^` : HEAD 바로 앞의 커밋 삭제(정확히는 HEAD 브랜치가 가리키는 커밋을 바꾼다.)

#### git reset한 커밋 복구

1. commit log 확인

```
git reflog
```

2. 복구할 내역 선택해 되돌아가기

```
git reset --hard commitHash
```

#### git cherry-pick

다른 브랜치에 있는 커밋을 선택적으로 체크아웃한 브랜치에 적용

```
git cherry-pick commitHash
git cherry-pick commitHash1 commitHash2
git cherry-pick commitHash1..commitHash3
```

revert 테스트
