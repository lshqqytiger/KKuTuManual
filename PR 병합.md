# 끄투 서버 운영 도움말

작성자: [베프](https://github.com/lshqqytiger)

오류 제보: [GitHub Issues](https://github.com/lshqqytiger/KKuTuManual/issues)

수정 요청: [GitHub Pull Requests](https://github.com/lshqqytiger/KKuTuManual/pulls)

작성일: 2024년 1월 12일

마지막 수정일: 2024년 1월 12일

# PR 병합

원하는 기능을 이미 다른 개발자들이 구현해 병합 요청(Pull Request)으로 올려놓은 경우, Git을 사용해 이를 본인의 Fork에 병합할 수 있습니다.

다음은 그 과정을 설명합니다.

## JJoriping/KKuTu 레포지토리의 Fork를 만듭니다.

이미 Fork를 만든 경우 이 단계를 건너뜁니다.

[JJoriping/KKuTu](https://github.com/JJoriping/KKuTu) 레포지토리 페이지에 방문합니다.

우측 상단의 Fork 버튼을 눌러 새 Fork를 만듭니다.

기본적으로 만들어진 Fork는 `https://github.com/깃허브ID/KKuTu`에서 확인할 수 있습니다.

## 만든 Fork를 로컬에 복제합니다.

이 과정은 필수적이지 않지만, 다음과 같은 이유로 이 과정을 거치는 것이 용이합니다.

1. Git을 사용해 복제하지 않고 레포지토리 페이지에서 `.zip` 파일을 다운로드하면 로컬 레포지토리를 Git으로 관리할 수 없습니다.
2. 작업 내용을 서버에 바로 반영할 수 있습니다.

Powershell 또는 명령 프롬프트를 열고 아래 명령어를 입력합니다.

```
git clone https://github.com/깃허브ID/KKuTu
```

명령어를 실행한 경로에 새 폴더 `KKuTu`가 생성되었다면 성공한 것입니다.

## PR 주인의 레포지토리를 Remote로 추가합니다.

PR 페이지 중앙의 아래 문구를 확인합니다.

```
someone wants to merge n commits into JJoriping:master from someone:branch
```

여기서 `someone:branch` 부분을 클릭하면 `https://github.com/someone/KKuTu/tree/branch`으로 이동됩니다.

URL에서 `https://github.com/someone/KKuTu` 부분을 복사합니다.
(이 URL은 예시입니다. 실제 이동되는 URL에서 해당하는 부분을 복사해야 합니다)

복제한 레포지토리로 이동해 아래 명령어를 실행합니다.

```
git remote add someone https://github.com/someone/KKuTu.git
```

## Remote에서 정보를 받아옵니다.

Remote에서 새 정보를 받아오기 위해 아래 명령어를 실행합니다.

```
git remote update
```

## Remote에서 branch를 병합합니다.

이제 병합할 수 있습니다. 아래 명령어로 병합합니다.

```
git merge someone/branch
```

이 때, Conflict가 발생할 수 있습니다.

여러가지 도구를 사용해 적당히 Conflict를 해결합니다.

모든 Conflict를 해결했다면 아래 명령어를 실행해 병합을 완료합니다. 이 명령어는 Conflict가 없었다면 실행하지 않아도 됩니다.

```
git add .
git merge --continue
```

Conflict가 발생한 후 병합 작업을 취소하고 싶다면 아래 명령어를 실행합니다.

```
git merge --abort
```

병합 이후 병합 작업을 취소하려면 Revert해야 합니다. 이 과정은 여기서는 설명하지 않겠습니다.

## 병합한 commit들을 원격 레포지토리에 반영합니다.

아래 명령어를 실행하면 GitHub 서버에 병합한 내용이 반영됩니다.

```
git push
```

## 참조
