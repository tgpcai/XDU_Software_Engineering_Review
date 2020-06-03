# 第八章：单元测试

#### Fault 和 Failure 的区别：

> **A fault occurs when a human makes a mistake, call an error, in performing some software activity. **

inside view，可以被开发者看到\(举例：bug,空指针异常..）

> **A failure is a departure from the system’s required behavior.**

outside view, 可以被用户看到（举例： 用户名或密码错误，更新失败，404，非法操作等\)

#### 测试的步骤：

1. 单元测试\(**Unit Test**\)
2. 集成测试\(**Integration Test**\)
3. 功能测试\(**Function Test**\)
4. 性能测试\(**Performance Test**\)
5. 验收测试\(**Acceptance Test**\)
6. 安装测试\(**Installation Test**\)

> 测试的进行有专门的独立的测试小组负责\(Independent Test Team\)

#### 黑盒法和白盒法的适用范围：

**Closed Box**\(黑盒法\)

> 在测试时，把程序看作一个不能打开的黑盒子，在完全不考虑程序内部结构和内部特性的情况下，测试者在程序接口进行测试，它只检查程序功能是否按照需求规格说明书的规定正常使用，程序是否能适当地接收输入数锯而产生正确的输出信息，并且保持外部信息（如数据库或文件）的完整性。

**Open Box**\(白盒法\)

> 盒子是可视的，你清楚盒子内部的东西以及里面是如何运作的。"白盒"法全面了解程序内部逻辑结构、对所有逻辑路径进行测试。"白盒"法是穷举路径测试。在使用这一方案时，测试者必须检查程序的内部结构，从检查程序的逻辑着手，得出测试数据。

区别：

> ```
> 二者最大的区别应该就是测试对象不一样。
> 白盒测试主要针对的是程序代码逻辑，耗费时间长。
> 黑盒测试主要针对的是程序所展现给用户的功能。
> 简单的说就是
> 白盒测试后台程序
> 黑盒测试前台展示功能。
> ```

白盒测试的优点：

* 迫使测试人员去仔细思考软件的实现
* 可以检测代码中的每条分支和路径
* 揭示隐藏在代码中的错误
* 对代码的测试比较彻底
* 最优化

白盒测试的缺点：

* 昂贵
* 无法检测代码中遗漏的路径和数据敏感性错误
* 不验证规格的正确性

#### 集成测试的两种策略：

* Bottom-Up 自底向上
* Top-Down  自顶向下

#### 语句测试，分支测试，路径测试方法及其应用：

> 上述三种测试方法均来自于白盒测试，**软件测试中的白箱测试是在黑箱测试完成后所进行的补充测试**，也是对软件内部结构的测试，它分为3方面的测试内容：**语句测试、分支测试、路径测试**。测试方法认为**路径测试是整个测试的基石**，目标是通过检验足够多的程序元素的路径来证实程序元素的实际结构同所期望的程序元素的结构是一致的。

* **语句覆盖测试**

**主要特点**：语句覆盖是最起码的结构覆盖要求，语句覆盖要求设计足够多的测试用例，使得程序中每条语句至少被执行一次

**优点**：可以很直观地从源代码得到测试用例，无须细分每条判定表达式。

**缺点**：由于这种测试方法仅仅针对程序逻辑中显式存在的语句，但对于隐藏的条件和可能到达的隐式逻辑分支，是无法测试的。

* **分支覆盖测试\(也叫做判定覆盖\)**

> 分支\(判定\)覆盖与条件覆盖有明显的区别，具体参考[http://bbs.csdn.net/topics/390915412](http://bbs.csdn.net/topics/390915412)

**主要特点**：条件覆盖要求设计足够多的测试用例，使得判定中的每个条件获得各种可能的结果，即每个条件至少有一次为真值，有一次为假值。

**优点**：显然条件覆盖比判定覆盖，增加了对符合判定情况的测试，增加了测试路径。

**缺点**：要达到条件覆盖，需要足够多的测试用例，但条件覆盖并不能保证判定覆盖。条件覆盖只能保证每个条件至少有一次为真，而不考虑所有的判定结果。

* **路径覆盖测试**

**主要特点**：设计足够的测试用例，覆盖程序中所有可能的路径。

**优点**：这种测试方法可以对程序进行彻底的测试

**缺点**：由于路径覆盖需要对所有可能的路径进行测试（包括循环、条件组合、分支选择等），那么需要设计大量、复杂的测试用例，使得工作量呈指数级增长。

> 补充，[白盒测试中的六种覆盖方法](http://www.cnblogs.com/MR-Guo/p/3449385.html)：语句覆盖，判定覆盖，条件覆盖，判定覆盖，组合覆盖，路径覆盖。


