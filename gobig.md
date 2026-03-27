# Model 1 环境基础

## 1.1.任务名：基础-VMware安装与网络配置自学实操

![image-20260326101044240](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260326101044240.png)

### NAT网络ping测试

NAT为网络地址转换，用来解决IPV4地址资源短缺问题，通过修改IP报头的方式来实现将子网地址转换为其NAT网关地址，通过逐层叠加来使IP地址指数性增加。在虚拟机技术中体现为将主机作为NAT网关来实现对虚拟机内软件网络的管理，使用虚拟交换机和虚拟网卡和主机的DNS。

![image-20260326171558826](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260326171558826.png)

### 桥接网络ping测试

通过搭建虚拟网桥为主机网卡和虚拟网卡提供数据连接，使主机与虚拟机的地位平等IP同级，解决了NAT和仅主机模式中外网无法访问虚拟机的问题

![image-20260326171433566](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260326171433566.png)

### 仅主机网络ping测试

![image-20260326171317694](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260326171317694.png)

在此模式下，虚拟网卡仅绑定到宿主机，不与物理网卡连接，仅支持主机与虚拟机双向通信

## 1.2.任务名：基础-OpenSUSE Leap 15.6 Linux部署自学实操

安装遇到镜像校验失败问题，发现下载的是aarch64镜像，重新下载X86-64镜像文件成功安装，按照默认分区未发生错误

Aarch64采用精简指令集RISC，只保留最基本的机械指令，长度相等；X86-64架构采用CISC复杂指令集，指令长度不一。两者寄存器数量不一致，因此不能在同一个CPU上运行，导致镜像安装出错

> 选择光盘映像

![image-20260326183331557](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260326183331557.png)

> 选择控制器类型 scsi为一种硬盘接口

![image-20260326183558739](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260326183558739.png)

>选择磁盘

![image-20260326183935964](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260326183935964.png)

# Model 2 Linux操作系统

## 2.1.任务名：基础-Linux基础操作自学练习

任务详情：学习Linux系统核心基础（目录结构、文件权限、常用命令：ls、cd、mkdir、rm、cp、vi等），用户与组管理、系统服务启停、基础文件编辑操作，完成实操练习，记录命令使用易错点。
任务大概时间：1.5h
输出/检查项：1. 命令实操截图（每类命令至少3张，含目录管理、文件编辑、服务启停）；2. 易错点记录文档（标注命令及错误用法、正确用法）。

ls：查看当前目录下所有文档

cd：移动到制定目录下

mkdir：创建目录

rm：删除制定文件，删除目录时需要添加-r修饰

cp：复制文件到制定位置，同样复制目录时需要添加-r不添加时会出现，同时不能把目录复制到文件上

vi：创建可编辑文件

![image-20260326182432810](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260326182432810.png)

## 2.2. 基础-SSH远程管理自学实操

任务详情：学习SSH远程管理原理与优势，安装并使用SSH客户端（Xshell、Putty），配置密钥登录与密码登录，使用scp、sftp命令完成远程文件传输，独立完成远程连接Linux服务器并执行基础操作。
任务大概时间：1h
输出/检查项：1. SSH客户端安装截图；2. 密钥登录配置截图、远程连接成功截图；3. scp/sftp文件传输截图。

> 下载XShell 使用家庭/学校版

![image-20260327105221240](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327105221240.png)

> 密钥登录配置截图、远程连接成功截图

![image-20260327105409311](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327105409311.png)

![image-20260327110555805](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327110555805.png)

>  连接失败，查找原因，Linux虚拟机未开启ssh服务并设置防火墙放行->启动服务

![image-20260327131804723](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327131804723.png)

>  启动后

![image-20260327131838343](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327131838343.png)

> scp传输文件

![image-20260327132803043](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327132803043.png)

> sftp传输文件，连接失败，发现需要添加端口号并且p需要大写，否则会被防火墙拦截

![image-20260327133223736](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327133223736.png)

![image-20260327133834783](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327133834783.png)

get为下载文件，put上传文件，bye

# Model 3 网络与协议

## 3.1.任务名：基础-基础网络知识自学掌握

任务详情：学习TCP/IP协议基础、IP地址、子网掩码、网关的含义与配置，网络通信基本原理，掌握ping、telnet命令的使用及网络故障简单排查方法
任务大概时间：1h
输出/检查项：1. 网络基础知识点笔记（重点记录TCP/IP、IP地址、网关核心内容）；2. ping、telnet命令测试截图，1个简单网络故障排查案例的分析文档。

TCP/IP为计算机网络系统划分为四个层次，分为应用层、传输层（端到端）、网络层（点到点）和网络接口层。

IP地址：用来给网络上的主机唯一标识，IPV4仅有12位10进制数，IPV6有32位

子网掩码：用来标识在该局域网下网络号在IP地址中所占位数，用于区别网络位和主机位

ping是一种shell命令，用来确认主机与另一IP的连接状态，也可以使用域名访问，验证DNS服务器是否正常运行属于网络层命令

