# Микросервис конвертирования HTML-файлов в PDF
Тестовое задание на вакансию junior node js developer в компанию JetStyle

* Реализация микросервиса на основе Express.js
* В качестве логера использован простой .json файл, для простого примера логирования запросов. На деле в продакшен проекте прибегну к использованию настоящей базы данных.
* Сервер стартует на порту :5001 и принимает POST запрос по маршруту /upload содеражащий в теле "по первому (любому) ключу!" файл в формате .zip (формат файла валидируется и при не соответсвии запись заносится в лог).
* На выходе, при успешном выполнении операции, получаем json с сообщением "complete" или данными об ошибке (Только если обращаемся по корректному маршруту!)
* Так же реализована валидация на размер загружаемого файла, составляющая 2gb
* Основная логика работы: 
  - Полученный файл сохраняется в папку upload в корне проекта, под новым уникальным именем (дабы избежать конфликта имен загруженных файлов)
  - После чего распаковывается в папке temp.
  - по средством wkhtmltopdf (в виде готового npm решения "p.s: Можно было реализовать при помощи child_process обращение к приложению на прямую, что было бы более корректно") происходит конвертирование HTML документа
  по обращению к файлу index.html
  - При успешном выполнении операции в лог заносится запись содержащая: метку времени, статус выполнения, имя входного файла, имя файла .pdf, затраченные время\память (по заданию так понял физическую, на хранение и распаковку)
  - Временные файлы .zip и распакованная версия удаляются, остается только .pdf в папке ./data
* Docker на практике применять не приходилось, но основную концепцию просмотрел и понял. .Dockerfile собран по гайдам)
  
p.s: 
- Во-первых огромное спасибо за предоставленную возможность попробовать свои силы и за данный мне шанс :)
- Имею огромное желание учиться (за прошедший год освоил огромную базу в плане программирования, и в частности разработки в сфере веб)
- Ваша вакансия для меня откроет дорогу в мир того, чем я хочу заниматься всю жизнь, и уже уверен в своем призвании :)
- Имею навык быстро обучаться и обещаю приложить все силы, чтобы оправдать ваши ожидания!

The project was prepared by Maxim Khamitov, specially for JetStyle.
