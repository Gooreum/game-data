# game-data

게임 데이터 백업용 private 레포.

`game-data.zip`(약 1GB)은 git 파일 크기 제한(100MB) 때문에 Releases 첨부파일로 보관한다.
따라서 `git clone`으로는 받아지지 않는다.

## 다운로드 방법

private 레포라 접근 권한이 있는 GitHub 계정으로 로그인되어 있어야 한다.

### 1. gh CLI (권장)

```bash
# 최초 1회 로그인
gh auth login

# 현재 디렉터리에 game-data.zip 다운로드
gh release download v1 -R Gooreum/game-data

# 저장 위치를 지정하려면
gh release download v1 -R Gooreum/game-data -D ~/Downloads
```

### 2. 브라우저

GitHub에 로그인한 상태에서 [Releases v1](https://github.com/Gooreum/game-data/releases/tag/v1) 페이지의
Assets 목록에서 `game-data.zip`을 클릭한다.

## 압축 해제

```bash
unzip game-data.zip
```

`game-data/` 폴더 아래에 `.mpq` 파일들이 풀린다. 함께 생기는 `__MACOSX/` 폴더는 macOS 메타데이터라 지워도 된다.

## 무결성 확인

파일 크기가 1,068,266,921바이트인지 확인한다.

```bash
stat -f "%z" game-data.zip   # macOS
stat -c "%s" game-data.zip   # Linux
```
