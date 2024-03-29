title: Tor
slug: tor
parent: opsec
lang: ru

Tor – это крупнейшая сеть прокси, объединенных технологией «луковой маршрутизации». Принцип ее работы в двух словах: клиент соединяется с интернетом через цепочку из независимых прокси-серверов (в терминах технологии – слоев), каждый из которых получает информацию только о следующем слое, но не знает ни о клиенте, ни о том, для чего тот использует сеть. Луковая маршрутизация позволяет обеспечить экспоненциально более высокий уровень анонимности при увеличении числа слоев, но имеет и очевидный недостаток – скорость соединения при этом тоже снижается.

Самое слабое место Tor – выходной слой, т.е. сервер, с которого трафик направляется в интернет. Если этот сервер принадлежит *недоброжелателям* – что весьма вероятно, потому что вся сеть Tor держится на добровольцах, предоставляющих свои сервера – то трафик может просматриваться и даже подменяться. Это не угроза для анонимности, но если вы, допустим, скачиваете исполняемый файл через Tor, он может быть подменен на вирус. Также возможна попытка подменить сертификат https с целью обхода шифрования, поэтому ко всем ошибкам https при использовании Tor следует относиться с большой осторожностью.

Кроме анонимного доступа к обычным сайтам (clearnet), Tor также предоставляет огромное количество внутрисетевых ресурсов (darknet), которые имеют доменную зону `.onion`: например, зеркала торрент-трекеров, интернет-библиотека Флибуста и т.д.

Есть несколько способов использования Tor. Самый простой – скачать [Tor Browser](https://www.torproject.org/ru/download/), в котором все работает "из коробки". Более универсальный способ доступен на Linux: нужно установить соответствующий пакет, следуя [этим инструкциям](https://support.torproject.org/ru/apt/tor-deb-repo/), и запустить службу Tor. После этого можно перенаправить трафик любого приложения через Tor, указав ему в качестве прокси-сервера `localhost:9050`.

А совсем ультимативный уровень анонимности можно получить, используя Tor вместе с [VPN](/pages/vpn.html). Так вы скроете от своего интернет-провайдера сам факт использования Tor, а от поставщика VPN – поток своих данных.
