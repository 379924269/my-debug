## maven plugin 学习

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