#Пример запуска мавена с параметрами:  
mvn -U clean install -s settings.xml -Dspring.version=1.0.0  

-U - загрузить заново классы из репозиториев  
-s - указать где лежит файл сеттингс  
-D - присвоить значение переменной ${spring.version}  

# mavenissues  
Убираем глюки мавена  

Если ошибка Execution default of goal org.springframework.boot:spring-boot-maven-plugin:1.5.9.RELEASE:repackage failed: Unable to find main class, то добавить в пом (возможно в родительский тоже нужно):  


#<build>  
#    <pluginManagement>  
#        <plugins>  
#            <plugin>  
#                <groupId>org.springframework.boot</groupId>  
#                <artifactId>spring-boot-maven-plugin</artifactId>  
#            </plugin>  
#        </plugins>  
#    </pluginManagement>  
# </build>  


