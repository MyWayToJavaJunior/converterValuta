Онлайн-конвертер рубль - японская йена
===============================
REST API,  позволяющее производить конвертацию “рубль - японская йена” и обратно по курсу ЦБ РФ.
онлайн-конвертер рубль - японская йена

Приложение принимает запросы и отдает ответы в следующем формате:

1. Покупка йен за рубли

Запрос: тип запроса - GET, параметр sum - сумма в рублях, положительное десятичное число с разделителем “.”, точность дробной части - 2 знака.
http://localhost:8080/yconverter/buy?sum=123.45
Ответ: JSON-формат, sum - сумма в йенах, число, формат тот же, что в запросе, status - строка, “ОК” в случае успешного ответа, “ERROR” в случае ошибки.
{ sum: 67.89, status: “OK”}

2. Продажа йен за рубли

Запрос: тип запроса - GET, параметр sum - сумма в йенах, положительное десятичное число с разделителем “.”, точность дробной части - 2 знака.
http://localhost:8080/yconverter/sell?sum=333.44
Ответ: JSON-формат, sum - сумма в рублях, число, формат тот же, что в запросе, status - строка, “ОК” в случае успешного ответа, “ERROR” в случае ошибки.
{ sum: 555.66, status: “OK”}

Курс йены запрашивается с сайта ЦБ РФ при запуске приложения и далее с периодичностью один раз в час. Полученный курс сохранять в базе данных с указанием времени его получения.
