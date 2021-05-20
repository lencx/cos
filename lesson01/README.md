# Hello World

## 编译流程

```bash
              gcc工具链
             ┌───────────┐
hello.c  --> │gcc预处理器 │ --> hello.i
hello.i  --> │ gcc编译器  │ --> hello.s
hello.s  --> │ gcc汇编器  │ --> hello.o
hello.o  --> │ gcc链接器  │ --> hello可执行文件
             └───────────┘
```

```bash
# step1: 预处理：加入头文件，替换宏
gcc -E hello.c -o hello.i

# step2: 编译：包含预处理，将 C 程序转换成汇编程序
gcc -S hello.i -o hello.s

# step3: 汇编：包含预处理和编译，将汇编程序转换成可链接的二进制程序
gcc -c hello.s -o hello.o

# step4: 汇编文件生成可执行文件
gcc hello.o -o hello

# -----------------------------------------------------------

# Linux系统运行可执行文件: `./hello`
gcc hello.c -o hello

objdump -d HelloWorld
```

![hello.o hex](img/hello-hex.png)
