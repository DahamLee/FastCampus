# AWS 배포 매뉴얼

### 장고 파일 생성

1. **Django 프로젝트에서 key값 분리**
2. AWS 접속 EC2 검색
3. 우분투(서버) 선택
4. SSH 키를 선택해야 한다.
5. private key와 public key 나옴
6. public key는 서버에 남아있음
7. private key는 처음에 한번만 나오니 저장해둬야 함
8. private key를 다운받아서 홈폴더의 .ssh에 저장
9. chmod 명령을 사용하여 private key 파일을 소유주만 읽을 수 있도록 권한 설정한다.
10. `chmod 400 /path/my-key-pair.pem `
11. 인스턴스 항목을 클릭 아래에 나오는 public DNS에 접근
12. 접근 방법은



### awscli 설치방법:
```
pip install awscli
```

https://aws.amazon.com/ko/cli/
