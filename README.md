# ACT
### Github Actions 테스트 편하게 하기!!

Github Actions를 테스트하려면 항상 commit / push 하면서 확인하는 
번거로운 과정을 항상 거쳐야했는데, 이를 로컬에서 테스트할 수 있도록 도와주는 툴을 발견..(만세)

1. Act 설치   
    - mac : `brew install act`
    - 설치 방법 : https://nektosact.com/installation/index.html

1. 작동 방식 
    - workflow가 돌아갈 컨테이너를 생성해서 실행시켜줌 -> **Docker 설치가 필요함**

1. (내가 생각한) 주요 Act 명령어  
    > [주의] ARM 아키텍쳐 사용하는 경우(맥북 M시리즈)에는 명령어마다 `--container-architecture linux/amd64` 옵션을 붙여주거나,
    `.actrc`파일 생성 후,`--container-architecture linux/amd64` 적어놓기

    - `act --help` : act 명령어 help를 보여줌
    - `act -l`  : 명령어를 입력한 위치에서 .github/workflows 디렉토리를 찾고, workflow들을 보여줌
    - `act`, `act push` : github에 push하는 상황을 동일하게 테스트 (Push로 트리거 되는 workflow들 실행)

Reference : https://github.com/nektos/act
