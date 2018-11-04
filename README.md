# config-repo
## 注意事项
* `eureka`的配置需要放置在`bootstrap.yml`文件中。
```
如果eureka使用的是默认端口8761，则将eureka的配置放置在统一配置中心也是可以的；
如果改变了eureka的默认端口，则必须将其配置在bootstrp.yml中，否则会由于连接不上eureka，更别说从eureka找到统一配置服务进而获取配置信息了；
```
* `XXXX.yml`文件中放公共的配置，个性化的配置放在`XXXX-dev.yml`、`XXXX-test.yml`等文件中。
```
spring-cloud-server会先从XXXX.yml中获取，然后从相对应的XXXX-dev.yml、XXXX-test.yml等文件中获取配置，最后将两个配置进行合并后作为最终的配置；
```
