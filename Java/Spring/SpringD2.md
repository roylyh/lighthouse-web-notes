# AOP in Spring

## AOP Aspect Oriented Programming
切入点 1 执行前 2 执行后 代理模式 proxy Pattern
execution()
@annotation
5 kinds of Advice
@Before Run advice before the mothod execution  
@AfterReturning Run advice after the method execution, only if the method completes successfully
@AfterThrowing Run advice after the method execution, only if the method exits by throwing an exception
@After Run advice after the method execution, regardless of its outcome
@Around Run advice before and after the advised method is invoked. 

## Java 建议不用字符串相加
由于String对象是不可变的，在String类中每一个看起来会修改String对象内容的方法，实质都是创建了一个全新的String对象。

所以在for循环中，每次都new了一个新的String对象

频繁的新建对象会耗费很多的时间，并且造成内存的浪费。

此在循环体拼接字符串时，应该使用 StringBuilder 的append() 去完成拼接。

## Some different objects in Java
PO persistant object (database)  
VO value object 通常用于业务层之间的数据传递，和PO一样也是仅仅包含数据而已。
DAO data access object 数据访问对象 DAO中包含各种数据库的操作方法
BO business object 业务对象 通过调用DAO方法，结合PO VO进行业务操作。这个对象可以包括一个或多个其它对象。
POJO plain ordinary java object 简单无规则java对象  
DTO Data Transfer Object 数据传输对象

## Test
Unit Tests
Slice Tests
Integration Test/System Tests
(Functional Tests)
(Regression Tests)
Acceptance Tests