# Spring5

## Factory Method Pattern
[The Factory Design Pattern in Java](https://www.baeldung.com/java-factory-pattern)
The factory method pattern loosens the coupling code by separating our Product‘s construction code from the code that uses this Product.

## Abstract Factory Pattern
This pattern is commonly used when we start using the Factory Method Pattern, and we need to evolve our system to a more complex system. It centralizes the product creation code in one place.

## DI

## Bean Life Cycle
Container Started --> Bean Instantiated --> Dependencies Injected --> Custom init() method --> Custom utility method --> Custom destroy() method
```java
// By XML
public class Orders {
 //无参数构造
 public Orders() {
 System.out.println("第一步 执行无参数构造创建 bean 实例");
 }
 private String oname;
 public void setOname(String oname) {
 this.oname = oname;
 System.out.println("第二步 调用 set 方法设置属性值");
 }
 //创建执行的初始化的方法
 public void initMethod() {
 System.out.println("第三步 执行初始化的方法");
 }
 //创建执行的销毁的方法
 public void destroyMethod() {
 System.out.println("第五步 执行销毁的方法");
 }
}
<bean id="orders" class="com.atguigu.spring5.bean.Orders" initmethod="initMethod" destroy-method="destroyMethod">
 <property name="oname" value="手机"></property>
</bean>
 @Test
 public void testBean3() {
// ApplicationContext context =
// new ClassPathXmlApplicationContext("bean4.xml");
 ClassPathXmlApplicationContext context =
 new ClassPathXmlApplicationContext("bean4.xml");
 Orders orders = context.getBean("orders", Orders.class);
 System.out.println("第四步 获取创建 bean 实例对象");
 System.out.println(orders);
 //手动让 bean 实例销毁
 context.close();
 }
```
[Using Annotation](https://www.geeksforgeeks.org/bean-life-cycle-in-java-spring/)
