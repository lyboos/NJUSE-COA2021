# NJUSE-COA
南京大学软件学院2021秋《计算机组织结构》课程项目。

实现一个简单的x86模拟器，包括数据的表示与运算(Transformer、ALU、FPU、NBCDU)，内存管理(Cache、Disk、分段机制、分页机制)，指令解析与执行等功能。

#### 代码结构

```bash
.
│  .gitignore
│  pom.xml
│  README.md
│
├─src
│  ├─main
│  │  └─java
│  │      ├─cpu
│  │      │  │  CPU.java       # CPU类，需要阅读
│  │      │  │  CPU_State.java # CPU的寄存器列表
│  │      │  │  MMU.java
│  │      │  │
│  │      │  ├─alu
│  │      │  │
│  │      │  ├─instr
│  │      │  │  ├─all_instrs # 需要在这个文件夹里面添加指令的实现类
│  │      │  │  │      Add.java          # ADD指令的实现
│  │      │  │  │      InstrFactory.java # 指令工厂，使用了Java反射机制
│  │      │  │  │      Instruction.java  # 指令接口，需要阅读
│  │      │  │  │      Opcode.java       # 指令的操作码，参考Intel 32位指令实现
│  │      │  │  │
│  │      │  │  └─decode # 取指令相关的类，需要阅读
│  │      │  │
│  │      │  ├─registers # 寄存器类的定义
│  │      │  │
│  │      │  └─utils
│  │      │
│  │      ├─kernel # 测试时的程序入口
│  │      │      Loader.java
│  │      │      MainEntry.java
│  │      │
│  │      ├─memory
│  │      │
│  │      ├─program
│  │      │      Log.java # 实现控制台输出
│  │      │
│  │      ├─transformer
│  │      │
│  │      └─util
│  │
│  └─test
│      └─java
│          └─cpu
│              └─instr
│                      ICCTest.java # 测试类
│
└─test # 6个测试用例分别使用到的指令序列，需要自行阅读
        icc_test_1.txt
        icc_test_2.txt
        icc_test_3.txt
        icc_test_4.txt
        icc_test_5.txt
        icc_test_6.txt

```