Для того, чтобы интегрировать свои файлы из jMeter в BitBucket необходимо создать проект в IntelliJ IDEA
используя сборщик Maven, добавить плагин (из статьи ниже)
Положить в проект все тесты/файлы (*.jmx и тд) по пути - <Project Dir>/src/test/jmeter

Запуск -mvn clean verify

https://github.com/jmeter-maven-plugin/jmeter-maven-plugin
https://maven.apache.org/surefire/maven-surefire-plugin/examples/configuring-classpath.html

Запрос картинок в монго
﻿db.getCollection('news').find({"image_new_main": {'$exists' : true}}, {"image_new_main.path": 1}).limit(100)
Запрос к конкретной картинке
﻿db.getCollection('news').find({"image_new_main.path" : "335595488582577.jpeg"}, {"image_new_main.path": 1})
Запрос по выбранной дате картинок и отображением конкретного поля
﻿db.getCollection('news').find({"publish_date" : {
$gte: ISODate('2019-01-09 12:00'),
$lt: ISODate('2019-08-08 17:00')
},
"image_new_main": {'$exists' : true}
},{"image_new_main.path": 1})

Выбор нужных файлов картинок из найденного запроса в sublime
\d+.jpeg

Команды в sublime
option+вниз - выделение записей в стоблце для того, чтобы добавить пробемы/запятые или DEL (удаление пробелов) + пробел - выравнивание в столбцы