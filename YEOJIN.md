# cpython

## compiling

### configuration

```shell
CPPFLAGS="-I$(brew --prefix zlib)/include" \
  LDFLAGS="-L$(brew --prefix zlib)/lib" \
  ./configure --with-openssl=$(brew --prefix openssl@1.1) \
  --with-pydebug
```

### build

```shell
make -j6 -s
```

* -j6 : 컴파일을 수행하는 프로세서의 코어 수에 맞게 설정

## 문법 파일 다시 만들기

1. python.gram 파일 수정
2. 문법 파일 리빌드
```shell
make regen-pegen
```
3. 파이썬 컴파일
