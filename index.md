# git 다시 해보기
# 새 저장소 만들기
- git init
- 터미널 -> git bash

# 파일 전부 스테이징
- git add .

# 커밋 메시지 작성
- git commit -m "작업 내용"

# github 원격저장소 연결
- git remote add origin 저장소 주소

# 저장소 내용 저장
- git push origin master

# 브런치 영역을 나눠보자
# 브런치는 저장소의 작업 공간
- master는 최종 작업물 다른 브런치를 만들어서 여럿이서 작업을 하거나 혼자 작업할 때 작업의 내용을 나눠서하고 최종 작업물로 병합한다.

- master(v0.1)로 작업하다가 -> dev라는 브런치를 만들고 -> dev에서 계속 작업하다가 -> master(v0.2)로 병합 / master에는 완벽한 파일만 올리기 위해

- master -> dev1, dev2 -> dev1 + dev2 -> master로 통합 /

# 브런치 목록 확인
- git branch : 로컬 저장소의 브런치 목록 확인
- git branch -a: 원격 저장소와 로컬저장소 브런치목록 확인
- 선택되어 있는 브런치는 *(글자가 초록색)

# 브런치 생성
- git branch 생성할 브런치 이름 / ex> git branch main

# 브런치 이동
- git checkout 이동할 브런치 이름 / ex> git checkout main
- git switch 이동할 브런치 이름

# 브런치의 제거
- git branch -d 제거할 브런치 이름 / ex> git branch -d main

# 저장소 병합
- git merge 병합할 브런치 이름

# merge 병합 중 충돌이 난 파일을 보여주고 선택할 수 있게 해준다.

# 원격 브랜치 삭제하기
- git push <원격 저장소 이름> -d <원격 브랜치 이름>

상황



 1. 신규 프로젝트 생성

2. 소스 생성 및 초기 설정

3. git init을 진행

4. git hub 에 개인 repository remote 수행 (git remote add origin [repository url] )

5. 생성한 소스를 커밋 과 푸시 시도

6. push reject 발생

7. pull 시도 하면 refusing to merge unrelated histories 로 pull 실패


원인

 - 신규로 만든 프로젝트와 기존에 있는 프로젝트는 공통 적으로 같은 조상을 보고 있지 않아서 서로 다른 프로젝트라고 인식 함.

   따라서 독립적인 두 프로젝트를 병합하려면 --allow-unrelated-histories를 사용해야 함.


해결책

- git pull origin 브런치명 --allow-unrelated-histories 를 사용

