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