# Purpose

演示[Spring Boot Logging](https://docs.spring.io/spring-boot/docs/current/reference/html/howto-logging.html)在Spring Cloud环境下如何通过Apollo配置中心方便地实现动态调整Logging Level

# Instructions

1. 在Apollo配置中心创建AppId为`spring-cloud-logger`的项目
2. 在默认的`application`下做如下配置（可以通过文本模式直接复制、粘贴下面的内容）：

    ```properties
    logging.level.com.ctrip.framework.apollo.use.cases.spring.cloud.logger = warn
    ```
3. 运行`com.ctrip.framework.apollo.use.cases.spring.cloud.logger.Application`启动Demo
4. 程序只会持续打印error级别日志
5. 在Apollo配置中心修改配置，把`logging.level.com.ctrip.framework.apollo.use.cases.spring.cloud.logger`的值改为`debug`并发布配置
6. 程序会输出debug, info, warn, error等级别日志，说明动态调整Logging Level生效了
