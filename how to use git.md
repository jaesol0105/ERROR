## 1. Working Directory로 이동

## 2. 깃허브 계정 연동 (최초 1회만 수행)
```
git config --global user.name "닉네임"
git config --global user.email "이메일"
```

## 3. git init (최초 1회만 수행)
```
git init
```
명령어를 통해 git 저장소를 생성

## 4. add
```
git add .
```
저장소 내의 모든 변경사항 추가 (staged 상태)

## 4-1. add 목록 확인하기
```
git status
```

## 4-2. add 취소하기
```
git reset HEAD [file]
```

## 5. commit
```
git commit -m “message”
```
커밋 메세지와 함께 커밋 수행

## 5-1. commit 취소하기
```
git log --oneline : 커밋내역 보기
git reset HEAD^ : 가장 최신 커밋 한개 취소
```

## 6. push
```
git remote add origin “remote repository url” (첫 push 때만 사용)
git push -u origin master (첫 push 때만 사용. 이후 git push 명령어로 push 가능)
```
```
git push
```
원격 저장소(github)로 업로드

## 7. clone
```
git clone “remote repository url”
```
원격 저장소를 로컬로 복제

## 8. gitignore 자동생성 사이트
https://www.toptal.com/developers/gitignore
