---
id: move-stake
title: Перенос стейка
description: Перемещение вашего пакета в сети polygon
keywords:
  - docs
  - polygon
  - matic
  - stake
  - move stake
  - validator
  - delegator
slug: move-stake
image: https://wiki.polygon.technology/img/polygon-wiki.png
---
import useBaseUrl from '@docusaurus/useBaseUrl';

## Перенос стейка из нодов Polygon Foundation во внешние ноды {#moving-stake-from-foundation-nodes-to-external-nodes}

<video loop autoplay width="100%" height="100%" controls="true" >
  <source type="video/mp4" src="/img/staking/MoveStakeDemo.mp4"></source>
  <source type="video/quicktime" src="/img/staking/MoveStakeDemo.mov"></source>
  <p>Ваш браузер не поддерживает этот видеоэлемент.</p>
</video>

Делегатам теперь предоставляется возможность перенести стейк из нодов Polygon Foundation в любые внешние ноды по выбору с помощью функции Move Stake (перенести стейк) в пользовательском интерфейсе стейкинга.

Перенос стейка из нода Polygon Foundation во внешний нод выполняется за одну транзакцию. Поэтому задержек и периодов отвязки во время такого события не предусмотрено.

Обращаем внимание, что переносить стейк можно только из нода Polygon Foundation во внешний нод. Если вы хотите перенести стейк из внешнего нода в другой внешний нод, сначала вам нужно осуществить отвязку, а потом делегировать средства в этот внешний нод.

Move Stake (перенести стейк) — это временная функция. Она разработана специалистами Polygon для беспрепятственного переноса средств из нодов Polygon Foundation во внешние ноды. Эта функция будет работать, пока не будут отключены ноды Polygon Foundation.

## Способы переноса стейка {#how-to-move-stake}

Чтобы перенести стейк, сначала вам нужно будет войти в интерфейс [Staking,](https://wallet.polygon.technology/staking) используя ваш адрес делегата.

**Адрес** делегата: адрес, который вы уже использовали для стейкинга в нодах Фонда.

После входа в систему вы увидите список валидаторов.

<img src={useBaseUrl("img/staking/validator-list.png")} />

Теперь перейдите в профиль делегата, нажав на кнопку **Детали делегата Показать** или параметр **сведений о моем** Delegator слева.

<img src={useBaseUrl("img/staking/show-delegator-details.png")} />

Здесь вы найдете новую кнопку под названием **Move Stake**.

<img src={useBaseUrl("img/staking/move-stake-button.png")} />

Нажав ее, вы перейдете на страницу со списком валидаторов, которым можно делегировать средства. Делегировать средства можно любому валидатору в этом списке.

<img src={useBaseUrl("img/staking/move-stake-validator.png")} />

Теперь после выбора валидатора, которого вы хотите делегировать, нажмите на кнопку **«Здесь** делегировать». Нажмите на эту кнопку откроет всплывающее окно.

<img src={useBaseUrl("img/staking/stake-funds.png")} />

Здесь вы увидите поле **Сумма,** которое автоматически заполнит всю сумму для Делегирования. Делегировать валидатору также можно часть средств.

Например, если вы делегировали 100 токенов MATIC ноду 1 Polygon Foundation и сейчас хотите перенести стейк из нода Polygon Foundation во внешний нод, вы можете делегировать часть средств внешнему ноду на ваш выбор, например, 50 токенов MATIC. Оставшиеся 50 токенов MATIC будут по-прежнему находиться в ноде 1 Polygon Foundation. Затем вы можете делегировать оставшиеся 50 токенов другому внешнему ноду или тому же самому внешнему ноду.

После ввода суммы вы можете нажать на кнопку **Stake Funds**. Затем будет запрошено подтверждение подписания адреса на MetaMask.

После подписания транзакции ваш стейк будет перенесен из нода Polygon Foundation во внешний нод. Однако, чтобы увидеть его в пользовательском интерфейсе стейкинга, потребуется дождаться 12 подтверждений блоков. Если перенесенные средства не отображаются после 12 подтверждений блоков, попробуйте обновить страницу, чтобы увидеть новые стейки.

Если у вас появятся вопросы или возникнут проблемы, вы можете отправить запрос в службу поддержки [здесь](https://support.polygon.technology/support/home).
