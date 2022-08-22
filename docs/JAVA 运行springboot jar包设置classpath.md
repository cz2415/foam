Java 命令行提供了如何扩展bootStrap 级别class的简单方法.

-Xbootclasspath: 完全取代基本核心的Java class 搜索路径.不常用,否则要重新写所有Java 核心class
-Xbootclasspath/a: 后缀。将classpath添加在核心class搜索路径后面。常用!!
-Xbootclasspath/p: 前缀。将classpath添加在核心class搜索路径前面.不常用,避免引起不必要的冲突.


 

//特定的jar到classpath
java -Xbootclasspath/a:/usrhome/thirdlib1.jar:/usrhome/thirdlib2.jar -jar yourJarExe.jar
//添加目录到classpath
java -Xbootclasspath/a:/usrhome/thirdlib1/:/usrhome/thirdlib1/ -jar yourJarExe.jar
//添加当前目录（可执行的jar所在的目录）到classpath
java -Xbootclasspath/a:./ -jar yourJarExe.jar
添加当前目录（可执行的jar所在的目录）到classpath

java -Xbootclasspath/a:./ -jar yourJarExe.jar