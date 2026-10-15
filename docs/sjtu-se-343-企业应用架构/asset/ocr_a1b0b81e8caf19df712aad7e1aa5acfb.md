+   - Lookup HelloWorldBean

```
HelloWorld hello = (HelloWorld) context.lookup("ejb:/HelloWorld//HelloWorldBean!HelloWorld.HelloWorld");
```

or

```
final String appName = "";
final String moduleName = "HelloWorld";
final String distinctName = "";
final String beanName = "HelloWorldBean";
final String viewClassName = "HelloWorld.HelloWorld";
HelloWorld hello = (HelloWorld) context.lookup("ejb:" + appName + "/" + moduleName + "/" + distinctName + "/" + beanName + "!" + viewClassName);
```