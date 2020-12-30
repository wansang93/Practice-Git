# 00. Basic CLI

1. `ls` : 목록 조회 (list)

   ```
   00_basic_cli.md  a.txt  b/  c.txt  d.txt  e.txt  images/  markdown.md
   ```

   `ls -al` : 상세 목록 조회

   ```
   $ ls -al
   total 20
   drwxr-xr-x 1 campusseven04 197121   0 Dec 29 15:05 ./
   drwxr-xr-x 1 campusseven04 197121   0 Dec 29 13:30 ../
   drwxr-xr-x 1 campusseven04 197121   0 Dec 29 14:03 .git/
   -rw-r--r-- 1 campusseven04 197121   0 Dec 29 15:05 00_basic_cli.md
   -rw-r--r-- 1 campusseven04 197121   0 Dec 29 11:26 a.txt
   drwxr-xr-x 1 campusseven04 197121   0 Dec 29 11:31 b/
   -rw-r--r-- 1 campusseven04 197121   0 Dec 29 11:33 c.txt
   -rw-r--r-- 1 campusseven04 197121   0 Dec 29 13:43 d.txt
   -rw-r--r-- 1 campusseven04 197121   0 Dec 29 13:43 e.txt
   drwxr-xr-x 1 campusseven04 197121   0 Dec 29 14:37 images/
   -rw-r--r-- 1 campusseven04 197121 854 Dec 29 15:04 markdown.md
   ```

2. `cd` : 폴더 변경 (change directory)
   1. `cd` : `~` 폴더(home 폴더)로 이동
   2. `cd 폴더명` : `폴더명`으로 이동
      1. `cd 폴더명/폴더명/폴더명` : 여러개의 폴더 한번에 이동
   3. `cd ..` : 상위 폴더로 이동

3. `mkdir` : 폴더 생성 (make directory)
   1. `mkdir A` : `A`이라는 이름의 폴더를 생성

4. `touch` : 파일 생성
   1. `touch A.txt` : `A.txt` 파일을 생성 (빈 파일)
5. `cp` : 파일/폴더 복사
   1. `cp A B` : `A`라는 파일/폴더를 복사하여 `B`를 생성
6. `mv` : 파일/폴더 이동
   1. `mv A.txt B/A.txt` : `A.txt` 파일을 `B` 폴더 안으로 이동
   2. `mv A.txt C.txt` : `A.txt` 파일의 이름을 `C.txt`로 변경

7. Tab : 자동완성
8. 방향키 위, 아래 : 명령어 기록 (History)

# 01. Git

- `git status` : git으로 관리 되고 있는 폴더(== Repository, 저장소)의 상태를 보여줌
- `git init` : 현재 폴더를 git으로 관리하겠다 선언! (초기화)
- `git add` : git으로 관리할 파일들을 추가!
  - `git add A.txt` : `A.txt` 파일을 INDEX(Stating 영역)에 등록 (폴더도 가능)
  - `git add .` : 현재 폴더(`.`)를 INDEX에 등록. 폴더를 등록하면 내부의 모든 파일이 등록됨.
- `git commit` : INDEX에 있는 파일들을 가지고 commit(history, 역사, 기록)을 남김!
  - `git commit -m '메세지'` : 기록을 남기면서, `메세지`를 남김! (필수)
- `git log` : 남겨온 commit들을 확인
  - `git log --oneline --graph` : 그래프 + 한줄로 기록을 조회

- `git config` : git 프로그램의 설정을 담당

  ```bash
  git config --global user.email '이메일'
  git config --global user.name '이름'
  ```

  - `git config --global --list` : 현재 git 프로그램에 설정된 값들을 확인.

# 02. Markdown

```
# heading 1 입니다.

## heading 2 입니다.

### heading 3

#### heading 4

##### heading 5

###### heading 6

- 리스트입니다.
- 순서가 없는 리스트입니다.

1. 순서가 있는 리스트입니다.
2. 2번
3. 3번

코드 블럭 backtic 3개
```

```bash
git add a.txt
git commit -m 'first commit'
```

```python
def hello():
    return 'hello'
```

```
![bono](images/bono.jpg)

[구글](https://google.com)

| 제목        | 내용        | 참고 |
| ----------- | ----------- | ---- |
| 반갑습니다. | 안녕하세요. |      |
|             |             |      |
|             |             |      |

- *기울임체*
- **굵게**
- ***기울이면서 굵게***
- ~~취소선~~
- `인라인 코드 블럭`
  - `git`
    - `commit`

---
```

# 03. Git Remote

