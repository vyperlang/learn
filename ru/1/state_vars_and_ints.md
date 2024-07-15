<!-- Add translation for the following page: https://learn.vyperlang.org/#/1/state_vars_and_ints
Do NOT change the code below. The below code runs the code editor -->

# Глава 2: Переменные состояния, целые числа и константы

Отличная работа! Теперь, когда у нас есть оболочка для нашего контракта, давайте узнаем, как Vyper работает с переменными.

Переменные состояния неизменно хранятся в хранилище контрактов. Это означает, что они записаны в блокчейне Ethereum. Думайте о них как о записи в БД.

## Пример

```vyper
# @version> = 0.2.4 <0.3.0

# Это будет храниться в блокчейне неизменно
storedData: int128
```

В этом примере контракта мы создали `int128` с именем `storedData`, который содержит значение _по умолчанию_ `1`.

## Беззнаковые целые числа: `uint256`

Тип данных `uint256` - это целое число без знака (256 бит), то есть его значение должно быть неотрицательным.

Также существует тип данных `int128` (128 бит) для целых чисел со знаком (тип для хранения положительных и отрицательных целых чисел).

## Пример

```vyper
# @version> = 0.2.4 <0.3.0

# Это создает константу uint256 со значением 10
TEN: constant(uint256) = 10
```

В этом примере контракта мы создали `константу` `uint256` с именем `TEN` и установили ее равной `10`.

## Давайте проверим это

ДНК Покемонов будет определяться 16-значным числом.

В области кодирования справа объявите `константу` `uint256` с именем `DNA_DIGITS` и установите ее равной `16`.

<!-- tabs:start -->

#### ** Template **

[embedded-code](../../assets/1/1.2-template-code.vy ':include :type=code embed-template')

#### ** Solution **

[embedded-code-final](../../assets/1/1.2-finished-code.vy ':include :type=code embed-final')

#### ** Previous Chapter Solution **

[embedded-code-previous](../../assets/1/1.1-finished-code.vy ':include :type=code embed-previous')

<!-- tabs:end -->