telnet用来确立本主机到某一个端口的连接，模拟HTTP请求，属于传输层命令

## 3.2.任务名：基础-HTTP协议核心知识点自学掌握

任务详情：学习HTTP协议基本概念、请求/响应流程，掌握Header、Body的组成与作用，Cookie与Token的机制（区别、使用场景、安全注意事项），使用抓包工具（如Fiddler）查看HTTP请求详情
学会如何浏览器打开开发者工具 查看网络请求
任务大概时间：1.5h
输出/检查项：1. HTTP协议知识点笔记（重点记录Header、Body、Cookie、Token）；2. 抓包工具查看的HTTP请求截图（标注Header、Body部分）。

### 	HTTP协议

* 基本概念

作为应用层协议，用于客户端与服务器端通信，实现信息交互；无状态、TCP、文本协议

* 请求/响应流程

客户端向服务器端发送TCP连接建立请求，成功后发送HTTP请求获取服务器响应，关闭或保持连接

### 	Header

是一组包含各种字段的键值对，用来描述HTTP请求、响应的各种属性和特征。分为请求头和响应头

请求头常见字段为host：指定目标服务器域名；User Agent：携带客户端（浏览器/OS）标识；Accept：可接受的响应类型；Content-Type：请求体的类型；Authorization：认证信息如token，cookie：服务器为了辨识用户身份和会话控制在客户机上缓存的一段文本数据；Referer：来源页面URL

响应头常见字段 Content-Type：响应体Body格式；Content：Body字节长；

Cookie和token都可以用来解决HTTP请求无状态的问题

Cookie机制：浏览器首次请求 → 服务器Set-Cookie → 浏览器存储 → 后续请求自动携带Cookie头，维持客户端与服务器端处于同一session中

token机制：是一种在客户端和服务端之间传递身份信息的方式，用户在登录时输入账号密码，服务器会据此生成一个token回发给客户，此后客户请求时携带token用来验证身份

# Model 4 开发工具链

## 4.1.任务名：工具-Git代码版本控制自学实操

任务详情：学习Git核心概念（仓库、分支、提交、合并），安装并配置Git（用户名、邮箱），熟练使用常用Git命令（git init、git add、git commit、git push、git pull、git branch），完成代码提交、分支创建与合并、远程仓库（GitHub/GitLab）关联的完整流程。基于公司内部gitlab，做好sshkey\token验证模式
任务大概时间：2h
输出/检查项：1. Git配置截图；2. 每一步命令执行截图（含仓库创建、提交、分支操作、远程关联）；3. 远程仓库关联成功截图。

>Git配置截图

![image-20260327114014219](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327114014219.png)

> 仓库创建与提交

![image-20260327114710386](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327114710386.png)

![image-20260327114755146](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327114755146.png)

> 分支操作

![image-20260327115057249](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327115057249.png)

> 连接到远端仓库

![image-20260327115634207](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327115634207.png)

![image-20260327115759841](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327115759841.png)

## 4.2.任务名：工具-Postman接口调试与测试自学实操

任务详情：安装并配置Postman，学习创建各类接口请求（GET/POST等）、设置请求参数与Header、查看并分析响应结果，设计简单接口测试用例并执行。
任务大概时间：1.5h
输出/检查项：1. Postman安装截图；2. 3个不同类型接口请求的创建截图、响应结果截图；3. 1份简单的接口测试用例文档及执行结果。

## 4.3. 任务名：开发-虚拟环境管理（venv+conda）自学实操

任务详情：学习虚拟环境的作用（环境隔离、依赖管理），使用venv创建、激活、退出虚拟环境，完成依赖导出/导入；安装并配置conda，使用conda创建虚拟环境、安装/卸载包，完成两种虚拟环境的实操练习。
任务大概时间：1.5h
输出/检查项：1. venv、conda虚拟环境创建、激活截图；2. 依赖导出/导入的文件及操作截图；

虚拟环境用来实现项目之间不同语言版本的差异

> 安装虚拟环境

![image-20260327145025060](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327145025060.png)

> 启动虚拟环境

![image-20260327145157716](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327145157716.png)

在虚拟环境中安装的依赖只会影响当前虚拟环境

> 依赖导出

![image-20260327150532631](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327150532631.png)

> 安装conda和虚拟环境

![image-20260327152721410](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327152721410.png)

>conda包安装

![image-20260327154906572](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327154906572.png)

>删除包

![image-20260327155043458](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260327155043458.png)

## 4.4任务名：基础-RESTful风格API交互与状态码自学掌握

任务详情：学习RESTful API的设计原则与风格，区分GET、POST、PUT、DELETE四种请求方式的区别与使用场景，牢记200、400、401、500状态码的含义与对应场景
任务大概时间：1.5h
输出/检查项：1. API交互知识点笔记（重点记录四种请求方式、核心状态码）；2. 完成3个API请求示例的分析文档（标注请求方式、状态码及含义）。