- `git remote` : Remote Repository 주소 등록 (여기서는 GitHub Repo)

  - `git remote add origin (주소)` : Remote Repo의 `주소`를 origin이라는 별칭으로 등록

  - `git remote -v` : 등록된 Remote 주소 확인

    ```bash
    origin  https://github.com/nwith/TIL.git (fetch)
    origin  https://github.com/nwith/TIL.git (push)
    ```

- `git push (별칭) (브랜치이름)` : `별칭`으로 `브랜치`를 push (올리기)

  - `git push origin main` : origin으로 main 브랜치를 전송

- `git clone (주소)` : 주소로부터 Repo 가져오기
- `git pull (별칭) (브랜치이름)` : `별칭`으로부터 `브랜치`를 pull (내려받기)

# 04. Push Error

### Pull을 빠뜨린 경우

- e를 commit 합니다.

- 그리고, push

  ```bash
  $ git push origin main
  To https://github.com/nwith/TIL-test.git
   ! [rejected]        main -> main (fetch first)
  error: failed to push some refs to 'https://github.com/nwith/TIL-test.git'
  # push 실패
  hint: Updates were rejected because the remote contains work that you do
  # 업데이트가 실패했는데, remote에는 니가 local에 가지고 있지 않은 작업을 들고 있다.
  hint: not have locally. This is usually caused by another repository pushing
  # 지금 같은 경우는 다른 Repo로 push 하려고 시도한 것이거나
  hint: to the same ref. You may want to first integrate the remote changes
  # push를 다시 하기전에 remote에서 발생한 변경 사항을 먼저 통합(반영)을 해야 할 수 있다.
  hint: (e.g., 'git pull ...') before pushing again.
  hint: See the 'Note about fast-forwards' in 'git push --help' for details.
  ```

- `git pull origin main`

  ```bash
  Merge branch 'main' of https://github.com/nwith/TIL-test # <- 이미 메세지가 작성되어 있다.
  # Please enter a commit message to explain why this merge is necessary,
  # especially if it merges an updated upstream into a topic branch.
  #
  # Lines starting with '#' will be ignored, and an empty message aborts
  # the commit.
  ```

  - vim : 에디터
    - esc
    - :
    - w (write, 저장)
    - q (quit, 종료)
  - enter

  ```bash
  $ git pull origin main
  From https://github.com/nwith/TIL-test
   * branch            main       -> FETCH_HEAD
  Merge made by the 'recursive' strategy.
  # Merge가 만들어 졌다.
   d.txt | 0
   1 file changed, 0 insertions(+), 0 deletions(-)
   create mode 100644 d.txt
  ```

# 05. 취소하기

1. git add 취소하기

   ```bash
   $ git status
   On branch main
   Changes to be committed:
     (use "git restore --staged <file>..." to unstage)
           new file:   f.txt
   
   ```

   ```bash
   $ git restore --staged f.txt
   ```

   - 구버전

     ```bash
     $ git reset HEAD f.txt
     ```

   ```bash
   $ git status
   On branch main
   Untracked files:
     (use "git add <file>..." to include in what will be committed)
           f.txt
   
   nothing added to commit but untracked files present (use "git add" to track)
   
   ```

2. git commit 취소 (되돌아가기)

   ```
   $ git reset (--mixed) [돌아갈 commit의 hash]
   ```

   ```
   $ git reset 0935e32
   ```

   - 옵션

     ```
     $ git reset --mixed [hash]
     ```

     - staging 없앰 + **작업한 것은 남아있음**.
     - 아무것도 입력 안하면 이 친구 사용!

     ```
     $ git reset --soft [hash]
     ```

     - staging 그대로 유지 + **작업한 것 남아있음.**

     ```
     $ git reset --hard [hash]
     ```

     - **[주의]** 완전히 취소하는 것 (작업한 것도 삭제!)

   - hash

     - ```
       git reset 0935e3213cad77483cc39015d22d1dce82835f3b
       ```

   - HEAD의 상대적 위치

     - HEAD~{숫자}
       - HEAD~1 (`HEAD~`)
       - HEAD~2

     ```bash
     $ git reset HEAD~
     ```

     - commit 되돌리기
       - HEAD~1 (1단계 전으로 되돌리고)
       - `--mixed`: staging은 취소, 작업 내용은 유지

   - git log시 내용이 너무 많이 잘리는 경우
     - q로 종료
     - 방향키로 위아래 왔다갔다 할 수 있음

