# Jitsi SRTP

+ [jitsi-srtp：使用Maven和CMake进行Java继续性集成](https://github.com/jitsi/jitsi-srtp/actions/workflows/build.yml)
+ [jitsi-srtp：代码覆盖率](https://codecov.io/gh/jitsi/jitsi-srtp)
+ [jitsi-srtp：Maven中央仓库](https://search.maven.org/artifact/org.jitsi/jitsi-srtp)
+ [jitsi-srtp：API文档](https://javadoc.io/doc/org.jitsi/jitsi-srtp)

Jitsi SRTP包含了用于加密和解密SRTP和SRTCP数据包的类。

## 构建Java修改

要避免构建所有native库，请执行`resources/fetch-maven.sh`，从Maven中央仓库的最新版本中下载并提取native库。

## 构建native库

Jitsi SRTP包含了native库，用于加快加密/解密的速度。发布到[Maven中央仓库](https://search.maven.org/artifact/org.jitsi/jitsi-srtp)的构件包含了为Ubuntu的OpenSSL 1.1/3预构建的二进制文件。

**咨询更详细的构建说明之前，请先查看GitHub Actions构建。**

### Ubuntu

先决条件：
+ OpenJDK 11（或更新版本）
+ Maven
+ Docker

运行`mvn compile`，生成JNI头文件；然后运行`resources/ubuntu-build-all.sh`。这个脚本会为每个架构和OpenSSL版本创建Docker镜像。

### Mac

先决条件：
+ OpenJDK 11（或更新版本，期望的架构）
+ XCode
+ CMake
+ Maven
+ OpenSSL（期望的版本和架构）

运行`mvn compile`，生成JNI头文件；然后运行`resources/mac-cmake.sh`。
