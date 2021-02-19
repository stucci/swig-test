[SWIG Tutorial](http://www.swig.org/tutorial.html)

env: ubuntu 20.04 on wsl

install swig
```shell
sudo apt install swig
```

generate
```shell
swig -python example.i
# -> example.py example_wrap.c
gcc -fpic -c example.c example_wrap.c -I/usr/include/python3.6
# -> example.o example_wrap.o
ld -shared example.o example_wrap.o -o _example.so
# -> _example.so
```

run
```shell
python3 main.py
```
