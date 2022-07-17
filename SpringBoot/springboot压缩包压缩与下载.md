## springboot压缩包压缩与下载

#### 极好用的文件管理工具（新建、拷贝、删除、压缩）

https://blog.csdn.net/haixian420/article/details/89970840

#### 压缩包下载

https://www.cnblogs.com/mengzhao/p/13744541.html（'下载文件到临时文件夹'标题下的）

如果在将压缩包数据流写入到out中时没有flush则在下载后的文件打开时，会出现打开错误的提示。这里是因为每次读取一些文件的数据，就要通过flush及时写入到response中，至于为什么不能在完全写完后再flush，猜测是因为缓冲区的空间有限，如果到最后一齐flush会造成数据丢失。

