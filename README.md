[![Build status](https://ci.appveyor.com/api/projects/status/vpejhcsy5avwgc7w/branch/main?svg=true)](https://ci.appveyor.com/project/Gnucheva/ci-appveyor/branch/main)

Общая схема работы выглядит следующим образом: CI должен запустить целевой сервис в фоновом режиме (который вы и тестируете) и ваши авто-тесты. Для этого мы будем на этот раз использовать возможности Bash.    
Для того, чтобы запустить целевой сервис есть несколько вариантов, самый простой из которых - положить jar-файл прямо в ваш репозиторий. Когда AppVeyor будет выкачивать исходники авто-тестов, он выкачает и ваш сервис.    
Ваш целевой сервис (SUT - System under test), расположен в файле `app-mbank.jar` (в проекте с лекции). Вам нужно его положить в каталог `artifacts` вашего проекта (создайте его).   
Поскольку файлы с расширением `.jar` находятся в списках `.gitignore`б вам нужно принудительно заставить git следить за ними: `git add -f artifacts/app-mbank.jar`.    
После чего сделать `git push`. Обязательно удостоверьтесь, что файл попал в репозиторий.   
