## BDD-тестирование сервиса weatherstack
Этот проект тестирует API сервиса weatherstack при помощи BDD-сценариев. Требования представлены ниже.

**Позитивный тест** на запрос текущей погоды в четырех городах. Результаты **сравниваются с ожидаемыми значениями** из тестового набора.
Ожидаемые тестовые данные заданы заранее с соблюдением формата (например, для wind_speed, temperature и пр.).
То есть корректность результата (например, `0 <= percent_value >= 100`) не проверяется -- это позволяет иметь некоторый постоянный набор падений.
Расхождения по каждому сравнению пишутся в лог.

**Негативный тест**, получающий 4 варианта ошибок из списка API Errors, сравнивает их с ожидаемым результатом.

**Результат** выполнения тестов должен быть в отчете Allure.

### Запуск
Собрать и запустить тесты, сгенерировать стандартный отчёт:
```
$ mvn test -fn
```

Сгенерировать отчёт в Allure:
```
$ allure serve .\target\surefire-reports\
```