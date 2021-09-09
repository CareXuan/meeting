# 面试问题总结1

1. nginx和php-fpm是怎么通信的？
   - 如果是127.0.0.1:9000 就是tcp socket方式进行通信 当nginx和php-fpm不在同一台机器的时候，可以通过php-fpm的ip地址和端口号进行跨服务器通信
   - 如果是php-fpm.sock 就是unix socket方式进行通信，就是通过终端进行通信，底层就是php-fpm的进程和nginx进程进行通信，这种方式配置的是php-fpm的pid文件位置，这种方式效率比tcp socket高
   - 在nginx和php-fpm配置的时候要保证都是用同一个用户和同一个组，这样不会有权限问题（一般为www-data）
2. B-Tree索引和B+Tree索引区别
   - B-Tree索引的值存在每一个节点上，B+Tree索引的值存在最底层叶子结点上
   - B+Tree的右子节点的第一个索引一定是他自己
   - B-Tree和B+Tree对于子节点都是索引值小的是左子节点，索引值大的是右子节点

