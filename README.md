# config-repo 注意事项
### `eureka`的配置需要放置在`bootstrap.yml`文件中。
* 如果`eureka`使用的是默认端口8761，则将`eureka`的配置放置在统一配置中心也是可以的；
* 如果改变了`eureka`的默认端口，则必须将其配置在`bootstrp.yml`中，否则会由于连接不上`eureka`，更别说从`eureka`找到统一配置服务进而获取配置信息了；
### `XXXX.yml`文件中放公共的配置，个性化的配置放在`XXXX-dev.yml`、`XXXX-test.yml`等文件中。
* `spring-cloud-server`会先从`XXXX.yml`中获取，然后从相对应的`XXXX-dev.yml`、`XXXX-test.yml`等文件中获取配置，最后将两个配置进行合并后作为最终的配置；
* 如果两个配置文件中有重复或冲突的配置，可能会导致配置信息混乱。
