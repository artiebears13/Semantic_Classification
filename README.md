## Semantic classification

---


### Локальный запуск
1. Создать .env.local файл по аналогии с предложенным в папке `semantic/frontend/.env-sample`
2. Развернуть контейнеры:
   docker-compose up

### Техническое описание
В рамках решения кейса, команда AAA IT подготовила сервис, позволяющий по загруженным документам различного формата (pdf, xlsx, rtf, txt и прочее) определить класс документа (заявление, приказ, договор, доверенность и т.д). Подобное решение позволит компаниям снизить нагрузку на персонал, который занимается ручной валидацией документов, ускорив первый этап фильтрации.

Сервис может быть запущен на сервере в виде 3 связанных докер-контейнеров с помощью одной команды docker-compose up.

В структуре проекта реализовано 2 основные модели, дающие качество распознавания около 100%: языковая модель (более тяжелая) с самым высоким качеством и легкая модель на основе деревьев решений с качеством чуть ниже, чтобы удовлетворить разные запросы от бизнеса.

Технические особенности:
Контейнеризированный сервис, интуитивный пользовательский интерфейс на React, бекенд на FastAPI, языковая модель distilbert для инференса, возможность валидации документации по классам, выгрузки и загрузки архивов, а также обработки файлов различного формата.

Уникальность решения:
Две реализованные модели под различные запросы бизнеса, открытое API для масштабирования на новые классы, легкое дообучение моделей, работа с разными форматами, возможность сортировки загруженного архива с документами по категориям и его выгрузки пользователю.