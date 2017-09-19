# SSH 다른 포트로 접속하는 방법

- 동작하지 않음
```bash
ssh root@mydomain.com:10022
```

- 올바른 방법
```bash
ssh -p 10022 root@mydomain.com:10022
```