# jarKiller
基于GO开发的一个帮助我们批量反编译满足搜索条件的组织的jar包的小工具

在我们进行代码审计或者想要反编译jar包来分析其代码的时候可能遇到以下的问题
1.在审计微服务等分布式项目时拥有大量独立jar包时
2.在代码调用了项目私有jar包时
我们通常需要去搜寻某个组织所编写的jar包，他们都拥有特定的名称，如org.apache.XXXXX
我们要从lib文件众多的jar包中提炼出特定组织的jar包并且反编译他们是一件非常重复，麻烦并且浪费时间的事情，该工具很好地解决了这一点，简单的一行代码便可以根据你提供的组织名称的一部分来确定属于该组织的所有jar包并自动反编译他们然后将源码输出到指定目录下

用法
jarKiller inputpath outputpath searchstr

jarkiller:主程序
inputpath:要扫描的目录
outputpath:反编译jar包后源码输出的目录
searchstr:搜索的目标组织名称的一部分字符串
例如：我想要扫描D:\Codes下所有来自Mengda组织的jar包并将他们反编译后的源代码全部输出到当前目录的src目录下
执行：
jarKiller D:\Codes src Mengda

注：反编译部分采用cfr-0.1.52,程序会自动在反编译代码的时候创建它并且在程序结束后销毁他，使用者不用下载cfr程序，但是必须保证java命令在环境变量中以便程序调用
垃圾代码就不开源了,目前只有windows版本,linux版本尚未编译测试
