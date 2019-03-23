| 设计模式     | 类型   | 归纳                   | 举例                              |
| ------------ | ------ | ---------------------- | --------------------------------- |
| 工厂方法模式 | 创建型 | 生产类的对象           | Beanfactory                       |
| 单例模式     | 创建型 | 独生子女               | Calender、ApplicationContext      |
| 原型模式     | 创建型 | 对象克隆               | BeanUtils、Cloneable、ArrayList   |
| 代理模式     | 结构型 | 找中介干活             | JdkDynamicAopProxy、CglibAopProxy |
| 委派模式     | 行为型 | 项目外包               | DispatcherServlet                 |
| 策略模式     | 行为型 | 条条道路通罗马         | ResourceLoader                    |
| 模板模式     | 行为型 | 定制流程规范           | JdbcTemplate                      |
| 适配器模式   | 结构型 | 兼容模式               | HandleAdapter                     |
| 装饰器模式   | 结构型 | 层层包装，加强原有功能 | jdk中的IO                         |
| 观察者模式   | 行为型 | 一种通知机制           | Listener                          |

列举SpringAOP、IOC、DI应用的代码片段

```java
@Aspect
public class MyInterceptor {
    @Pointcut("execution (* com.gupaoedu.patternsummary.*(..))")
    private void myMethod(){};

    @Before("myMethod()")
    public void doAccessCheck(){
        System.out.println("before");
    }

}
```

```java
@Controller
public class PersonServiceImpl implements IPersonService  {
    @Autowired
    private Person person;
    @Override
    public void save(String name) {
        person.setName(name);
        System.out.println("保存");
    }

    @Override
    public void update(String name) {
        person.setName(name);
        System.out.println("更新");
    }

}
```


	

	

