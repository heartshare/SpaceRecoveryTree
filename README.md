# SpaceRecoveryTree
数据库的空间回收策略，MySQL, Mongodb, Redis, Memcache, Cache, Disk


<pre>
MySQL
      InnoDB
           InnoDB存储引擎对于已经删除掉额数据只是标记为删除，并不真正释放所占用的磁盘空间
      ，这就导致InnoDB数据文件不断增长。

      如果在创建数据库的时候设置 innodb_file_per_table = 1， 这样InnoDB会对每个表建立数
      据文件，然后只需要运行OPTIMIZE TABLE命令就可以释放所有已经删除的磁盘空间，释放空间，并整理文件。

      如果没有设置这个参数，又想彻底释放这些已经删除的数据，需要把数据库导出，删除InnoDB数
      据库文件，然后再导入。

OPTIMIZE TABLE 命令只对 MyISAM 、 BDB 和 InnoDB 表起作用

表优化的工作对提高表的访问效率有一定的好处，但是需要注意的是，优化表期间会锁定表，所以一定要在空闲的时候进行。
</pre>


