# 깃허브 마스터를 꿈꾸며

2020-07-01 ~ 2020-07-17(초급 단계 완성)

먼저 강의를 가르쳐 준 유튜버 **동빈나** 님께 감사합니다.
[동빈나 유튜브 링크](https://www.youtube.com/watch?v=rhP5pseOJc0&list=PLRx0vPvlEmdD5FLIdwTM4mKBgyjv4no81)

또 종혁이에게 깃을 가르쳐 주면서 저 스스로 배울 수 있어서 좋은 기회가 되었으면 좋겠습니다.

- 참고문서
  - 지옥에서 온 문서 관리자 깃 & 깃허브 입문(고경희 지음, 이지스퍼블리싱)
  - 전문가용: [Pro GIT](https://git-scm.com/book/ko/v2) 웹 사이트
  - 초보자용: [Git 입문](https://backlog.com/git-tutorial/kr/) 웹 사이트

- 나중에 볼 영상: [생활코딩 유튜브 링크](https://www.youtube.com/playlist?list=PLuHgQVnccGMA8iwZwrGyNXCGy2LAAsTXk)

14 가지 목표를 동빈나 유튜브와 책에서 가져왔습니다.

## :zero::one: 첫번째 목표

원격 저장소에 저장되어있는 파일들을 읽어와 내 컴퓨터의 폴더 디렉토리와 연동시킵니다.  
또는 내 컴퓨터의 폴더에 있는 자료들을 원격 저장소에 올립니다.

### 1단계: 기본 설정

1. 깃 다운로드 받기

    [권장] 다운로드에 유닉스 명령어를 추가 설정 시 편하게 작업할 수 있습니다.  
    ![다운 설정](./photo/001.png)

2. 깃 설치 되었는지 확인

    명령 프롬포트에서 확인 `윈도우+R` -> `cmd` -> `git --version`

3. **깃 기본 설정하기**

    업로드 할 사람의 이름과 연락처(이메일)를 등록합니다.  
    명령 프롬포트에서 등록  `윈도우+R` -> `cmd` ->  
    `git config --global user.name wansang`  
    `git config --global user.email wansang93@naver.com`

    `git config --global --list`: git에서 설정한 global한 변수들을 봅니다.  
    `git config --global --edit`: git에서 설정한 global한 변수들을 수정합니다.

### 2단계: 원격 저장소(깃허브 사이트)와 로컬 저장소(자신의 컴퓨터 깃 폴더) 연동하기

1. 원격 저장소 만들기

2. 원격 저장소와 로컬 저장소 연동하기

    `git clone` 과 `git init` 방법이 있습니다.  
    이 두가지 방법 모두 결국 .git 폴더(숨김파일 해제시 보임) 를 만드는 작업입니다.  
    로컬 저장소에 . git 폴더가 있어야 깃을 시작할 수 있습니다.  
    .git 폴더에는 수정내용, 변경사항, 날짜, 올린사람 등등 각종 자료들이 들어있습니다.

    - **`git clone`을 할 경우와 특징**

        1. **원격 저장소에 작성해 둔 파일**들이 있을 때 `git clone`을 사용합니다.
        2. `git clone`은 원격 저장소에 있는 것을 다운로드 받아 깃폴더를 만듭니다.
        3. 다운로드와 동시에 자동으로 연동을 해주어  따로 경로 설정을 할 필요는 없습니다.
        4. 즉 다운로드 자체로만으로도 해당 폴더(로컬 저장소)와 원격 저장소가 연동이 되었습니다.

    - **`git init` 을 했을 경우와 특징**

        1. **로컬 저장소에 작성해 둔 파일**들이 있을 때`git init`명령어를 입력합니다.
        2. `git init`은 로컬 저장소에서 깃을 시작한다는 의미입니다. 해당 로컬 저장소에서 깃을 사용할 수 있게 합니다.
        3. 경로를 설정해 줍니다. 명령어는 `git remote add origin https://github.com/wansang93/Practice-Git` 입니다.
        4. 즉 해당 폴더(로컬 저장소)에서 깃 폴더를 생성하여 원격 저장소와 `git remote` 명령어를 사용해서 연동을 합니다.

[[reference] Git Commands - Getting and Creating Projects](https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Getting-and-Creating-Projects)  
[[참고자료] Git 명령어 - 프로젝트 가져오기와 생성하기](https://git-scm.com/book/ko/v2/Appendix-C%3A-Git-%EB%AA%85%EB%A0%B9%EC%96%B4-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0%EC%99%80-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0)

### 3단계: 로컬 저장소에 있는 파일을 수정해서 원격 저장소에 올리기

![깃 동작 과정](./photo/002.jpg)

- `git add .`  
- `git commit -m "first commit"`
- `git push`  

## :zero::two: 두번째 목표

로컬 저장소에 있는 파일을 원격 저장소에 올리고 내리기

### 1단계: 파일 올리기, 내리기

1. 추가, 수정, 삭제된 파일이 있는지 확인 및 깃의 현재 상태 표시

    `git status`

2. 파일을 Staging Area 로 올리기

    특정 파일 올리기 -> `git add <파일 이름>`  
    모든 파일 올리기 -> `git add .`

3. Staging Area 에 파일을 내리기

    `git reset <파일 이름>`

4. Local Repository에 파일 올리기

    `git commit -m "<작성하고 싶은 메시지>"`

    - 커밋 메시지 작성하는 방법
      - 좋은 git commit 메시지를 작성하기 위한 7가지 약속 [https://meetup.toast.com/posts/106](https://meetup.toast.com/posts/106)
      - 좋은 git commit 메시지를 위한 영어 사전 [https://blog.ull.im/engineering/2019/03/10/logs-on-git.html](https://blog.ull.im/engineering/2019/03/10/logs-on-git.html)

5. Remote Repository에 파일 올리기

    `git push`

### 2단계: 파일 수정 무시하기

1. 추가, 수정, 삭제된 파일이 있는지 확인 및 깃의 현재 상태 표시

    `git status`

2. 파일 수정 무시하기

    `git checkout -- <파일 이름>`

3. 커밋 로그 보기

    `git log`

## :zero::three: 세번째 목표

git bash 에서 리눅스 명령어 연습, vim 사용법 익히기

### 리눅스 명령어 연습하기

1. 현재 디렉터리 살펴보기

    물결 표시(~)는 홈 디렉터리(home diretory)에 있다는 의미  
    - `pwd` : 현재 경로 표시
    - `ls`:  디렉터리와 파일이름 표시, `/`가 붙어있는 것이 디렉터리
    - `-`: 옵션 추가
        - `-a`: 숨긴 파일 표시
        - `-l`: 상세 정보 표시
        - `-r`: 파일 정렬 순서 거꾸로
        - `-t`: 파일 작성 시간 순으로 내림차순 표시
    - `ls -al`: 위 옵션들(숨긴 파일 표시, 상세 정보 표시) 추가
    - `clean`: 터미널 창의 내용을 지움

2. 터미널 창에서 디렉터리 이동하기

    디렉터리 이동시 `cd` 를 사용
    - `cd ..`: 상위 디렉터리로 이동
    - `cd <하위 디렉터리 이름>`: 하위 디렉터리로 이동
    - `~`: 현재 사용자의 홈 디렉터리, 홈 디렉터리 경로는 **c/Users/사용자 아이디** 입니다.

3. 터미널 창에서 디렉터리 만들기 및 삭제하기

    - `mkdir <디렉터리 이름>`: 디렉터리 만들기
    - `rm -r <디렉터리 이름>`: 디렉터리 삭제하기

4. 텍스트 문서 내용 확인하기

    - `cat <파일 이름>.txt`: 텍스트 문서를 터미널에서 확인 가능  
        (cat은 concatenate의 줄임말)

### 깃에서 기본 편집기 및 변경하기

#### 리눅스의 기본 편집기 빔(Vim)

빔은 터미널에서 사용할 수 있는 대표적인 편집기입니다.

`vim <파일 이름>.txt` 로 파일을 엽니다.  
해당 파일 이름이 없을 경우 새로 텍스트 파일을 만듭니다.

```bash
# vim으로 test.txt 열기
$ vim test.txt
```

vim은 ex 모드와 입력 모드가 있습니다.

`I`를 누르면 입력 모드로 들어가지고 수정이 가능하며  
`ESC`를 누르면 ex 모드로 나가지고 저장 및 종료가 가능합니다.

- `:w` or `:write`: 편집 중이던 문서를 저장
- `:q` or `:quit`: 편집기를 종료
- `:wq (파일)`: 편집 중이던 문서를 저장하고 종료, 파일 이름을 입력하면 그 이름으로 저장
- `:q!`: 저장하지 않고 종료, `!`를 사용해서 경고를 무시했기 때문에 **확장자가 .swp인 임시파일**이 생김

#### vim 설명서

- vim 게임으로 배우기 [https://vim-adventures.com/](https://vim-adventures.com/)
- vim 단축키 목록 [vim graph sheet link](https://flatcap.org/vim/)

![vim graph sheet](./photo/003.png)

#### vim 이 익숙하지 않고 다른 에티터를 쓰고싶다면?

```bash
# vim 에서 notepadd++ 로 변경
$ git config --global core.editor "notepad++"
```

파일 이름 대신 편집기 실행 파일 경로로 입력해도 가능

### CRLF Warning 이란?

**리눅스**나 **Max**에서 `Enter` 는 `LF` 문자가 삽입되지만  
**Windows**에서 `Enter` 는 `CR` + `LF` 문자가 삽입됩니다.

> LF(Line Feed): 커서의 위치를 그대로 두고 종이를 한 라인 올리는 동작  
> CR(Carriage Return): 현재 라인에서 커서를 가장 앞으로 옮김

깃은 리눅스 기반이고 우리가 사용하는 컴퓨터는 윈도우기 때문에  
깃 배시에서 작성된 `리눅스 Enter`를 `윈도우 Enter`로 바꿔야 합니다.

따라서 "warning: LF will be replaced by CRLF in hello.txt" 같은 경고 메시지는  
`리눅스 Enter(LF)`가 `윈도우 Enter(CRLF)`로 대체되어서 깃이 올린다는 의미입니다.

## :zero::four: 네번째 목표

Branch를 만들고 사용해보자  
브랜치란? [동비나 유튜브 강의 링크 7강](https://www.youtube.com/watch?v=I4latDqXo5M&list=PLRx0vPvlEmdD5FLIdwTM4mKBgyjv4no81&index=7)

### 1단계: 브랜치 생성

1. 깃 브랜치를 현재 브랜치를 확인합니다. `git branch`
2. 깃 브랜치를 만듭니다. `git branch <원하는 브랜치 이름>`

    브랜치를 잘 못 만들었을 때는 `git branch -d <지울 브랜치 이름>` 입력합니다.

### 2단계: 브랜치 이동

1. 깃 체크아웃으로 브랜치를 이동합니다. `git checkout <원하는 브랜치>`
2. 깃 브랜치로 다시 현재 브랜치를 확인합니다.(\*가 이동됨)`git branch`

### 3단계: 문서 작업 후 브랜치에서 커밋

1. 브랜치가 잘 바뀌었다면 원하는 문서작업을 합니다.
2. 작업이 끝난 후 `add` 와 `commit` 을 하고 `log`로 커밋내용을 확인합니다.
3. HEAD(가장 최근에 커밋한 메시지)부분이 만든 브랜치를 가르키고, origin(원격 저장소)와 master(메인 브랜치)는 다른 부분을 가르킵니다.

### 4단계: 마스터 브랜치로 돌아가서 합치기

결합(Merge)는 보통 마스터 브랜치에서 합니다.

1. 이제 마스터 브랜치로 돌아갑니다.  `git checkout master`
2. 마스터 브랜치에 새로만든 브랜치를 결합(merge)합니다. `git merge`

### 5단계: 마무리

1. 결합이 잘 되면 원격 저장소에 `push` 합니다.
2. 브랜치를 사용할 일이 없으면 `git branch -d <지울 브랜치 이름>`으로 지웁니다.

## :zero::five: 다섯번째 목표

브랜치 충돌(Conflict) 해결하기

충돌 상황 -> 마스터 브랜치와 다른 브랜치의 코드가 다를 때

Git에서는 자동으로 충돌난 부분을 표시해 줍니다.

```python
<<<<<<<<<  # 충돌이 난 부분(수정 후 삭제)
# 충돌 내용
 ========  # 가운데 선 위아래 차이 경계선(수정 후 삭제)
>>>>>>>>>  # 충돌이 난 부분(수정 후 삭제)
```

이 부분을 해결(원하는 부분을 지우는 등)한 후 커밋하면 자동으로 merge가 됩니다.

## :zero::six: 여섯번째 목표

원격 저장소 관리하기

시나리오: 내가 작성한 코드를 공유 원격 저장소와 나만의 원격 저장소에 동시에 저장 및 관리하고 싶을 때

- `git remote`: 깃 원격 저장소에 연결된 목록 보기
  - 보통 기본적인 원격 저장소 이름은 **origin**으로 나옵니다.
- `git remote -v`: 깃 원격 저장소에 연결된 목록 간단히 보기
- `git remote show origin`: 깃 원격 저장소 origin 자세히 보기
- `git remote add <사용할 원격 저장소 이름> <원격 저장소 주소>`: 다른 원격 저장소 추가하기
- `git remote rename <기존 이름> <바꿀 이름>`: 원격 저장소 이름 바꾸기
- `git rm <원격 저장소 이름>`: 원격 저장소 제거

## :zero::seven: 일곱번째 목표

로그 다루기

- `git log --stat`: 커밋의 통계 정보 출력
- `git log --graph`: 브랜치를 그래프로 보여줌
- `git log -p`: 커밋에 적용한 구체적인 항목 출력
여러 옵션 보기 링크 -> [https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History}](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)

예시 -> `git log --pretty=format:"%h -> %an, %ar : %s" --graph`

로그는 원격저장소에서도 이쁘게 나오지만 이런게 있다고 알아두면 좋음

## :zero::eight: 여덟번째 목표

README.md 관리하기

- [MarkDown 가이드 사이트](https://www.markdownguide.org/basic-syntax/)  
- [MarkDown 수식 참고 사이트](https://csrgxtu.github.io/2015/03/20/Writing-Mathematic-Fomulars-in-Markdown/)

MarkDown 이모티콘 사이트 Search on Google `markdown emoji`

- 1st site [https://gist.github.com/rxaviers/7360908](https://gist.github.com/rxaviers/7360908)
- 2ed site [https://github.com/ikatyang/emoji-cheat-sheet](https://github.com/ikatyang/emoji-cheat-sheet)

## :zero::nine: 아홉번째 목표

git archive 로 소스코드만 압축하기

`git archive --format=zip master -o ../<프로젝트 이름>.zip`

git 관련 파일을 제거하고 파일을 압축 배포할 때 사용

## :one::zero: 열번째 목표

커밋 내역을 확인하고 수정하기

커밋 내역을 보면 개발자들이 언제 파일을 수정하고 어떻게 했는지 알 수 있습니다.  
이 기록들을 어떻게 수정할 수 있는지 알아봅시다.

### 1단계: 원격 저장소에 있는 파일 불러와서 커밋 삭제하기

1. 원격 저장소에 있는 파일들 가져오기

    `git pull`

2. 원하는 커밋으로 돌아가기

    `git reset --hard <커밋 해쉿값>` -> 특정 커밋으로부터 최신까지 다 지우겠습니다.  
    `--hard` 옵션은 전부 다 지우고 [주의!] 커밋이 다 날라가 예전문서로 돌아가서 복구할 수 없습니다.  
    `--sort`옵션은 윗부분 커밋은 남겨두고 해당 커밋때로 돌아갑니다.

3. 커밋 수정 원격 저장소에 올리기

    `git push -f` -f 로 강제로 푸쉬해야 가능합니다.

### 2단계: 커밋 메시지 수정하기

가장 최근에 커밋한 메시지를 수정하는 방법입니다.

1. `git commit --amend` 입력
2. Unix 에디터에 들어오면 관리자 모드와 수정모드로 나뉩니다.
3. 수정모드로 가기위해 `a`나 `i`키를 눌릅니다.
4. 원하는 글자로 커서를 옮긴 뒤 수정합니다.
5. 수정이 완료되면 `ESC`를 누르고 `:wq`(저장 후 종료) 를 씁니다.
6. 로컬 저장소로 강제로 푸쉬 `git push -f`합니다.

## :one::one: 열한번째 목표

Git config 환경 설정에 대해 알아보기

- `git config --list`: 깃 환경설정 보기
- `~` -> `ls -al` -> `cat .gitconfig`: 깃 글로벌로 확인하기
- `git config user.name "<다른 이름>"`: 다른 이름으로 유저 이름 설정
- `git config user.email "<다른 이메일>"`: 다른 이메일로 유저 이메일 설정

## :one::two: 열두번째 목표

커밋 날짜 변경하기

다양한 기능은 강의 참고 [동비나 유튜브 강의 링크 15강](https://www.youtube.com/watch?v=ys0lVeTHl7c&list=PLRx0vPvlEmdD5FLIdwTM4mKBgyjv4no81&index=15)

1. Commit 하나 수정하기

   1. 수정하고 싶은 커밋 아래의 커밋 주소를 복사
   2. `git rebase -i <붙여넣기>`
   3. vim 편집기 -> `pick` 을 `edit`으로 수정 후 저장
   4. `GIT_COMMITER_DATE="Oct 1 10:00:00 2018 +0000 git commit --amend -no-edit --date "Oct 1 10:00:00 2018 +0000"`
   5. `git rebase --continue`

2. Filter를 사용

   깃에서는 Filter 기능을 지원

   ```bash
   git filter-branch -f --env-filter \
   'if [ $GIT_COMMIT = <Commit 해시 값> ]
   then
     export GIT_AUTHOR_DATE="Jan 1 03:00 2017 +0900"
     export GIT_COMMITTER_DATE="Jan 1 03:00 2017 +0900"
   fi'
   ```

## :one::three: 열세번째 목표

깃허브에 SSH 원격 접속하기

SSH란 Secure Shell의 줄임말로 보안이 강화된 안전한 방법으로 정보를 교환하는 방식입니다.  
Private Key와 Public Key를 한 쌍으로 묶어서 컴퓨터를 인증합니다.  

SSH 방식으로 깃허브 저장소에 접속하는 과정을 간단히 살펴보자

1. 사용자가 만든 퍼블릭 키를 깃허브 서버에 전송합니다.
2. 사용자 컴퓨터에 깃허브 저장소에 접속하면 사용자 컴퓨터에 있는 프라이빗 키와 깃허브 서버의 퍼블릭 키를 교환합니다.
3. 교환할 때 두 키가 서로 맞으면 사용자 컴퓨터와 깃허브 저장소가 연결 됩니다.

### 1단계: SSH 키 생성하기

```bash
$ cd ~
# 홈 디렉토리로 이동합니다.
$ ssh-keygen
# ssh key generate
```

-> 우리는 잘 모르니 아무것도 입력하지 말고 `Enter` 만 계속 누르면 키가 생성됩니다.  

### 2단계: SSH 키 생성 확인하기

```bash
$ cd ~/.ssh
# .ssh 폴더로 이동합니다. 없으면 ssh 키생성이 안됬습니다.
$ ls -al
# 폴더안의 내용을 확인합니다.
```

```bash
total 17
drwxr-xr-x 1 wansang 197609    0  7월 17 05:37 .
drwxr-xr-x 1 wansang 197609    0  7월 17 05:37 ..
-rw-r--r-- 1 wansang 197609 2610  7월 17 05:37 id_rsa  # private key
-rw-r--r-- 1 wansang 197609  577  7월 17 05:37 id_rsa.pub  # public key
```

### 3단계: 깃허브에 퍼블릭 키 전송하기

SSH 방식을 사용해서 깃허브에 접속하기

1. 퍼블릭 키를 깃허브에 올리기

    ```bash
    cd ~/.ssh
    cat id_rsa.pub
    ```

    ssh-rsa로 시작해서 끝까지(drag) 복사(`Ctrl` + `Insert`)합니다.

2. 깃허브에 로그인 -> 오른쪽 위 사용자 사진 클릭 -> Setting 클릭 -> SSH and GPG keys 클릭
3. SSH Keys 에 New SSH Keys 클릭 -> title 작성 후 Key에 붙여넣기(```Shift``` + ```Insert```) -> Add SSH Key 클릭
4. 이제 로그인 없이 SSH 키를 만들었던 컴퓨터는 깃허브 저장소의 SSH 주소만 알고 있으면 접속이 가능합니다.

### 4단계: SSH 주소로 원격 저장소 연결하기

1. 연결한 원격 저장소를 새로 만들거나 해당 원격 저장소로 들어갑니다.
2. SSH 주소를 복사합니다.
3. ```git remote add origin <주소 붙여넣기>``` 로 연결합니다.
4. 연결이 잘 되었는지 확인하기 위해 ```git remote -v```로 확인합니다.

## :one::four: 열네번째 목표

git rebase 마스터 하기

중급 버전에서 업데이트 할 예정

---

## 깃 명령어 정리

1. 깃 설치 확인

   - `git`: 깃 명령에서 사용할 수 있는 여러 옵션 표시, 단 깃이 설치되어 있어야 작동

2. 깃 사용자 환경 설정

    깃 버전을 저장할 때마다 버전을 만든 사용자 정보도 함께 저장하기 때문에 사용자 이름과 메일주소를 등록해야 합니다.

    - `git config --global user.name 'wansang'`: 사용자 이름 정보 저장
    - `git config --global user.email 'wansang93@naver.com'`: 사용자 이메일 정보 저장
    - `git config --global --list`: global 변수 보기
    - `git config --global --edit`: global 변수 수정

3. 깃 시작하기

    - `git init`: 깃 저장소 빈폴더로 초기화(Initialized empty Git repository)

4. 깃 상태보기

    - `git status`: 깃 상태 보기

        1. On branch master: master 브랜치에 있습니다.
        2. No commits yet: 아직 커밋한 파일이 없습니다.
        3. nothing to commit: 현재 커밋할 파일이 없습니다.
        4. Untracked files: Working tree에 파일이 있습니다.
        5. changes to be committed: Stage에 파일이 있습니다.
        6. nothing to commit, working tree clean: Working tree와 Stage에 파일이 없습니다.

        unmodified, modified, staged 상태

        ![상태 이미지](photo/004.jpg)

5. 깃 스테이징하기

    - `git add <파일 이름>`: Working tree에 **해당 파일**을 Stage로 올립니다.
    - `git add .`: Working tree에 **모든 파일**을 Stage로 올립니다.

6. 스테이지에 올라온 파일 커밋하기

    - `git commit -m "<커밋 메시지>"`: 커밋 메시지(보통 변경 이유나 특이사항)을 작성하고 올리기
    - `git commit -am "<커밋 메시지>"`: add와 commit을 한꺼번에 합니다.

7. 커밋 내용 확인하기
    - `git log`: 커밋 이력을 확인합니다.
    - `git diff`: 현재 상황과 변경 사항을 비교하여 확인합니다.
  
8. 작업 되돌리기(Reset, Restore)

    ![깃 동작 과정](./photo/002.jpg)

    1. add와 commit을 하지 않은 상태일 때(Working tree(작업 트리)에서만 수정함)
       - `git restor <파일 이름>`: 작업 트리에서 수정한 **해당 파일** 되돌리기
       - `git restore .`: 작업 트리에서 수정한 **모든 파일** 되돌리기
    2. add만 하고 commit은 하지 않은 상태일 때(Staging Area에서 Working tree로 이동하고 싶을 때)
       - `git reset HEAD <파일 이름>`: Staging Area에 있는 **해당 파일**이 내려오고 1번 상태가 됩니다.
       - `git reset HEAD .`: Staging Area에 있는 **모든 파일**이 내려오고 1번 상태가 됩니다.
    3. add와 commit 둘 다 한 상태(최신 커밋 되돌리기)
       - `git reset`: 최신 커밋을 되돌리고 1번 상태가 됩니다.

    `git reset <옵션> <commit>` 옵션들

    ```text
    <옵션>
    1. --sort: 최근 커밋을 하기 전 상태로 작업 트리를 되돌립니다.
    2. --mixed: 최근 커밋과 스테이징을 하기 전 상태로 작업 트리로 되돌립니다.(기본 값)
    3. --hard: 최근 커밋과 스테이징, 파일 수정을 하기 전 상태(하드한 상태)로 되돌립니다.

    <commit>
    1. HEAD^: 해드 이전 커밋으로 이동
    2. HEAD~3: 해드 포함 3칸 이전 커밋으로 이동
    3. 커밋 해쉬: 해당 해쉬 커밋으로 이동
    ```

9. 브랜치 상태보기

    - `git branch`: 현재 브랜치의 상태와 갯수를 봅니다.
    - `git log --oneline --branches --graph`: 브랜치 상태를 그래프로 봅니다.

10. 브랜치 만들기

    - `git branch <브랜치 이름>`: 브랜치 이름으로 브랜치를 만듭니다.

11. 브랜치 이동

    - `git checkout <브랜치 이름>`: 브랜치 이름으로 이동합니다.

12. 브랜치 합치기

    - `git merge`: 이어질 브랜치에서 사용해야하고 다른 브랜치와 합칩니다.

13. 브랜치 삭제

    - `git branch -d <브랜치 이름>`: 해당 브랜치를 삭제합니다.

14. 수정 중인 파일 감추기 및 되돌리기

    현재 작업하는 내용을 특정 공간(stash)에 임시적으로 보관이 가능합니다.  
    이 기능을 쓰면 경고 메시지가 나오지 않아 편하게 작업할 수 있습니다.

    - `git stash`: 해당 작업들을 stash에 임시적으로 보관합니다.
    - `git stash list`: stash 목록을 보여줍니다.
    - `git stash apply`: stash에 보관된 자료를 현재 문서에 적용합니다.
    - `git stash drop`: stash에 보관된 자료를 삭제합니다.
    - `git stash pop`: stash에 보관된 자료를 현재 문서에 적용하고 삭제합니다.(apply + pop)
