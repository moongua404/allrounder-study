# Github 사용법

## Overview
깃허브란? 원격 코드 저장 서비스
- 웹상에 코드를 올려 여러 개발자가 협업할 수 있도록 돕는 대표적인 서비스

<img width="400" alt="image" src="https://github.com/user-attachments/assets/9f2b0b0d-2ba6-46e4-8d66-582e43c14f83" />

#### Repository : 원격 저장소, 프로젝트의 파일을 저장할 수 있는 공간
#### Branch : 코드의 복사복 생성
- 특정 시점에서 별도의 작업을 하기 위해 복사본을 생성, Tree 자료구조와 유사하게 갈래를 뻗어나감
  - ex) `main` branch에서 배포중인 프로젝트 파일을 관리, 여기서 branch를 친 `develop` branch에서 개발중인 프로젝트 파일을 관리
    - `develop`에서 새로운 branch를 쳐서 각자 기능을 구현 -> 서로의 파일에 대한 간섭 없이 코드 작성 가능, 효율적인 버전 컨트롤 가능
#### Pull Request(PR) : 코드 병합 요청
- 분리된 branch의 코드에 대한 병합 요청, 코드 리뷰 등의 서비스를 지원
  - ex) `feature-???` branch에서 구현한 기능을 `develop` branch로 병합을 요청
  - 권한을 가진 사용자가 Pull Request를 받아 병합(Merge) 가능
#### Commit : 변경된 파일을 저장하는 과정
- 코드의 snapshot을 저장, 이를 기준으로 되돌리거나 병합하는 등의 행동을 할 수 있다.
- 작업의 기준이 되기에 일반적으로 Commit convention을 지켜야 한다. 
 
...

## 사용 가이드
### 새 저장소(Repository) 생성
<img width="full" alt="image" src="https://github.com/user-attachments/assets/d403651e-d87f-4d09-bd20-a37f6ab3b7cc" />

#### 1. [깃허브 웹사이트](https://github.com/)에 접속한 후 `New` 아이콘을 클릭한다. 

<img width="full" alt="image" src="https://github.com/user-attachments/assets/e897f606-a7b8-4db4-a389-46b448d5aae3" />

#### 2. 필요한 필드를 채운다.
- Repository name을 입력한다. 일반적으로 영어 소문자와 `-`를 활용하여 이름짓는다.
- 공개 범위를 설정한다.
- 설정을 마친 경우 `Create repository` 버튼을 누른다.

### 로컬 저장소 연결 (clone을 통한 연결)
#### 1. Repository Url을 복사한다. url의 구성은 일반적으로 `github.com/{Organization의 이름}/{Repository의 이름}.git` 이다. 
<img width="full" alt="image" src="https://github.com/user-attachments/assets/f41a4d17-2325-4f8d-860b-2d4d68de0a7b" />

#### 2. 원격 저장소를 로컬 저장소로 복사한다. 
- 터미널에서 `git clone {url}`을 통해 프로젝프 파일을 복제할 수 있다.
- 대부분의 개발환경에서 원격 저장소에서 복제하는 기능을 지원한다.
  - IntelliJ의 경우 `Get from VCS`를 통해 원격 저장소를 복제할 수 있다.

### 파일 작성 / 수정
<img width="full" alt="image" src="https://github.com/user-attachments/assets/f43e2e4c-a956-4dc0-99a0-2c8f13fe18aa" />

#### 1. 파일을 작성하거나 수정한다.
- 이미지에서는 리드미 파일을 생성하여 작성했다.
  - 리드미 파일은 루트 디렉토리에서 `README.md` 파일을 만들어 작성한다.
  - 리드미 파일은 프로젝트 전반에 대한 설명을 포함한다.

### commit / push
<img width="full" alt="image" src="https://github.com/user-attachments/assets/4ce7169d-a7b2-4c5e-8a84-1c657ab53e29" />

#### 0. 본인이 작성할 내용이 현재 브랜치와 다를 경우 브랜치를 판다.
- `git checkout branch -b "{브랜치명}"`을 통해 브랜치를 새로 팔 수 있다.
  - cf. `git checkout`은 브랜치를 바꾸는 명령어이다. `-b`를 붙이면 새로운 브랜치를 만들면서 체크아웃하게 되는 것이다.
#### 1. 변경사항을 `git add`를 통해 저장한다. (전부 변경사항에 반영하려면 `git add .`을 한다.)
#### 2. `git commit -m "{커밋 메시지}"` 명령어를 통해 커밋을 만든다.
- 이 때 커밋 메시지는 커밋 컨벤션을 따르며, 첫째 줄은 간결하게 작성 후 남길 메시지가 있다면 줄바꿈을 2번 한 뒤 2~3줄 정도 작성한다.
- 커밋을 한 시점에는 로컬 저장소에 저장되며 push를 해야 원격 저장소에도 저장된다.
#### 3. `git push` 명령어를 통해 로컬 저장소에 있는 변경사항을 원격 저장소로 올린다.
- 로컬 저장소에서 브랜치를 만들었을 경우, `git push -u origin {브랜치명}`을 통해 원격저장소로 브랜치를 저장(생성)한다. 
- cf. 반대 급부로 원격 저장소에 있는 변경사항을 가져올 때는 `git pull` 명령어를 사용한다. 

### Pull Request
<img width="full" alt="image" src="https://github.com/user-attachments/assets/1ab1c2f6-9345-4cd5-9615-167eb004c34d" />

#### 1. `Compare & Pull request` 버튼을 누른다. 
#### 2. PR 메시지를 작성한다. 
- PR역시 컨벤션을 지키며 작성하는 것이 좋다.
#### 3. `Create pull request` 버튼을 누른다. 
(결과 예시)\
<img width="512" alt="image" src="https://github.com/user-attachments/assets/72f0330b-3fe9-45e5-8ebe-4fae4323a9cd" />

### Code Review
<img width="full" alt="image" src="https://github.com/user-attachments/assets/a2693365-ce45-4a65-8660-bdee707eda86" />

#### 1. PR에서 상단 탭에 `File changed`를 클릭한다. 
#### 2. 리뷰를 달 부분을 클릭한다. 
#### 3. 리뷰를 작성한 후 `Start a review` 또는 `Add review comment` 버튼을 누른다. 

<img width="full" alt="image" src="https://github.com/user-attachments/assets/00e025e4-952d-47ef-bc21-926a6f913776" />

#### 4. 리뷰를 끝마친 후, `Finish your review` 버튼을 눌러 리뷰를 마친다. 
#### cf. `Finish your review` 버튼을 누르지 않을 경우 `Pending` 상태이며 리뷰가 공유되지 않는다. 
