# 毕业设计
## 前端 ionic
#### @Viewchild()
> ionic cordova run android
> ionic g

## 后端 spring cloud
#### 通过eureka.client.registerWithEureka：false和fetchRegistry：false来表明自己是一个eureka server.
#### 
> ribbon.eureka.enabled=true #启用负载均衡
### 断路器
> 在落引用微服务架构中，根据业务来拆分成一个个的服务，服务与服务之间可以相互调用（RPC），在Spring Cloud可以用RestTemplate+Ribbon和Feign来调用。为了保证其高可用，单个服务通常会集群部署。由于网络原因或者自身的原因，服务并不能保证100%可用，如果单个服务出现问题，调用这个服务就会出现线程阻塞，此时若有大量的请求涌入，Servlet容器的线程资源会被消耗完毕，导致服务瘫痪。服务与服务之间的依赖性，故障会传播，会对整个微服务系统造成灾难性的严重后果，这就是服务故障的“雪崩”效应。
> feign.hystrix.enabled=true # 开启断路器
### compent
> @component （把普通pojo实例化到spring容器中，相当于配置文件中的<bean id="" class=""/>）
  @Component,@Service,@Controller,@Repository注解的类，并把这些类纳入进spring容器中管理。 
### 服务过滤
> filterType：返回一个字符串代表过滤器的类型，在zuul中定义了四种不同生命周期的过滤器类型，具体如下：
pre：路由之前
routing：路由之时
post： 路由之后
error：发送错误调用
filterOrder：过滤的顺序
shouldFilter：这里可以写逻辑判断，是否要过滤，本文true,永远过滤。
run：过滤器的具体逻辑。可用很复杂，包括查sql，nosql去判断该请求到底有没有权限访问。
### rabbitmq 
#### 需要将rabbitmq新增的用户授权
#### 其对应的端口号为5672 可视化端口号为15672
> POST http://localhost:8881/actuator/bus-refresh /actuator/bus-refresh?destination=customers:**” 即刷新服务名为customers的所有服务

### JPA
##### 在SQL的查询方法上面使用@Query注解，如涉及到删除和修改在需要加上@Modifying.

> 在service层调用接口的方法的方法上添加注解@Transactional进行事务的处理,然后在调用service层的方法

### maven
> https://mvnrepository.com/

### withCredentials 开启可以 使请求携带cookie

### invalid bound statement (not found)
>         <!-- 如果不添加此节点mybatis的mapper.xml文件都会被漏掉。 -->
        <resources>
            <resource>
                <directory>src/main/java</directory>
                <includes>
                    <include>**/*.properties</include>
                    <include>**/*.xml</include>
                </includes>
                <filtering>false</filtering>
            </resource>
            <resource>
                <directory>src/main/resources</directory>
                <includes>
                    <include>**/*.properties</include>
                    <include>**/*.xml</include>
                </includes>
                <filtering>false</filtering>
            </resource>
        </resources>```language

```

