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

#### 마크다운 문법
- 외부 링크 추가
```
사용문법 : [Title](link)
적용예 : [Google](https://google.com, "google link")
```
Link : [Google](https://google.com, "google link")

#### 코드 인용법
``` js
const abc = 123;
````
