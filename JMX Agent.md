# JMX Agent

If during build you get the following error:

- `org.springframework.beans.factory.BeanCreationException: Error creating bean with name `
- `Caused by: javax.management.InstanceAlreadyExistsException:org.springframework.boot:type=Admin,name=SpringApplication`

```shell
org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'springApplicationAdminRegistrar' defined in class path resource [org/springframework/boot/autoconfigure/admin/SpringApplicationAdminJmxAutoConfiguration.class]: Invocation of init method failed; nested exception is javax.management.InstanceAlreadyExistsException: org.springframework.boot:type=Admin,name=SpringApplication
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1762) ~[spring-beans-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:593) ~[spring-beans-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:515) ~[spring-beans-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:320) ~[spring-beans-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:222) ~[spring-beans-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:318) ~[spring-beans-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:199) ~[spring-beans-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.beans.factory.support.DefaultListableBeanFactory.preInstantiateSingletons(DefaultListableBeanFactory.java:849) ~[spring-beans-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.context.support.AbstractApplicationContext.finishBeanFactoryInitialization(AbstractApplicationContext.java:877) ~[spring-context-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:549) ~[spring-context-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.refresh(ServletWebServerApplicationContext.java:142) ~[spring-boot-2.1.3.RELEASE.jar:2.1.3.RELEASE]
	at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:775) ~[spring-boot-2.1.3.RELEASE.jar:2.1.3.RELEASE]
	at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:397) ~[spring-boot-2.1.3.RELEASE.jar:2.1.3.RELEASE]
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:316) ~[spring-boot-2.1.3.RELEASE.jar:2.1.3.RELEASE]
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1260) ~[spring-boot-2.1.3.RELEASE.jar:2.1.3.RELEASE]
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1248) ~[spring-boot-2.1.3.RELEASE.jar:2.1.3.RELEASE]
	at com.oceanpremium.api.products.ProductsDriver$Companion.main(Handler.kt:42) ~[classes/:na]
	at com.oceanpremium.api.products.ProductsDriver.main(Handler.kt) ~[classes/:na]
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method) ~[na:na]
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62) ~[na:na]
	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43) ~[na:na]
	at java.base/java.lang.reflect.Method.invoke(Method.java:566) ~[na:na]
	at org.springframework.boot.devtools.restart.RestartLauncher.run(RestartLauncher.java:49) ~[spring-boot-devtools-2.1.3.RELEASE.jar:2.1.3.RELEASE]
Caused by: javax.management.InstanceAlreadyExistsException: org.springframework.boot:type=Admin,name=SpringApplication
	at java.management/com.sun.jmx.mbeanserver.Repository.addMBean(Repository.java:436) ~[na:na]
	at java.management/com.sun.jmx.interceptor.DefaultMBeanServerInterceptor.registerWithRepository(DefaultMBeanServerInterceptor.java:1855) ~[na:na]
	at java.management/com.sun.jmx.interceptor.DefaultMBeanServerInterceptor.registerDynamicMBean(DefaultMBeanServerInterceptor.java:955) ~[na:na]
	at java.management/com.sun.jmx.interceptor.DefaultMBeanServerInterceptor.registerObject(DefaultMBeanServerInterceptor.java:890) ~[na:na]
	at java.management/com.sun.jmx.interceptor.DefaultMBeanServerInterceptor.registerMBean(DefaultMBeanServerInterceptor.java:320) ~[na:na]
	at java.management/com.sun.jmx.mbeanserver.JmxMBeanServer.registerMBean(JmxMBeanServer.java:522) ~[na:na]
	at org.springframework.boot.admin.SpringApplicationAdminMXBeanRegistrar.afterPropertiesSet(SpringApplicationAdminMXBeanRegistrar.java:131) ~[spring-boot-2.1.3.RELEASE.jar:2.1.3.RELEASE]
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.invokeInitMethods(AbstractAutowireCapableBeanFactory.java:1821) ~[spring-beans-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1758) ~[spring-beans-5.1.5.RELEASE.jar:5.1.5.RELEASE]
	... 22 common frames omitted

```

Make sure you **DISABLE JMX agent** in config editor and re-run again:

![Disable.png](https://bitbucket.org/repo/qEd965M/images/147241789-Disable.png)