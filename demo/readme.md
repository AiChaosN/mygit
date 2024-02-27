# Welcome DB_JIT_Benchmark !

## 系统环境要求
- Linux


## 运行方法
### 环境变量和依赖安装
- Fast way:复制下面的命令到终端执行
  - `sudo script.sh`
- Or 自己一个一个配置：
  Clang 14
  
  lli 14
  
  emcc 3.1.48
  
  wasmer 4.2.3
  
  wasmtime 15.0.0
  
  wasmedge 0.13.5

  python3+
  
  LLVM 8.0

  Hyper table rely on: https://tableau.github.io/hyper-db/docs/installation 
  
  PG relay on the PostgreSQL 15 installation : https://www.postgresql.org/docs/15/install-procedure.html 
  
  Mutable relay on the Mutable installation: https://github.com/mutable-org/mutable 


### 测试脚本运行
1. 生成测试数据：`sh -x ./run.sh`（这步骤将依次执行Native，LLVM，WASM并产生.csv数据文件）


2. 通过以下.py文件来打印出各个编译器的运行时间对比图：

`python PG_auto_execution.py`

`python hyper_auto_execution.py`

`python mutable_auto_execution.py`

`python noisepage_auto_execution.py`


### 做的好！结果图在result目录下，如下图所示：
![image](./result/hashjoin-compile.png)
![image](./result/hashjoin.png)

## 项目结构
- /test/ 包含了所有的测试算法
- /result/ 包含了所有的测试结果
上面是正式版的readme，可能会遗漏一些东西从下面取。

Experimental wrapper algorithm tests over LLVM and Wasm for compiling and executing code at run-time.

## About

* /test/ include all the test algorithms over LLVM and Wasm, and give the execution time and compilation time.
  
* PG_auto_execution.py
* hyper_auto_execution.py
* mutable_auto_execution.py
* noisepage_auto_execution.py

  are to test the TPCH Q1, Q3, Q6, Q12, Q14 performance in each Database.


### Result

https://github.com/UNSW-database/DB_JIT_Benchmark/tree/main/result