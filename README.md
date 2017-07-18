 
<!-- apidoc官网： http://apidocjs.com/ -->

<project>
 	<!-- 其他maven配置 -->
 	<build>
 		<plugins>
            <plugin>
                <groupId>com.cmy</groupId>
                <artifactId>apidoc-javadoc-generator-maven-plugin</artifactId>
                <version>0.0.1-SNAPSHOT</version>
                <dependencies>
                    <!-- 添加 configuration | apiSources | apiSource 这些类文件所需的依赖 -->
                </dependencies>
                <configuration>
                    <apiDocFileName>ApiDocContent</apiDocFileName><!--生成文件的文件名，默认是ApiDoc，会生成ApiDoc.java文件-->
                    <apiDocPackage>com.cmy.apidoc</apiDocPackage><!--放置生成文件的包，默认是com-->
                    <classPathDir>target\classes</classPathDir><!--项目编译后类文件的文件路径，执行插件目标前最好重编译一次项目，默认是target\classes-->
                    <apiVersion>0.0.1-SNAPSHOT</apiVersion><!--生成的javadoc里的@ApiVersion，默认是0.0.1-->
                    <apiDocDir>src\test\java</apiDocDir><!--生成文件代码的包的文件路径，默认是项目的源代码文件路径（src\main\java）-->
                    <apiSources><!--插件唯一一个没有默认配置，需要手动添加的配置，需要生成javadoc文件的源数据的类全限定名，一般是web项目的Controller-->
                        <apiSource>com.cmy.controller.XxxController</apiSource>
                        <apiSource>com.cmy.controller.ZzzController</apiSource>
                    </apiSources>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>

<project>
 	<!-- 其他maven配置 -->
    <repositories>
        <repository>
            <id>cmy-mvn-repo</id>
            <url>https://raw.githubusercontent.com/Zerojump/mvn_deploy_repo/master/repository</url>
            <releases><enabled>true</enabled></releases>
        	<snapshots><enabled>true</enabled></snapshots>
        </repository>
    </repositories>
</project>