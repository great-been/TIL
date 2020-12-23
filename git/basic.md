# Github 특강 - Basic

## git이란?

한 번에 완벽한 파일을 만들어 내는 것은 힘들뿐더러, 지속적으로 수정이 필요하다.
따라서 사람들은 한 파일에 대해 여러가지 버전을 만들게 된다.
git은 이러한 버전을 관리하기 위한 시스템이다.

## github란?

- github는 git을 저장하고 있는 클라우드이다.
- 하나의 git은 하나의 프로젝트처럼 보여진다.

## git 설치

1. git-scm.com에서 다운로드
2. 계속 next 로 설치

## git 사용법

### 최초 설정

처음 컴퓨터에 git을 설치하면, 사용자의 이메일과 이름을 적어준다.
이는 앞으로 일어나는 commit에 서명을 하기 위해서 필요하다.

```
$ git config --global user.name '<이름>'

$ git config --global user.email '<이메일주소>'
```

설정을 확인하는 명령어는 다음과 같다.

```
$ git config user.name
이름 출력

$ git config user.email
이메일 출력
```

### 상태점검

```
$ git status
```

현재 상태를 보여준다.
상태는 아래와 같이 4개로 나누어진다.

| Untracked     | Unmodified    | modified | stage              |
| ------------- | ------------- | -------- | ------------------ |
| 인식되지 않음 | 수정되지 않음 | 수정됨   | commit 가능한 상태 |

- 처음 생성된 파일은 untracked 상태이다.
- 빨간색으로 표시되는 파일은 stage에 올라가 있지 않은 상태이며, commit을 실행해도 아무 변화도 생기지 않는다.
- 초록색으로 나타나는 파일은 stage에 있는 상태이며 commit이 가능하다.

### 초기화

초기화는 `git init`을 통해 진행한다.

```
$ git init
```

- `git init` 은 git의 저장소를 만들어준다.
- 일반 폴더를 텅 빈 방이라고 했을 때, 버전을 관리할 수 있는 기능을 부여한다. 기능이 부여된 폴더는 repo 라고 부르며, 일반 폴더와 다르다.
- `.git` 폴더가 생성된다. 이는 숨겨진 폴더로  `ls -a` 로 확인 가능하다.
- repo는 하위 폴더에 영향을 준다. 즉, 상위 폴더가 repo면 하위 폴더도 repo가 된다.
- 홈폴더는 repo가 아니며 "절대" 초기화를 하면 안된다.

### Add 하기

```
$ git add <filename>
```

add의 기능은 파일을 stage에 올리는 것이다. 카메라에 비유하면 화각에 넣는것이다.
파일을 stage에 올림으로써 commit 이 가능해진다.
add를 사용하는 경우를 두 가지로 나누어 볼 수 있다.

1. Untracked 파일을 stage에 올리기 위해
2. 수정된 파일을 stage에 올리기 위해

1의 경우는 생성된 파일을 인식시키는데 사용된다.

한 번 인식된 파일은 의도하지 않는 이상 untracked 상태로 돌아가지 않는다.

### Commit 하기

```
$ git commit -m '<message>'
```

stage에 있는 파일을 저장하는 것이다. 카메라에 비유하면 사진을 촬영하고 사진첩에 저장하는 것이다.
stage에 있는 파일만 commit 가능하다. 
commit 된 파일은 log에 기록된다.

`$ git commit` 을 한 경우에는 esc 후 `:q!` 로 종료한다.

commit 된 파일은 unmodified상태로 돌아간다.
commit을 할 때는 directory를 확인한 후 진행한다.
commit 주기는 보통 하루에 한 번 정도이며 개인에 따라 기준을 세워서 진행한다.
메시지는 후에 쉽게 알아볼 수 있도록 성의있게 남겨야 한다.

### Log 보기

```
$ git log
```

commit된 파일에 대한 기록을 보여준다.
최신 파일이 가장 먼저 보여진다.

### 원격 저장소 등록하기

```
$ git remote add origin <URL> # 원격 저장소 등록하기

$ git remote -v # 원격 저장소 확인하기

$ git remote rm # 원격 저장소 삭제하기
```



### 원격 저장소에 push 하기



## 구조화 

보고서_최종

보고서_최종최종

