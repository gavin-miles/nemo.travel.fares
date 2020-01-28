<p align="center">
    <img width="200" src="http://demo.nemo.travel/templates/wurst/f2.0/img/nemo.travel.svg">
</p>

# Fare Families
 
В директории fareFamilies содержится информация о семействах тарифов авиакомпаний с описаниями тарифных опций.
Данные сгруппированы в файлы по авиакомпаниям, код IATA используется в качестве имени файла.
Расширение файлов `.json`, формат данных `JSON`, кодировка `UTF-8`

### Структура файла тарифных правил
В файле содержится массив обьектов, каждый объект правил описывает одно семейство тарифов

**Описание семейства:**
 
| Поле        | Тип           | Описание  |
| ------------- |---------------| ------|
| owner          | String        | Двухсимвольный IATA код авиакомпании |
| baseClass      | String        |  Сервис класс перелета, к которому относится набор тарифных правил. Допустимые значения `economy`, `premiumEconomy`, `business`, `first`|
| tariffCodePattern  | String      |    Регулярное выражение, описывающее код тарифа |
| priority  | Number      | Рекомендуемый авиакомпанией порядок отображения |
| saleTimeSince  | String      |    Допустимая дата для продажи "От" (Формат ISO 8601) |
| saleTimeUntil  | String      |    Допустимая дата для продажи "До" (Формат ISO 8601) |
| flightTimeSince  | String      |    Допустимая дата вылета "От" (Формат ISO 8601) |
| flightTimeUntil  | String      |    Допустимая дата вылета "До" (Формат ISO 8601) |
| parameters| Object[] | Тарифные опции, характеризующие семейство |

**Описание тарифной опции:**

| Поле        | Тип           | Описание  |
| ------------- |---------------| ------|
| code | String | Тип (описание см. ниже) |
| shortDescription | Object | Краткое описание |
| &nbsp;&nbsp;&nbsp;&nbsp; ru | String | Описание на русском языке |
| &nbsp;&nbsp;&nbsp;&nbsp; en | String | Описание на английском языке |
| fullDescription  | Object | Расширенное описание параметра. Может использоваться, к примеру, во всплывающих подстказках |
| &nbsp;&nbsp;&nbsp;&nbsp; ru | String | Описание на русском языке |
| &nbsp;&nbsp;&nbsp;&nbsp; en | String | Описание на английском языке |
| needToPay | String \| Null | Параметр отвечающий за платность или допустимость услуги (описание см. ниже)  |

**Таблица возможных значений `code` с описаниями:**

| Имя  | Описание |
| ------------- |-------|
| description | Название и описание семейства тарифа |
| meal | Доступное питание на борту |
| baggage | Информация о регистрируемом багаже |
| carryOn | Ручная кладь |
| refundable | Правила возврата |
| exchangeable | Правила обмена |
| seatsRegistration | Информация о предоставляемых местах в самолете |
| vipService |  VIP обслуживание |

**Возможные варианты значений поля `needToPay`:**

* **null**: параметр не применим к данной тарифной опции
* **notAvailable**: услуга не доступна
* **free**: услуга доступна, является бесплатной
* **charge**: услуга доступна за дополнительную плату

### Если вы нашли ошибку

[Сообщите нам об этом](./CONTRIBUTING.md)


