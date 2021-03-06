---
tags: ["kovri"]
terms: ["Garlic-Encryption", "Layered-Encryption", "чесночного-шифрования", "чесночное-шифрование", "Чесночное-шифрование", "чесночным-шифрованием", "многоуровневое-шифрование", "Многоуровневое-шифрование", "чесночную-службу"]
summary: "Многоуровневое шифрование, реализованное в Kovri / I2P"
---

### Основная информация

@Чесночное-шифрование является @I2P реализацией @сообщения, в основе которой лежит @многоуровневое-шифрование (подобно потоковому [луковому шифрованию](https://en.wikipedia.org/wiki/Onion_routing)).

@Шифрование @сообщений по уровням позволяет направить @сообщение по маршруту, состоящему из последовательности прокси-узлов. При этом такие прокси-узлы (или любые другие посредники) не смогут прочитать содержание @сообщения. @Многоуровневое-шифрование является фундаментальной особенностью  @Kovri, @I2P и [Tor](https://torproject.org), а также краеугольным камнем обеспечения анонимности в пределах этих оверлейных сетей.

### Углублённая информация

В случае с @чесночным-шифрованием основное различие между @Kovri / @I2P и Tor заключается в следующем:

- @Kovri / @I2P связывает вместе множество @сообщений, формируя "чесночные зубки"
  - такой "зубок" может содержать *любое* количество сообщений, а не только одно единственное
- @Kovri / @I2P использует [ElGamal](https://en.wikipedia.org/wiki/ElGamal) / [AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) @шифрование @сообщений и @транспортного уровня.

### Примечание

Более подробная информация содержится в статье @чесночная-маршрутизация.
