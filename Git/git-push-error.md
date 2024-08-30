## 에러 내용

```python
[info] error: RPC failed; HTTP 400 curl 22 The requested URL returned error: 400
send-pack: unexpected disconnect while reading sideband packet
fatal: the remote end hung up unexpectedly
Everything up-to-date
```

## 해결 방법

```bash
git config http.postBuffer 524288000
```

## 정리

나 같은 경우 push 하려고 하는 데이터의 크기가 너무 커서 에러 발생  
그 외에도 다양한 원인이 존재해서 상황에 맞게 해결해야함  