# osde - oknosoft data engine

### Предпосылки
Проект задумывался, как альтернативный лёгкий javascript клиент 1С, позволяющий читать и редактировать данные, расположенные на [сервере 1С](http://v8.1c.ru/overview/Term_000000033.htm).
Прследовались две цели:
- Не нарушая лицензионного соглашения с [фирмой 1С](http://www.1c.ru/eng/title.htm), предоставить дешевые подключения из расчета 100-300 пользователей на [сервер 1С](http://1c-dn.com/1c_enterprise/what_is_1c_enterprise/)
- Обеспечить более высокое по сравнению с традиционными клиентами 1С быстродействие за счет:
   + Отказа от избыточной для большинства проектов функциональности стандартного _клиента 1С_
   + Кеширования html5 и оптимизации вычислений на стороне браузера

### Презентации
- [Зачем это нужно](http://www.oknosoft.ru/presentations/zd_what_for.html)
- [Как это устроено](http://www.oknosoft.ru/presentations/zd_how.html)
 
### Концепция
Наиболее востребованные в реализованных ранее наших проектах функции платформы 1С:
- Эффективная модель *Метаданных* со *ссылочной типизацией* и *подробным описанием полей объектов*. Есть примеры реальных production систем 1С без единой строчки клиентского кода. Для решения большинства задач достаточно форм, которые платформа генерирует автоматически по свойствам метаданных
- Высокоуровневая объектная модель данных. Предопределенное (при необходимости, переопределяемое) поведение *Документов*, *Регистров*, *Справочников* и *Менеджеров объектов*, наличие *стандартных реквизитов* и *событий*, повышает эффективность разработки в разы по сравнению с фреймворками, оперирующими записями реляционных таблиц
 
Чтобы предоставить разработчику на javascript инструментарий, подобный 1С-ному, на верхнем уровне фреймворка osde реализованы следующие классы:
- [AppEvents](http://www.oknosoft.ru/upzp/apidocs/classes/AppEvents.html), обслуживающий события при старте программы, авторизацию пользователей и состояния сети
- [Meta](http://www.oknosoft.ru/upzp/apidocs/classes/Meta.html) - хранилище метаданных конфигурации
- [DataManager](http://www.oknosoft.ru/upzp/apidocs/classes/DataManager.html) с наследниками RefDataManager, EnumManager, InfoRegManager, CatManager, DocManager - менеджеры объектов данных - аналоги 1С-ных ПеречислениеМенеджер, РегистрСведенийМенеджер, СправочникМенеджер, ДокументМенеджер
- [DataObj](http://www.oknosoft.ru/upzp/apidocs/classes/DataObj.html) с наследниками CatObj, DocObj, EnumObj, DataProcessorObj - аналоги 1С-ных СправочникОбъект, ДокументОбъект, ОбработкаОбъект

### Благодарности
* Andrey Gershun, author of [AlaSQL](https://github.com/agershun/alasql) - Javascript SQL database library
* authors of [dhtmlx](http://dhtmlx.com/) - a beautiful set of Ajax-powered UI components
* Eli Grey for [FileSaver.js](https://github.com/eligrey/FileSaver.js)
* authors of [XLSX](https://github.com/SheetJS/js-xlsx) library
* other people for useful tools, which make our work much easier


### Лицензия
Доступ к материалам данного репозитоиря предоставляется исключительно в личных информационно-ознакомительных целях.
Воспроизведение и распространение полученных материалов запрещено. При возникновении необходимости иного использования полученных материалов, Вы обязаны обратиться к Правообладателю (info@oknosoft.ru) для заключения договора на передачу имущественных прав.

[Текст лицензии](LICENSE.ru.md)

Данная лицензия распространяется на все содержимое репзитория, но не заменяют существующие лицензии для продуктов, используемых в этой работе.

(c) 2010-2015, компания Окнософт (info@oknosoft.ru)
