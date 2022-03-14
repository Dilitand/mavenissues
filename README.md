#Пример запуска мавена с параметрами:  
mvn -U clean install -s settings.xml -Dspring.version=1.0.0  

-U - загрузить заново классы из репозиториев  
-s - указать где лежит файл сеттингс  
-D - присвоить значение переменной ${spring.version}  

# Рабочая реализация spring-boot
https://github.com/Dilitand/mavenissues/blob/main/pom_spring_boot.xml <br />
собирать так: mvn clean package spring-boot:repackage  <br />
запускать так: java -jar .\target\SpringForDocker-1.0-SNAPSHOT.jar <br />


# mavenissues  
Убираем глюки мавена  

Если ошибка Execution default of goal org.springframework.boot:spring-boot-maven-plugin:1.5.9.RELEASE:repackage failed: Unable to find main class, то добавить в пом (возможно в родительский тоже нужно):  

"
<build>  
    <pluginManagement>  
        <plugins>  
            <plugin>  
                <groupId>org.springframework.boot</groupId>  
                <artifactId>spring-boot-maven-plugin</artifactId>  
            </plugin>  
        </plugins>  
    </pluginManagement>  
</build>
"

Если проблема с сертификатом PKIX при импорте библиотек попробовать сбилдить с параметрами:
mvn clean package -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true




