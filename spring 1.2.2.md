
# Spring 1.2.2版本使用

## BeanFactory

### service.xml

```java
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE beans PUBLIC "-//SPRING//DTD BEAN//EN" "http://www.springframework.org/dtd/spring-beans.dtd">
<beans>
    <bean id="myBean1" class="com.kenny.spring.beans.MyBean1">
        <property name="id" value="10"/>
        <property name="name" value="hello"/>
        <property name="password" value="world"/>
    </bean>
    <bean id="myBean2" class="com.kenny.spring.beans.MyBean2"></bean>
</beans>
```

### FileSystemResource

```java
        Resource resource = new FileSystemResource("src/main/resources/service.xml");
        BeanFactory beanFactory = new XmlBeanFactory(resource);
        MyBean1 bean1 = (MyBean1) beanFactory.getBean("myBean1");
        System.out.println(bean1 == null);
```

### ClassPathResource

```java
        Resource resource = new ClassPathResource("service.xml");
        BeanFactory beanFactory = new XmlBeanFactory(resource);
        MyBean1 bean1 = (MyBean1) beanFactory.getBean("myBean1");
        System.out.println(bean1 != null);
```

### FileSystemXmlApplicationContext

```java
        ApplicationContext context = new FileSystemXmlApplicationContext("src/main/resources/service.xml");
        BeanFactory beanFactory = (BeanFactory)context;
        MyBean1 bean1 = (MyBean1) beanFactory.getBean("myBean1");
        System.out.println(bean1 != null);
```

### ClassPathXmlApplicationContext

```java
        ApplicationContext context = new ClassPathXmlApplicationContext("service.xml");
        BeanFactory beanFactory = (BeanFactory)context;
        MyBean1 bean1 = (MyBean1) beanFactory.getBean("myBean1");
        int count = context.getBeanDefinitionCount();
        System.out.println(bean1 != null);
```

### SpringBoot ConfigurableApplicationContext

```java
        ConfigurableApplicationContext context = SpringApplication.run(SbApplication.class, args);
        BeanFactory beanFactory = (BeanFactory)context;
        MyBean myBean = (MyBean) beanFactory.getBean("myBean");
        System.out.println(myBean != null);
```

## BeanFactoryPostprocessors
