# **myproject**

팀원: 

충돌이 발생하는 경우 - 파일의 같은 위치에 다른 내용이 입력된 상황이라면?

```cmd
## merge에서 충돌이 발생하는 경우
git switch main
git merge conflict-1

# Auto-merging tigers.yaml
# CONFLICT (content): Merge conflict in tigers.yaml
# Automatic merge failed; fix conflicts and then commit the result.

# 당장 충돌 해결이 어렵다면 merge 중단
git merge --abort

# 해결 가능 시 충돌 부분 수정 후 git add, commit으로 병합 완료
git add .
git commit
:wq

## rebase에서 충돌이 발생하는 경우
# 오류 메세지와 git status 확인
# 당장 해결이 어려운 경우 중단
git rebase --abort

# 해결 가능 시 충돌 부분 수정한 뒤 아래 명령어 수행 (continue하여 또 충돌이 있는 지 찾는다)
# 충돌이 해결될 때까지 반복
git add .
git rebase --continue
:wq

# main에서 git merge conflict-2로 merge하여 마무리
git switch main
git merge conflict-2
git branch -d conflict-1
git branch -d conflict-2
```

------

### **Github 사용하기**

- Personal access token 만들기 - github에 파일을 올릴 때 이 토큰이 필요함
  - 우측 상단의 프로필 - Settings
  - Developer Settings
  - Personal access tokens - Generate new token
  - repo 및 원하는 기능에 체크, 기간 설정 뒤 Generate token
  - 토큰 안전한 곳에 보관해 둘 것
- 토큰 컴퓨터에 저장하기
  - Windows 자격 증명 관리자
  - Windows 자격 증명 선택
  - git:[https://github.com](https://github.com/) 자격 정보 생성
  - 사용자명과 토큰 붙여넣기
- Repository는 프로젝트 단위로 구성
  - Public : 모두에게 공개되는 프로젝트
  - Private : 허용된 인원만 볼 수 있는 프로젝트
- Repository의 settings - collaborators에서 협업할 팀원 추가

------

### **원격 저장소 사용하기**

#### **git과 github 연동하기**

```cmd
# 로컬에 원격 저장소 추가 후 푸시 (repository 명령어 복붙)

# 여기서는 https 프로토콜 사용
# 로컬의 git 저장소에 원격 저장소로의 연결 추가
git remote add origin (원격 저장소 주소)

# 브랜치 명 수정
git branch -M main

# 로컬 저장소의 커밋 내역을 원격으로 push (업로드). origin의 main branch로 push
git push -u origin main


# 원격 저장소 목록보기
git remote
git remote -v

# 원격 지우기 (github repository가 지워지는 것이 아니라 로컬 프로젝트와의 연결만 삭제)
git remote remove (origin 등 원격 이름)
# Github에서 프로젝트 다운받기

# 프로젝트를 다운받고자 하는 폴더에서 우클릭 - Git Bash here
git clone (원격 저장소 주소, https://github.com/gin-girin-grim/git-practice.git)
```

#### **Branch 합치기**

- Merge : 두 브랜치를 한 커밋에 이어붙이는 방식
  - 브랜치 사용 내역을 남길 필요가 있을 때
  - 다른 형태의 merge도 있음



![image](https://github.com/yeotaekyeong/git_test/assets/156942422/2289aecd-55a6-4443-98ab-49966c55dc5d)![image](https://github.com/yeotaekyeong/git_test/assets/156942422/44ac215d-2398-42b2-af6c-364ec6fbc461)


https://www.atlassian.com/git/tutorials/merging-vs-rebasing