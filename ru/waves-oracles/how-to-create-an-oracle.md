# Как создать оракул

Waves Platform предоставляет каталог для поиска и создания карточек оракулов — [https://oracles.wavesexplorer.com](https://oracles.wavesexplorer.com). Используя сервис [Waves Oracles](/waves-oracles/about-waves-oracles.md), вы можете посмотреть, какие оракулы уже созданы другими разработчиками и какие данные они записывают в блокчейн, или, если у вас уже есть оракул, вы можете опубликовать карточку своего оракула, чтобы другие пользователи знали о ее существовании и могли пользоваться его данными.

Но создание самого опакула — микросервиса, который берет данные из какого-то источника и записывает их в блокчейн, остается за рамками сервиса Waves Oracles.

В этой статье мы на простом примере познакомим вас с полным циклом создания оракула состоящим из регистрации карточки оракула в Waves Oracles, создания и развертывания программной части оракула, а также с последующим использованием данных оракула в каких-либо [dApp](/blockchain/dapp.md).

## Пример оракула

Примером может служить dApp, которому необходимы данные курса [WAVES](/blockchain/token/waves.md) по отношению доллару США (USD) и по отношению к биткоину (BTC).

Если для выполнения dApp необходимы внешние данные, эти данные необходимо получить и сохранить в [блокчейн](/blockchain/blockchain.md), потому что dApp может получить доступ только к данным, хранящимся в блокчейне. Для получения данных из внешнего мира в блокчейн реализуются небольшие программы, которые и называются [оракулами](/blockchain/oracle.md).

Для нашего dApp требуются данные котировок, записанные в блокчейне. Поэтому мы создадим новый оракул, который будет раз в час получать соответствующие данные о котировках из публичного API Waves Data Service и сохранять их в блокчейн, и кроме того создадим карточку оракула, чтобы другие пользователи могли также использовать эти данные при необходимости в своих децентрализованных приложениях.

## Реализация программной части оракула

Создадим главную часть оракула — программу, которая получит доступ к котировкам и запишет их в хранилище данных оракула. В примере, используем для этого TypeScript с Node.js. Вы можете использовать Python или любой другой язык программирования. Смотрите список [клиентских библиотек](/waves-api-and-sdk/client-libraries.md).

### Cron

Создаем cron, который будет запускать наш сервис для получения данных из API каждый час:

``` typescript
import * as cron from 'node-cron';
import { WavesPrice } from './WavesPrice';
​
// run WavesPrice class every 1 hour
cron.schedule('0 0 */1 * * *', () => {
  new WavesPrice(logger);
});
```

### Получение данных и отправка транзакции

Создаем сам сервис, который будет запрашивать данные из API публичного Waves Data Services.

Получаем параметр _lastPrice_ из API, сдвигаем точку на нужное количество знаков и присваиваем значение соответствующему ключу:

``` typescript
lastPrice = await this.getLastprice('https://api.wavesplatform.com/v0/pairs/WAVES/Ft8X1v1LTa1ABafufpaCWyVj8KkaxUWE6xBhW6sNFJck');
dataParams.push({ key: 'waves_usd_2', value: lastPrice * Math.pow(10, 2) });

lastPrice = await this.getLastprice('https://api.wavesplatform.com/v0/pairs/WAVES/8LQW8f7P5d5PZM7GtZEBgaqRPGSzS3DfPuiXrURJ4AJS');
dataParams.push({ key: 'waves_btc_8', value: lastPrice * Math.pow(10, 8) });
```

Самый простой и правильный способ — создать новый аккаунт нового оракула. Как это сделать читайте в разделе [создание аккаунта](/waves-client/account-management/creating-an-account.md).

Подписываем [транзакцию данных](/blockchain/transaction-type/data-transaction.md) SEED от аккаунта оракула:

``` typescript
const signerDataTX = DataTX(params,'YOU ORACLE SEED HERE');
```

Отправляем подписанную транзакцию данных в блокчейн, Для [тестовой сети](/blockchain/blockchain-network/test-network.md) — [pool.testnet.wavesnodes.com](https://pool.testnet.wavesnodes.com/api-docs/index.html), для [основной сети](/blockchain/blockchain-network/main-network.md) — [https://nodes.wavesnodes.com](https://nodes.wavesnodes.com/api-docs/index.html).

``` typescript
const result = await broadcast(signerDataTX, 'https://nodes.wavesnodes.com');
```

Помните, что создание карточки оракула, а также все остальные транзакции требуют уплаты комиссии, поэтому не забудьте пополнить баланс аккаунта. Для начала вы можете попробовать создать оракул в тестовой сети.

В итоге код выглядит следующим образом:

``` typescript
import axios from 'axios';
import { data as DataTX, broadcast } from '@waves/waves-transactions';
​
​
export class WavesPrice {
​
  constructor() {
    this.start();
  }
​
  private async getLastprice(url: string): Promise<number> {
    const data = (await axios.get(url)).data.data;
    return data.lastPrice;
  }
​
  private async broadcastTX(dataParams) {
    const params = {
      data: dataParams
    };
​
    const signerDataTX = DataTX(params,'YOU ORACLE SEED HERE');
    const result = await broadcast(signerDataTX, 'https://nodes.wavesnodes.com');
  }
​
  public async start() {
    try {
      let dataParams = [];
      let lastPrice = 0;
​
      lastPrice = await this.getLastprice('https://api.wavesplatform.com/v0/pairs/WAVES/Ft8X1v1LTa1ABafufpaCWyVj8KkaxUWE6xBhW6sNFJck');
      dataParams.push({ key: 'waves_usd_2', value: lastPrice * Math.pow(10, 2) });
​
      lastPrice = await this.getLastprice('https://api.wavesplatform.com/v0/pairs/WAVES/8LQW8f7P5d5PZM7GtZEBgaqRPGSzS3DfPuiXrURJ4AJS');
      dataParams.push({ key: 'waves_btc_8', value: lastPrice * Math.pow(10, 8) });
​
      await this.broadcastTX(dataParams);
    } catch(err) {
      console.log(err);
    }
  }
}
```

### Зависимости проекта

Описываем зависимости проекта:

``` typescript
{
  "name": "balance-oracle",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "axios": "0.19.0",
    "node-cron": "2.0.3",
    "@waves/waves-transactions": "3.16.3"
  },
  "scripts": {
    "start": "tsc ./project/src/app.ts && node ./project/src/app.js"
  },
  "devDependencies": {
    "@types/node": "^11.11.3"
  }
}
```

## Запуск оракула

Для начала установите Node.js, если он ещё не установлен: [https://nodejs.org/en](https://nodejs.org/en).

Устанавливаем зависимости проекта:

``` bash
$ npm install
```

Если не устанавливали TypeScript, нужно установить его глобально:

``` bash
$ npm install -g ts-node typescript
```

Теперь запускаем наш оракул:

``` bash
$ npm run start
```

В [Waves Explorer](/waves-explorer/about-waves-explorer.md) мы видим транзакцию с данными котировок в том формате, в котором хотели (рис. 1):

<img src="img/5_transaction_in_explorer.png" width="700">

_Рисунок 1_.

## Создание карточки оракула

Чтобы другие пользователи знали о нашем оракуле, используем Waves Oracles для создания карточки оракула.

Waves Oracles использует расширение [Waves Keeper](/waves-keeper/about-waves-keeper.md).

Для создания карточки оракула используйте тот же аккаунт, который указывали для подписания транзакций в коде.

Перейдите в Waves Oracles, авторизуйтесь в Waves Keeper и нажмите кнопку Create an oracle на боковой панели (рис.2).

<img src="img/1_create_an_oracle.png" width="700">

_Рисунок 2_.

В появившейся форме необходимо заполнить информацию об оракуле.

Назовем наш оракул "WAVES/USD and WAVES/BTC" и выбираем соответствующую категорию "Market data & exchange rates", чтобы его можно было быстро найти. Указываем статус "Production", т.к. оракул уже работает и доступен. В поле About даем небольшое описание оракула и принципах его работы. Так как оракул обновляет данные котировок каждый час — указываем это в поле Update frequency.

Верхняя часть формы показана на рис. 3.

<img src="img/2_create_an_oracle_popup_form_fill.png" width="700">

_Рисунок 3_.

Спускаемся ниже, где заполняем спецификацию и пример.

В нашем случае оракул должен записывать два значения котировок: WAVES/USD и WAVES/BTC. Поэтому мы определяем эти два параметра, как показано на рис. 4.

Здесь нужны некоторые пояснения: dApp на [RIDE](/ride/about-ride.md) не может использовать значение с плавающей запятой (float), поэтому мы используем целочисленный тип (integer) со сдвигом точки на необходимое количество знаков. В ключе указываем количество знаков, на которое смещается точка: для USD на два знака, для BTC на восемь знаков. Таким образом будет легко парсить такие ключи с помощью RIDE и понимать, на сколько именно символов необходимо смещать точку.

Также отметим, что такой ключ не является уникальным и в [хранилище данных аккаунта](/blockchain/account-data-storage.md) всегда будет сохраняться только последнее значение. Вы можете добавить метку времени (timestamp), чтобы сделать каждый ключ уникальным, и таким образом сохранять исторические данные.

<img src="img/3_create_an_oracle_popup_form_fill_specification.png" width="700">

_Рисунок 4_.

После заполнения формы, подтвердите транзакцию данных создания карточки оракула в Waves Keeper, нажатием Approve. Как только вы это сделали, новая карточка оракула успешно зарегистрирована в Waves Oracles. Протокол карточки оракула можно увидеть в Waves Explorer (см. рис. 5). Через некоторое время карточка также появится в интерфейсе Waves Oracles.

<img src="img/4_oracle_card_explorer.png" width="700">

_Рисунок 5_.

## Использование данных оракула

Поздравляем, теперь наш оракул полностью готов. После сохранения  данных в блокчейн, все dApp на RIDE могут получить к ним доступ (используя методы _getInteger()_, _getString()_, _getBinary()_ и _getBoolean()_) и использовать для своих расчетов, например, определения размера выплат, отправки транзакций, определения победителей конкурса и т.д.

В нашем случае, например, для получения из оракула данных по курсу пары WAVES/BTC, нужно в методе _getInteger()_ указать адрес оракула и соответствующий ключ:

``` ride
getInteger("3PPTrTo3AzR56N7ArzbU3Bpq9zYMgcf39Mk", "waves_btc_8")
```
