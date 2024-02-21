#### Windows 下编译方法
1.下载orthancohif 源码（https://orthanc.uclouvain.be/downloads/sources/orthanc-ohif/OrthancOHIF-1.2.tar.gz）
2.下载viewers（js）源码，build出dist，为编译orthancohif 最准备
3.将build好的viewer 拷贝到OrthancOHIF-1.2\OHIF\dist目录下（如果是在linux平台步骤2、3执行脚本[../Resources/CreateOHIFDist.sh]就可以完成）这个脚本的工作就干了两件事情 1）下载viewers源码进 2）编译源码将结果拷贝到OrthancOHIF-1.2\OHIF\dist目录，这部分编译在docker进行，windows 就直接build了手动拷贝
4.cmake 配置OrthancOHIF （cmake ../ -G "Visual Studio 16 2019" -A x64 -DMSVC_MULTIPLE_PROCESSES=ON -DSTATIC_BUILD=ON -DOPENSSL_NO_CAPIENG=ON -DALLOW_DOWNLOADS=ON）
或者简单点：cmake ../ -G "Visual Studio 16 2019" -A x64 -DSTATIC_BUILD=ON -DALLOW_DOWNLOADS=ON
5.生成vs工程后打开项目进行build 即可