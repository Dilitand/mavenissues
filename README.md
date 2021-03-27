# mavenissues
Убираем глюки мавена



Если ошибка Execution default of goal org.springframework.boot:spring-boot-maven-plugin:1.5.9.RELEASE:repackage failed: Unable to find main class
То добавить в пом (возможно в родительский тоже нужно):


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