버전을 효율적으로 관리하기 위해 파일을 구조화 해야한다.

보고서_v1.0

보고서_v2.0

이렇게 변경하면 직관적이고 편리한 버전 관리가 가능하다.
하지만 버전이 많아지면 용량 문제가 생긴다. 
이는 변경사항만 저장함으로써 해결할 수 있고, 따라서 unmodified와 modified가 존재하는 것이다.
버전을 더 효율적으로 관리하기 위해서는 수정내역을 작성하면 편리하다.

ex) $ git commit -m '<수정내역>' 

###  semantic versioning

x.y.z의 구조로 major.minor.patch 순이다.
버전은 출시(release)시기에 보여진다.

## Typora

### typora란?

코드를 저장하고 구조화하여 관리할 수 있다.
.md (mark down) 파일에 코드를 저장한다.

### typora 설정

1. typora 열기
2. 파일
3. 환경설정
4. 이미지
5. assets 경로로 이미지 복사, 가능하다면 상대적 위치 사용 체크하기

### typora 사용법

typora는 편리한 문서 구조화 기능을 제공한다. 

- #를 사용하여 상위, 하위 목록을 나눌 수 있다.
- ctrl + 숫자는 #과 같이 markdown 기능을 한다.
  ex) # = ctrl + 1, ## = ctrl + 2
- 코드를 작성할 때는```을 사용하여 코드 작성 공간을 만들 수 있다.
- 문장내에서 코드 작성을 하고 싶으면 `을 사용한다.
- 숫자 + . 을 활용하여 ordered list 작성이 가능하다.
- 내용만 입력하면 본문으로 작성된다.
- ctrl + / 은 실제 작성된 내용을 보여준다.

typora에서 중요한 것은 글씨 크기의 차이가 아니다. markdown을 하고 있는 것이 중요하다.

## 참고

- 스타일 가이드, 언어 컨벤션은 언어마다 지켜주는 것이 중요하다. 맞춤법 지키는 것과 같다.

- 스타일가이드는 프로젝트, 팀마다 다르다. ex) 파이썬은 _ 를 사용한다. 

- 삽질 총량의 법칙 나만 모르는 거 아니고 다른 사람도 다 모른다!

## Summary

git에 대한 소개와 간단한 실행법에 대해서 학습했다.

- directory 지정
- 폴더와 파일의 생성 및 수정
- 초기화
- 파일 상태의 이해
- add와 commit에 대한 이해

| 명령어                              | 설명                                                |
| ----------------------------------- | --------------------------------------------------- |
| `$ cd`                              | change directory 의 의미이다. 디렉토리를 이동한다.  |
| `$ cd ~`                            | 홈폴더로 이동한다                                   |
| `$ cd ..`                           | 상위 디렉토리로 이동한다.                           |
| `$ mkdir <foldername>`              | make directory 의 의미이다. 폴더를 생성한다.        |
| `$ mkdir TIL`                       | 저장, 시간도 저장된다.                              |
| `$ touch <filename>`                | 파일을 생성한다.                                    |
| ` $ mv <before> <after>`            | 이름변경 (같은폴더내에서)                           |
| `$ git restore <filename>`          | 파일을 수정전 상태로 되돌린다.                      |
| `$ git restore --staged <filename>` | stage상태에서 전상태로 되돌린다.                    |
| `$ git init`                        | 빈 디렉토리(폴더)를 git 저장소(repo)로 초기화 한다. |
| `$ git add <filename>`              | `<filename>`을 Stage 에 올린다.                     |
| `$ git add .`                       | stage에 올릴 수 있는 파일을 모두 올린다.            |
| `$ git commit -m "commit message"`  | commit을 실행한다.                                  |
| `$ git status`                      | 현재 상태를 보여준다.                               |
| `$ git log`                         | 기록을 보여준다.                                    |
| `$ ls`                              | list 의 의미, 목록을 보여준다                       |
| `$ ls -a`                           | list all 의 의미, 숨겨진 목록까지 보여준다.         |
| `$ rm -rf <name>`                   | 강제 삭제를 실행한다.                               |
| ctrl + c                            | 취소 기능                                           |
| tab                                 | 자동완성 기능                                       |
| Windows + shift + s                 | 화면 캡쳐 기능, 사진을 삽입할 때 사용한다.          |
