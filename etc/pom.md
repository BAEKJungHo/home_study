## pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.5.4.RELEASE</version>
        <relativePath/> <!-- lookup parent from repository -->
    </parent>
    <groupId>net.mayeye</groupId>
    <artifactId>core</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <name>core</name>
    <packaging>war</packaging>
    <description>MEC_CMS</description>

    <licenses>
        <license>
            <name>The Apache Software License, Version 2.0</name>
            <url>http://www.apache.org/licenses/LICENSE-2.0.txt</url>
        </license>
    </licenses>

    <properties>
        <java.version>1.7</java.version>
        <egovframework.rte.version>3.8.0</egovframework.rte.version>
    </properties>

    <!--start 전자정부 repository -->
    <repositories>
        <repository>
            <id>mvn2</id>
            <url>http://repo1.maven.org/maven2/</url>
            <releases>
                <enabled>true</enabled>
            </releases>
            <snapshots>
                <enabled>true</enabled>
            </snapshots>
        </repository>
        <repository>
            <id>egovframe</id>
            <url>http://www.egovframe.go.kr/maven/</url>
            <releases>
                <enabled>true</enabled>
            </releases>
            <snapshots>
                <enabled>false</enabled>
            </snapshots>
        </repository>
        <repository>
            <id>egovframe2</id>
            <url>http://maven.egovframe.kr:8080/maven/</url>
            <releases>
                <enabled>true</enabled>
            </releases>
            <snapshots>
                <enabled>false</enabled>
            </snapshots>
        </repository>
    </repositories>
    <!--end 전자정부 repository-->

    <dependencies>

        <!-- 전자정부 표준 프레임워크 실행환경 -->
        <dependency>
            <groupId>egovframework.rte</groupId>
            <artifactId>egovframework.rte.ptl.mvc</artifactId>
            <version>${egovframework.rte.version}</version>
            <exclusions>
                <exclusion>
                    <groupId>egovframework.rte</groupId>
                    <artifactId>egovframework.rte.fdl.logging</artifactId>
                </exclusion>
                <exclusion>
                    <groupId>commons-validator</groupId>
                    <artifactId>commons-validator</artifactId>
                </exclusion>
            </exclusions>
        </dependency>

        <dependency>
            <groupId>egovframework.rte</groupId>
            <artifactId>egovframework.rte.psl.dataaccess</artifactId>
            <version>${egovframework.rte.version}</version>
            <exclusions>
                <exclusion>
                    <groupId>egovframework.rte</groupId>
                    <artifactId>egovframework.rte.fdl.logging</artifactId>
                </exclusion>
                <exclusion>
                    <groupId>javax</groupId>
                    <artifactId>javaee-api</artifactId>
                </exclusion>
            </exclusions>
        </dependency>
        <dependency>
            <groupId>egovframework.rte</groupId>
            <artifactId>egovframework.rte.fdl.idgnr</artifactId>
            <version>${egovframework.rte.version}</version>
        </dependency>
        <dependency>
            <groupId>egovframework.rte</groupId>
            <artifactId>egovframework.rte.fdl.property</artifactId>
            <version>${egovframework.rte.version}</version>
        </dependency>
        <!-- END -->

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.mybatis.spring.boot</groupId>
            <artifactId>mybatis-spring-boot-starter</artifactId>
            <version>1.3.2</version>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-devtools</artifactId>
        </dependency>
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <scope>runtime</scope>
        </dependency>
        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <optional>true</optional>
        </dependency>

        <!--Embeded Jasper (JSP 사용)-->
        <!-- https://mvnrepository.com/artifact/org.apache.tomcat.embed/tomcat-embed-jasper -->
        <dependency>
            <groupId>org.apache.tomcat.embed</groupId>
            <artifactId>tomcat-embed-jasper</artifactId>
            <scope>provided</scope>
        </dependency>
        <!-- jstl -->
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>jstl</artifactId>
        </dependency>
        <!-- tiles 추가 -->
        <dependency>
            <groupId>org.apache.tiles</groupId>
            <artifactId>tiles-jsp</artifactId>
            <version>3.0.8</version>
        </dependency>
        <!--StringUtils3 -->
        <!-- https://mvnrepository.com/artifact/org.apache.commons/commons-lang3 -->
        <dependency>
            <groupId>org.apache.commons</groupId>
            <artifactId>commons-lang3</artifactId>
            <version>3.8.1</version>
        </dependency>
        <dependency>
            <groupId>commons-io</groupId>
            <artifactId>commons-io</artifactId>
            <version>2.5</version>
        </dependency>
        <!-- log4jdbc -->
        <!-- https://mvnrepository.com/artifact/com.googlecode.log4jdbc/log4jdbc -->
<!--        <dependency>-->
<!--            <groupId>com.googlecode.log4jdbc</groupId>-->
<!--            <artifactId>log4jdbc</artifactId>-->
<!--            <version>1.2</version>-->
<!--        </dependency>-->

        <!-- https://mvnrepository.com/artifact/org.lazyluke/log4jdbc-remix -->
        <dependency>
            <groupId>org.lazyluke</groupId>
            <artifactId>log4jdbc-remix</artifactId>
            <version>0.2.7</version>
        </dependency>


        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-tomcat</artifactId>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
<!--        <dependency>-->
<!--            <groupId>org.apache.tika</groupId>-->
<!--            <artifactId>tika-core</artifactId>-->
<!--            <version>1.20</version>-->
<!--        </dependency>-->

        <!-- 썸네일 -->
        <dependency>
            <groupId>org.imgscalr</groupId>
            <artifactId>imgscalr-lib</artifactId>
            <version>4.2</version>
        </dependency>

        <!--  Security5  -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-security</artifactId>
        </dependency>

        <dependency>
            <groupId>org.springframework.security</groupId>
            <artifactId>spring-security-test</artifactId>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>org.springframework.security</groupId>
            <artifactId>spring-security-taglibs</artifactId>
            <version>${spring-security.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework.security</groupId>
            <artifactId>spring-security-core</artifactId>
            <version>${spring-security.version}</version>
        </dependency>

        <!-- LocalDateTime -->
        <dependency>
            <groupId>joda-time</groupId>
            <artifactId>joda-time</artifactId>
            <version>2.10</version>
        </dependency>

<!--     properties config    -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-configuration-processor</artifactId>
            <optional>true</optional>
        </dependency>

<!--    jXls -->
        <dependency>
            <groupId>net.sf.jxls</groupId>
            <artifactId>jxls-core</artifactId>
            <version>1.0.6</version>
        </dependency>

<!--     암호화 -->
        <!-- https://mvnrepository.com/artifact/commons-codec/commons-codec -->
        <dependency>
            <groupId>commons-codec</groupId>
            <artifactId>commons-codec</artifactId>
            <version>1.10</version>
        </dependency>

		<dependency>
		    <groupId>commons-fileupload</groupId>
		    <artifactId>commons-fileupload</artifactId>
		    <version>1.2.1</version>
		</dependency>

    <!--   lucy filter      -->
        <dependency>
            <groupId>com.navercorp.lucy</groupId>
            <artifactId>lucy-xss-servlet</artifactId>
            <version>2.0.1</version>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>

</project>
```