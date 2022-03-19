# 欢迎来到安徽大学信息安全专业
借用 [SurviveSJTUManual](https://survivesjtu.gitbook.io/survivesjtumanual/li-zhi-pian/huan-ying-lai-dao-shang-hai-jiao-tong-da-xue) 的起始章节，在本repo的开始，我不得不遗憾地告诉大家一个消息：国内绝大部分大学的本科教学，不是濒临崩溃，而是早已崩溃。

有些同学思维一直停留在高考结束那一刻，进入大学便止步不前；有些同学缺乏合理详实的学习路线，不断踩坑失去学习CyberSecurity的兴趣；有些同学只会疯狂卷GPA，表面上成为了每门专业课都在90分以上的所谓“优等学生”，但却是个连最基本的安全技能（比如命令行下 `gdb` 调试、`elf` 文件分析、缓冲区溢出原理）都不懂的菜鸟，在虚假的 GPA 繁荣背后，是找不到工作与面试碰壁的进退维谷......四年如弹指一挥间，我希望我所走过的弯路，后人便不必再走。人人薪尽火传，有一分热，发一分光，就令萤火一般，也可以在黑暗里发一点光，不必等候炬火。


下面是一些课程的学习路线和资料收集，希望对学弟学妹有所帮助

# 漏洞分析 & 逆向工程

ym老师的漏洞分析& 逆向工程应该是计科院最硬核的课程（没有之一），很多人反映听不懂这门课程，在 ddl 前一晚通过祖传的实验报告糊弄过去，拿个及格分数就感到万事大吉。但是，请相信，这是我院含金量最高的一门课程，你的付出将会有所回报。

在做某一lab的攻击之前，你需要搞懂该攻击对应的的知识点。诚然，《计算机安全导论》这本书对于攻击原理的讲解已经足够优秀和详细，但是由于大多数同学并没有Linux基础，因此光看这本书，还是很难理解背后的机理。假设连Linux下gcc的常用命令都不懂，那么直接去做缓冲区溢出实验，这是十分荒唐的。

**一个推荐的学习路线：**

- 安装并使用Linux系统。下面提供几个方案,可以酌情选择使用：
  - [使用VMware安装Linux虚拟机](https://zhuanlan.zhihu.com/p/110128514)。你需要知道如何使用VMware新建虚拟机、使用快照备份等功能、在本机与虚拟机下使用[VMware-tools](https://www.kali.org/docs/virtualization/install-vmware-guest-tools/)完成文本与文件的复制粘贴
  - 使用双系统方案
  - 使用 [wsl2](https://docs.microsoft.com/en-us/windows/wsl/install)
  - 使用云服务器。安装云服务器，可以通过ssh在任何一个主机上连接并使用Linux环境
  - 使用[docker Linux镜像](https://hub.docker.com/_/ubuntu)。docker是一个很火的虚拟化方式，[docker hub上Ubuntu的镜像](https://hub.docker.com/_/ubuntu)已经被下载了超过十亿次
- [《鸟哥的Linux私房菜》](https://github.com/LaPhilosophie/AHU-CyberSecurity/blob/main/Linux/%E3%80%8A%E9%B8%9F%E5%93%A5%E7%9A%84Linux%E7%A7%81%E6%88%BF%E8%8F%9C-%E5%9F%BA%E7%A1%80%E7%AF%87%E3%80%8B%E7%AC%AC%E5%9B%9B%E7%89%88.pdf)
  - 这本书大而全，适合作为字典查看，比如，你要做环境变量的lab，那么除了《计算机安全导论》这本书外，你需要知道环境变量对应的基本知识点，那么，直接`ctrl + f`搜索环境变量这部分知识，会让你读《计算机安全导论》好受很多

- 自学MIT [《计算机教育中缺失的一课》](https://missing-semester-cn.github.io/)
  - 该课程列出了一些计算机专业老师不会教但是十分有用（你永远绕不开）的知识，比如shell编程、命令行、Git 版本控制、Vim 的使用等等
  - 只听这些课程是远远不够的，这门课更像是一个大纲，告诉你哪些是需要额外学习的，为了深入学习某一个章节，比如Vim，你应该学会自己找资料、配置Vim从而熟练掌握
-  [流传自远古时代的OS实验课程网站中的Linux入门教程](https://nju-projectn.github.io/ics-pa-gitbook/ics2021/linux.html)
   -  这是一个墙裂推荐的Linux自学教程
   -  想做seedlab，学好Linux的基本使用是最基本的，因此我建议在任何的lab开始之前学习好相关基本操作
- seed-lab配套网站
  - [seed主页](https://seedsecuritylabs.org/index.html)
  - [seed实验](https://seedsecuritylabs.org/Labs_20.04/)
  - [某一实验具体主页（以Shellcode 为例）](https://seedsecuritylabs.org/Labs_20.04/Software/Shellcode/)
- [ctf-wiki](https://ctf-wiki.org/)
  - ym老师的课可以概括为pwn和逆向，该网站包含了几乎ctf所有知识点，进去后点击pwn/reverse发现新世界
- [安全客](https://www.anquanke.com/)
- [FreeBuf](https://www.freebuf.com/)
# Linux
为了完成漏洞分析&逆向工程课程的学习，需要懂得一些基本的Linux知识
- 熟练掌握Linux基本命令的使用，比如使用`man`指令查询手册、`grep`指令匹配模式串、`cd`、`mv`、`cp`、`rm `、`touch`、`find`、`mkdir`、`ls`、`gcc`、`objdump`等等
- 由于Linux源码几乎全是C编写，因此你需要有比较扎实的C语言和数据结构知识，C语言之父所著的[C程序设计语言](https://github.com/LaPhilosophie/AHU-CyberSecurity/blob/main/C%E8%AF%AD%E8%A8%80%E8%BF%9B%E9%98%B6/C%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1%E8%AF%AD%E8%A8%80%20.pdf)是一本极佳的教材
- 为了完成例如缓冲区溢出的实验，你需要有扎实的汇编语言知识，详见【汇编语言】章节

**Linux的学习资源推荐：**

**[《计算机教育中缺失的一课》](https://missing-semester-cn.github.io/)**
- 大学里的计算机课程通常专注于讲授从操作系统到机器学习这些学院派的课程或主题，而对于如何精通工具这一主题则往往会留给学生自行探索
- 在这个系列课程中讲授了命令行、强大的文本编辑器的使用、使用版本控制系统提供的多种特性等等，花时间打磨使用这些工具的能力并能够最终熟练地、流畅地使用它们是非常有必要的
- 讲座视频可以在[Youtube](https://www.youtube.com/playlist?list=PLyzOVJj3bHQuloKGG59rS43e29ro7I57J)上找到

**[流传自远古时代的OS实验课程网站中的Linux入门教程](https://nju-projectn.github.io/ics-pa-gitbook/ics2021/linux.html)**
   -  这是一个墙裂推荐的Linux自学教程
   -  想做seedlab，学好Linux的基本使用是最基本的，因此我建议在任何的lab开始之前学习好相关基本操作
# C语言
很多同学认为C语言没有学习的必要，但是绝大多数同学有必要回炉重造一遍。

下面是几个最简单的C语言知识点，可以自测一下：
- 试解释以下C语言语句：
  - `void (*signal(int sig, void (*func)(int)))(int);`
  - `int (*(*(*pfunc)(int *))[5])(int *)`
- .c文件到可执行文件过程中经历了几个阶段？对这几个阶段的过程(预处理，编译，汇编，链接)分别做简要叙述
- C语言的函数调用栈过程是怎样的？如何构造缓冲区溢出攻击？

为了实现C语言进阶，请自学如下书籍：
- [C和指针](https://github.com/LaPhilosophie/AHU-CyberSecurity/blob/main/C%E8%AF%AD%E8%A8%80%E8%BF%9B%E9%98%B6/C%E5%92%8C%E6%8C%87%E9%92%88.pdf)
- [C程序设计语言](https://github.com/LaPhilosophie/AHU-CyberSecurity/blob/main/C%E8%AF%AD%E8%A8%80%E8%BF%9B%E9%98%B6/C%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1%E8%AF%AD%E8%A8%80%20.pdf)
- [C陷阱与缺陷](https://github.com/LaPhilosophie/AHU-CyberSecurity/blob/main/C%E8%AF%AD%E8%A8%80%E8%BF%9B%E9%98%B6/C%E9%99%B7%E9%98%B1%E4%B8%8E%E7%BC%BA%E9%99%B7.pdf)
- 程序员的自我修养：链接、装载与库（不要被书名骗了，这是一本C语言进阶书籍，还是比较难的）


# 汇编
首先，学校的教材是自编教材，因此质量不敢恭维。其次，学校的汇编教学十分局限，是16位汇编、实模式，且是Intel的汇编语言格式。但是众所周知，苹果自从iPhone5S发布就开始使用64位架构，且除了Intel的汇编格式外还有AT&T这种非常常见的格式。

综上，总结下来，学校的汇编教学有如下不足：
- 只教学16位汇编内容，与当今流行的64位汇编脱节
- 只教学Intel格式，更通用的AT&T格式没有教学（Linux下反汇编默认格式就是AT&T格式）
- 只教学实模式，没有教学保护模式

针对以上弊病，下面给出几本书以自学：
- 汇编语言 王爽（这本书讲了16位汇编，但是通俗易懂，比学校教材好很多）
- [x86汇编语言_从实模式到保护模式](https://github.com/LaPhilosophie/AHU-CyberSecurity/blob/main/%E6%B1%87%E7%BC%96%E8%AF%AD%E8%A8%80/x86%E6%B1%87%E7%BC%96%E8%AF%AD%E8%A8%80_%E4%BB%8E%E5%AE%9E%E6%A8%A1%E5%BC%8F%E5%88%B0%E4%BF%9D%E6%8A%A4%E6%A8%A1%E5%BC%8F(%E5%AE%8C%E6%95%B4%E6%89%AB%E6%8F%8F%E7%89%88).pdf)
- [琢石成器： Windows环境下32位汇编语言程序设计](https://github.com/LaPhilosophie/AHU-CyberSecurity/blob/main/%E6%B1%87%E7%BC%96%E8%AF%AD%E8%A8%80/%E7%90%A2%E7%9F%B3%E6%88%90%E5%99%A8%EF%BC%9A%20%20Windows%E7%8E%AF%E5%A2%83%E4%B8%8B32%E4%BD%8D%E6%B1%87%E7%BC%96%E8%AF%AD%E8%A8%80%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1.pdf)
- 深入理解计算机系统

# 保研
**保研的关键时间节点：**
- 夏令营
- 预推免
- 九推

**保研申请所需材料：**
- 个人简历
- 教授推荐信
- 比赛、奖学金、四六级证书
- 项目经历
- 论文复印件
  

**想要了解更多，请见：**
- [保研夏令营申请攻略](https://mubu.com/doc/klyrpL5cCB)
- [保研经验贴合集](https://github.com/richardodliu/CS-BAOYAN/blob/main/%E4%BF%9D%E7%A0%94%E7%BB%8F%E9%AA%8C%E5%B8%96/%E4%BF%9D%E7%A0%94%E7%BB%8F%E9%AA%8C%E8%B4%B4.md)
- [计算机类保研准备_1](https://github.com/my-style/computer-exemption)
- [计算机类保研准备_2](https://github.com/richardodliu/CS-BAOYAN)
# 密码学
# 操作系统


# GitHub 仓库推荐
# 书籍推荐