3. WD(Working Directory) 변경 내용 취소(삭제)하기, 원상 복구

   - WD
     - 지금 우리가 작업 중인 공간
     - == Git이 관리하고 있는 공간
     - == 기록이 한번이라도 기록된 파일들이 있는 공간

   ```bash
   $ git restore [파일명]
   $ git restore a.txt
   ```

   - 구버전

     ```bash
     $ git checkout -- [파일명]
     ```

# 06. gitignore

- 우리가 git으로 관리하고 싶지 않은 파일들을 제외 시키는 방법

  - 우리가 원하지 않는 파일을 제외
  - 외부에 공개되면 안되는 것들 (key, secret)

- `.gitignore`

  - `.gitignore`에 작성된 파일들은 git으로 관리하지 않겠다! 무시해라!

  ```
  .DS_Store # Mac OS에서만 사용하는 파일
  ```

- 작성법

  ```
  f.txt # 특정 파일
  secret/ # 특정 폴더, 그 안에 있는 것들도 다 제외
  *.png # 특정 확장자 / 모든 png는 빼고,
  !profile.png # profile.png만 넣고!
  ```

- 처음부터, git으로 관리한 적이 없을때 부터 관리를 해줘야 함!

- 그렇다면 이미 commit을 한 파일들은 어떻게 제외할 수 있을까?

  1. `.gitignore` 에다가 파일 명시

  2. `git rm --cached [파일명]`

     - git에서 더 이상 관리하지 않겠다!

     - WD에서 삭제해서 더 이상 관리하지 않겠다!

- `.DS_Store` : Mac OS
- `Thumbs.db` : Windows

# 07. Branch

- branch : 가지 -> 가지치기
- `git branch` : 브랜치 목록 확인
- `git branch login` : `login` 브랜치 생성

- `git switch login` : `login` 브랜치로 이동

  ```
  $ git switch login
  Switched to branch 'login'
  ```

- `git log --oneline --graph --all` 
  - 한줄로, 그래프 포함, 브랜치 전부
- `git switch -c login` : 브랜치 만들면서 바로 이동
  - `git branch login` + `git switch login`

- 구버전
  - `git checkout login` : 이동
  - `git checkout -b login` : 생성하면서 바로 이동

# 08. Merge Branch

![branch](images/branch.jpg)

- 병합
  - `git merge {브랜치이름}`

1. Fast-Forward

   ![fast-forward](images/fast-forward.jpg)

   ```
   (main) $ git switch -c login
   (login) $ touch login.txt
   (login) $ git add, git commit
   (login) $ git switch main
   (main) $ git merge login
   ```

   ```
   $ git log --oneline --graph --all
   * 3620487 (HEAD -> main, login) login 추가
   * 98712c2 b 추가
   * 21006da a 추가
   ```

2. 3-Way Merge

   ![3-way](images/3-way.jpg)

3. Merge Conflict

   ![merge-conflict](images/merge-conflict.jpg)

   ```bash
   campusseven04@DESKTOP-KTJ1O7B MINGW64 ~/git-merge (main)
   $ git merge signup
   CONFLICT (add/add): Merge conflict in README.md
   Auto-merging README.md
   Automatic merge failed; fix conflicts and then commit the result.
   
   campusseven04@DESKTOP-KTJ1O7B MINGW64 ~/git-merge (main|MERGING)
   $
   ```

   ```bash
   campusseven04@DESKTOP-KTJ1O7B MINGW64 ~/git-merge (main|MERGING)
   $ git status
   On branch main
   You have unmerged paths.
     (fix conflicts and run "git commit")
     (use "git merge --abort" to abort the merge)
   
   Unmerged paths:
     (use "git add <file>..." to mark resolution)
           both added:      README.md
   
   no changes added to commit (use "git add" and/or "git commit -a")
   
   campusseven04@DESKTOP-KTJ1O7B MINGW64 ~/git-merge (main|MERGING)
   $
   
   ```

   ```bash
   campusseven04@DESKTOP-KTJ1O7B MINGW64 ~/git-merge (main|MERGING)
   $ git commit -m '합의함!'
   [main a202512] 합의함!
   
   campusseven04@DESKTOP-KTJ1O7B MINGW64 ~/git-merge (main)
   $
   
   ```

# [실습] Fork & PR

1. Fork
2. git clone
   - 제 것을 clone 받으시면 안됩니다!
   - Fork를 통해 생성된 여러분의 Repo를 clone 받아주세요!
3. `본인의 이름.md`로 파일을 만들어서 간단한 후기를 남겨주세요.
   - 정말 간단한 것이라도 좋습니다. 아무말도 좋습니다.
4. git add
5. git commit
6. git push
7. 본인의 Repo 가서, `Create PR`

- 그러면 저는 요청을 받아서 합치겠습니다.
