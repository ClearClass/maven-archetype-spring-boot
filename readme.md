## О проекте

Maven-проект архетипа SpringBoot-приложения. Основные особенности:

* архетип на основе Spring Boot 2.1.3, `spring-boot-starter-web` и `spring-boot-starter-test`; 
* простой контроллер, возвращающий текстовую строку в теле ответа;
* тестовый класс, проверяющий загрузку контекста;
* тестовый класс для контроллера на основе `MockMvc`;
* файл `application.properties` с настройкой уровня логгирования `ERROR`;
* настройка плагина компилятора для работы с Java 1.8;
* директория статических ресурсов, содержащая шаблон главной страницы `index.html`;
* сценарий запуска исполняемого архива `run.bat`.

### Версии

* Версия 1.0 - базовая версия.

## Установка
```sh
$ mvn clean install
```
Для проверки корректности установки можно воспользоваться командами:
```sh
$ mvn archetype:generate -B -DarchetypeGroupId=lib.clearclass.maven.archetypes -DarchetypeArtifactId=maven-archetype-spring-boot -DarchetypeVersion=1.0 -DgroupId=com.company -DartifactId=myproject -Dversion=1.0-SNAPSHOT -Dpackage=mypack
$ cd myproject
$ mvn package
$ java -jar target/myproject.jar
$ curl -XGET http://localhost:8080/hello
```

## Использование с Eclipse

1. Создать/обновить файл `~/.m2/archetype-catalog.xml`. Для этого перейти в каталог `~/.m2` и выполнить из него команду:
```sh
$ mvn archetype:crawl -Dcatalog=archetype-catalog.xml
```

2. Добавить в Eclipse путь к каталогу `~/.m2` (где должен находится `archetype-catalog.xml`), выполнив настройку:  
>**`Preferences->Maven->Archetypes->Add Local Catalog...`**