RESTful API设计原则为 无状态：每一次请求都相对独立；统一接口：采用http四个请求 GET、PUT、DELETE、POST；资源导向：所有资源都采用URI统一标识；可缓存性：所有响应都可以标注为可响应或不可响应

GET: 获取资源，POST: 向服务器提供资源, DELETE: 删除服务器资源，PUT：更新服务器资源

有幂等性：GET，DELETE，PUT

安全性：GET

200为HTTP请求和获取回应成功，400为当前请求无法被[服务器](https://baike.baidu.com/item/服务器/100571?fromModule=lemma_inlink)理解，一般为HTTP请求编写错误；401为未通过认证，由于请求头未携带认证信息或认证失败导致；403为服务器成功理解了HTTP请求但不接受，可能原因为用户权限不够或其他地区原因；500为在请求时服务器完全理解了请求但在处理请求时发生了无法预料的错误

# Model 5 数据库基础

## 5.1任务名：数据库-MariaDB数据库基础自学

任务详情：学习关系型数据库的核心概念、作用，了解常见数据库的特点，掌握存储、检索的基本原理，完成简单向量数据的插入与检索实操。
vmware中opensuse中安装，不要dockerfile安装
任务大概时间：2.5h
输出/检查项：1. MariaDB数据库知识点笔记；2. 数据插入、检索的实操截图；

## 5.2任务名：数据库-SQL语法基础（增删改查）自学实操

任务详情：学习关系型数据库基础概念、SQL核心语法，重点练习INSERT（增）、DELETE（删）、UPDATE（改）、SELECT（查）语句，完成条件查询、排序、分组、关联查询等练习。
任务大概时间：2h
输出/检查项：1. SQL语法笔记（重点记录增删改查语句）；2. 每类SQL语句的执行截图（至少各2张，含复杂查询）；3. 执行结果截图。

## 5.3任务名：数据库-关系型数据库表结构设计基础自学

任务详情：学习表结构设计原则（主键、外键、字段类型选择、约束条件），了解常见业务场景下的表结构设计思路，参照示例，设计1个简单业务表（如用户表、订单表）并优化。
任务大概时间：1.5h
输出/检查项：1. 表结构设计知识点笔记；2. 自行设计的表结构文档（含字段名、类型、约束、主键/外键）；3. 表结构优化说明文档。







# Model 6 开发实践

## 6.1任务名：开发-异步编程（FastAPI+uvicorn+async/await）自学实操

任务详情：学习python异步编程核心概念，安装FastAPI与uvicorn，掌握async/await语法，编写1个简单的异步接口并成功运行、测试。
任务大概时间：2h
输出/检查项：1. FastAPI、uvicorn安装截图；2. 异步接口代码文档；3. 接口运行成功、测试通过的截图。

## 6.2任务名：开发-异步编程（FastAPI+uvicorn+async/await）自学实操-中阶

任务详情：按命题写个简单增删改查 连接数据库的api
任务大概时间：2h
输出/检查项：1. FastAPI、uvicorn安装截图；2. 异步接口代码文档；3. 接口运行成功、测试通过的截图。

## 6.3任务名：开发-前端与交互基础（react管理端）自学

任务详情：学习React管理端的基础结构、核心组件，常用架构（如Ant Design）的安装与使用；了解前端与后端的交互逻辑。
任务大概时间：2h
输出/检查项：1. React管理端基础知识点笔记；

## 6.4任务名：开发-前端与交互基础（react管理端）自学-中阶

任务详情：构造命题管理端页面 （单页面+表单提交） 跟前面api交互
任务大概时间：1.5h
输出/检查项：1. React管理端基础知识点笔记；

## 6.5任务名：开发-前端与交互基础（gradio）自学

任务详情：学习Gradio的核心功能、构造方法，创建1个简单的Gradio交互页面，了解前端与后端的交互逻辑。
仿openui，做一个ollama的交互界面（如有问题，提出来）
任务大概时间：2h
输出/检查项：1. Gradio自行创建的交互页面截图。

## 6.6任务名：开发-前端与交互基础（浏览器插件）自学

任务详情：学习浏览器插件的开发与使用，了解前端与后端的交互逻辑。
1.制作前面react页面的列表页api数据爬取
2.模拟人类点击，前面react页面的进行数据录入（比如新增）
任务大概时间：4h
输出/检查项：1. React管理端基础知识点笔记；2. Gradio安装截图、自行创建的交互页面截图。

## 6.7任务名：开发-整体项目打包、迁移与发布流程自学实操

任务详情：学习项目打包的核心步骤（依赖整理、打包配置），不同环境（开发、测试、生产）的迁移方法，项目发布的完整流程，完成1个简单项目的打包、迁移与发布。
以前面自己写的代码为例处理下打包,vmware中opensuse构造虚拟环境，然后部署
任务大概时间：2h
输出/检查项：1. 项目打包文件；2. 迁移过程记录（含步骤截图）；3. 发布后测试通过的截图及测试报告。

