# ACT
### Github Actions 테스트 편하게 하기!!

Github Actions를 테스트하려면 항상 commit / push 하면서 확인하는 
번거로운 과정을 항상 거쳐야했는데, 이를 로컬에서 테스트할 수 있도록 도와주는 툴을 발견..(만세)

1. Act 설치   
    - mac : `brew install act`
    - 다른 OS 설치 방법 : https://nektosact.com/installation/index.html

1. 작동 방식 
    - workflow가 돌아갈 컨테이너를 생성해서 실행시켜줌 -> **Docker 설치가 필요함**

1. Act 명령어  
    > [주의] ARM 아키텍쳐 사용하는 경우(맥북 M시리즈)에는 명령어마다 `--container-architecture linux/amd64` 옵션을 붙여주거나,
    `.actrc`파일 생성 후,`--container-architecture linux/amd64` 적어놓기

    - `act --help` : act 명령어 help를 보여줌
    - `act -l`  : 명령어를 입력한 위치에서 .github/workflows 디렉토리를 찾고, workflow들을 보여줌
    - `act -W 파일명` : 특정 workflow 파일만 실행
    - `act -e 파일명` : json파일로 input값 전달 가능

1. 트리거 방법
    - push : `act`, `act push`
    - pull_request : `act pull_request`
    - workflow_dispatch : `act workflow_dispatch`

Reference : https://github.com/nektos/act
