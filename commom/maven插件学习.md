## maven plugin 学习

## appassembler 插件介绍：  
用于生成启动关闭应用的脚本，同时集成了相应的需要启动应用的依赖（当然，jdk还是要自己安装的）。它适用于linux平台、windows平台。  
使用的也是jsw的支持。  
[参考地址](https://www.jianshu.com/p/26332c0c5d92)

### maven检查包冲突的配置
~~~~
<!-- 检查包冲突的配置，参考地址：https://blog.csdn.net/z69183787/article/details/92408692 -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-enforcer-plugin</artifactId>
                <version>1.4.1</version>
                <executions>
                    <execution>
                        <id>enforce</id>
                        <configuration>
                            <rules>
                                <dependencyConvergence/>
                            </rules>
                        </configuration>
                        <goals>
                            <goal>enforce</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
~~~~~