http://www.importnew.com/29321.html

# 隔离级别

## 读未提交(read uncommited)

```mysql
SET GLOBAL TRANSACTION ISOLATION LEVEL READ UNCOMMITTED;
```

读取其他事务没有提交的改变，会导致**脏读**，因此实际中一般不会采用这样的隔离级别。

## 读已提交(read commited)

```mysql
SET GLOBAL TRANSACTION ISOLATION LEVEL READ COMMITTED;
```

读取其他事务提交改变后的结果，可以解决脏读的问题。但又会导致**不可重复读**，针对当前读，**RC 隔离级别保证对读取到的记录加锁 (记录锁)**

## 可重复读(repeatable read)

```mysql
SET GLOBAL TRANSACTION ISOLATION LEVEL REPEATABLE READ;
```

针对当前读，**RR 隔离级别保证对读取到的记录加锁 (记录锁)，同时保证对读取的范围加锁，新的满足查询条件的记录不能够插入 (间隙锁)**

**幻读**

除了上面提到的脏读、不可重复读，还有一种情况是幻读：在事务中，前后两次查询，记录数量是不一样的。

mysql的RR（可重复读）一并解决了幻读的问题