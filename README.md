# gRPCDemo


基于官网提供的 java 示例代码，通过 Maven 构建一个 gRPCDemo。
 
官网使用 Gradlew 构建，参考地址：https://github.com/grpc/grpc-java/tree/master/examples

官网文档：http://www.grpc.io/docs/


git 拉起项目，然后执行 maven 构建命令:

```
mvn clean package
```

说明： `src/main/proto/hello_world.proto` 文件是定义 gRPC 服务的


构建完成后，gRPC 服务相关代码的生成目录： `target/generated-sources`

源码如果提示找不到定义的 gRPC 服务类，需要将生成的 `target/generated-sources/protobuf` 下的两个目录加入项目的 SourcesRoot


启动 server,在项目根目录下执行:
```
java -cp target/grpctest-1.0-SNAPSHOT-jar-with-dependencies.jar org.jpdna.grpchello.HelloWorldServer
````

控制台输出:
```
INFO: Server started, listening on 50051
```

运行测试客户端程序：
```
java -cp target/grpctest-1.0-SNAPSHOT-jar-with-dependencies.jar org.jpdna.grpchello.HelloWorldClient 
```

you sould see:
```
Nov 22, 2015 7:20:56 PM org.jpdna.grpchello.HelloWorldClient greet
INFO: Will try to greet HUBO ...
Nov 22, 2015 7:20:56 PM org.jpdna.grpchello.HelloWorldClient greet
INFO: Greeting: Hello HUBO
```

也可以直接在 Idea 中通过启动按钮启动。