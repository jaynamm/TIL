## psycopg2 이슈

psycopg2 를 사용해서 postgres 의 데이터를 가져오려고 했는데 다음과 같이 에러가 발생했다.  

- 에러 내용  

```
Traceback (most recent call last):
  File "/Users/jeonghyeon/workspace/data-pipeline/db/postgres.py", line 1, in <module>
    import psycopg2
  File "/opt/homebrew/anaconda3/envs/data-pipeline/lib/python3.10/site-packages/psycopg2/__init__.py", line 51, in <module>
    from psycopg2._psycopg import (                     # noqa
ImportError: dlopen(/opt/homebrew/anaconda3/envs/data-pipeline/lib/python3.10/site-packages/psycopg2/_psycopg.cpython-310-darwin.so, 0x0002): Library not loaded: '@rpath/libpq.5.dylib'
  Referenced from: '/opt/homebrew/anaconda3/envs/data-pipeline/lib/python3.10/site-packages/psycopg2/_psycopg.cpython-310-darwin.so'
  Reason: tried: '/opt/homebrew/anaconda3/envs/data-pipeline/lib/libpq.5.dylib' (no such file), '/opt/homebrew/anaconda3/envs/data-pipeline/lib/libpq.5.dylib' (no such file), '/opt/homebrew/anaconda3/envs/data-pipeline/lib/libpq.5.dylib' (no such file), '/opt/homebrew/anaconda3/envs/data-pipeline/lib/libpq.5.dylib' (no such file), '/opt/homebrew/anaconda3/envs/data-pipeline/bin/../lib/libpq.5.dylib' (no such file), '/opt/homebrew/anaconda3/envs/data-pipeline/bin/../lib/libpq.5.dylib' (no such file), '/usr/local/lib/libpq.5.dylib' (no such file), '/usr/lib/libpq.5.dylib' (no such file)
```

### 해결 방법

해결 방법으로는 postgres 재설치 후 psycopg2 를 재설치했다.  

```
brew uninstall postgresql
```

```
brew install postgresql
```

```
pip uninstall psycopg2
```

```
pip install psycopg2
pip install psycopg2-binary
```