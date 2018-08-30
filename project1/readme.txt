eureka-client是服务提供者 8762
eureka-client2是服务提供者2 8763
eureka-server是服务注册中心 8761
eureka-feign是服务消费者的一种 8765
eureka-feign2是服务消费者的一种(开启了断路器) 8767
erueka-ribbon是服务消费者的一种 8764
erueka-hystrix是断路器 8766
erueka-hystrix2是断路器(集成Hystrix Dashboard (断路器：Hystrix 仪表盘)) 8768
erueka-zuul是服务网关 8769 Zuul的主要功能是路由转发和过滤器。路由功能是微服务的一部分，比如／api/user转发到到user服务，/api/shop转发到到shop服务。zuul默认和Ribbon结合实现了负载均衡的功能。
erueka-config-model 分布式配置中心组件(模块 包括config-server 和config-client)


启动顺序
1.server
2.client
3.feign ribbon

访问
1.监控中心
http://localhost:8761/

2.feign远程调用效果
http://localhost:8765/hi?name=dong

3.ribbon远程调用效果
http://localhost:8764/hi?name=dongbao

4.hystrix远程调用效果(关闭client服务提供者后,熔断效果显现)
http://localhost:8766/hi?name=dongbao

5.feign2远程调用效果(开启了断路器)
http://localhost:8767/hi?name=dongbao

6.hystrix2是断路器(集成Hystrix Dashboard)
访问--http://localhost:8768/hystrix
输入--http://localhost:8768/hystrix.stream
访问--http://localhost:8768/hi?name=dongbao

7.erueka-zuul是服务网关,调用效果
http://localhost:8769/api-a/hi?name=forezp
http://localhost:8769/api-b/hi?name=forezp
增加过滤器之后
http://localhost:8769/api-a/hi?name=forezp
http://localhost:8769/api-a/hi?name=forezp&token=2

8.erueka-config-client 分布式配置中心组件,调用效果
启动子model server 8888和 子model client 8881
访问http://localhost:8881/hi

