{% assign version = '1.1.0' | split: '.' %}
{% include disclaimer.html translated="true" version=page.version %}
### Содержание

* [1. Windows](#1-windows)
* [2. Mac OS X](#2-mac-os-x)
* [3. Linux](#3-linux)
* [4. Final notes](#4-a-few-final-notes)

### 1. Windows

Сначала мы должны убедиться, что мы достаточно подготовлены. Это влечет за собой следующее:

1. В этом руководстве предполагается, что вы уже инициализировали свой Ledger кошелек и, таким образом, создали мнемоническую seed-фразу из 24 слов.

2. Вам нужно запустить / использовать клиент CLI версии v0.12.2.0 или новее, который можно скачать <a href="{{site.baseurl}}/downloads/">здесь</a>.

3. Вам необходимо установить приложение Ledger Monero и настроить свою систему. Инструкции можно найти [здесь](https://github.com/LedgerHQ/blue-app-monero/blob/master/doc/user/bolos-app-monero.pdf) в частности, разделы 3.1.1 и 3.2.3). Кроме того, убедитесь, что сеть переключена в `Mainnet`

4. Ваш Ledger должен быть подключен, и приложение Ledger Monero должно работать.

5. Ваш демон (`monerod.exe`) должен корректно работать и быть полностью синхронизированным, либо вы должны подключиться к удаленной  ноде.

Теперь, когда мы подготовлены, давайте начинать!

1. Перейдите в каталог / папку где находятся файлы monerod.exe и monero-wallet-cli.exe.

2. Откройте cmd / powershell. Убедитесь, что ваш курсор не находится ни на одном из файлов, затем нажимается SHIFT + ПКМ (щелчок правой кнопкой мыши). Это даст вам возможность "Open command window here" (Открыть окно командной строки здесь). Если вы используете Windows 10, это даст вам возможность "open the PowerShell window here" (Открыть окно PowerShell здесь).

3. Введите:

`monero-wallet-cli.exe --generate-from-device <new-wallet-name> --subaddress-lookahead 3:200` (Win 7 + 8)

`.\monero-wallet-cli.exe --generate-from-device <new-wallet-name> --subaddress-lookahead 3:200` (Win 10)

Обратите внимание, что <new-wallet-name> это параметр для фактического имени кошелька. Если вы, например, хотите назвать свой кошелек `MoneroWallet`, то команда будет следующей:

`monero-wallet-cli.exe --generate-from-device MoneroWallet --subaddress-lookahead 3:200` (Win 7 + 8)

`.\monero-wallet-cli.exe --generate-from-device MoneroWallet --subaddress-lookahead 3:200` (Win 10)

4. CLI после выполнения вышеупомянутой команды запросит пароль. Обязательно установите надежный пароль и подтвердите его.

5. Ledger спросит, хотите ли вы экспортировать приватный ключ просмотра. Прежде всего, стоит понимать, что ваши средства не могут быть скомпрометированы только с помощью приватного ключа просмотра. Экспорт приватного ключа просмотра позволяет клиенту (на компьютере - Monero v0.12.2.0) сканировать блоки, принадлежащие вашему кошельку / адресу. Если этот параметр не используется, устройство (Ledger) сканирует все блоки, что будет значительно медленнее. Однако есть одно предостережение - если приватный ключ просмотра экспортирован и ваша система будет скомпрометирована, злоумышленник потенциально сможет нанести ущерб вашей конфиденциальности. Это практически невозможно, если ключ приватного просмотра не экспортируется в Ledger.

6. Возможно, вам потребуется дважды подтвердить операцию, прежде чем начнется процесс.

7. Теперь будет создан ваш Ledger Monero кошелек. Обратите внимание, что это может занять до 5-10 минут. Кроме того, следует понимать, что немедленной синхронизации с CLI и с Ledger не будет.

8. `monero-wallet-cli` начнет обновлять данные. Подождите, пока он полностью не закончит.

Поздравляем, теперь вы можете использовать Ledger Monero кошелек совместно с CLI.

### 2. Mac OS X
Сначала мы должны убедиться, что мы достаточно подготовлены. Это влечет за собой следующее:

1. В этом руководстве предполагается, что вы уже инициализировали свой Ledger кошелек и, таким образом, создали мнемоническую seed-фразу из 24 слов.

2. Вам нужно запустить / использовать клиент CLI версии v0.12.2.0 или новее, который можно скачать <a href="{{site.baseurl}}/downloads/">здесь</a>.

3. Вам необходимо установить приложение Ledger Monero и настроить свою систему. Инструкции можно найти [здесь](https://github.com/LedgerHQ/blue-app-monero/blob/master/doc/user/bolos-app-monero.pdf) в частности, разделы 3.1.1 и 3.2.3). Кроме того, убедитесь, что сеть переключена в `Mainnet`

4. Обратите внимание на то, что инструкции по конфигурированию системы (раздел 3.2.2) в Mac OS X достаточно сложны и могут восприниматься как слегка запутанные. К счастью, tficharmers создал простое и понятное руководство, которое находится [здесь](https://monero.stackexchange.com/questions/8438/how-do-i-make-my-macos-detect-my-ledger-nano-s-when-plugged-in). Вы можете воспользоваться им, если у вас возникнут проблемы.

5. Ваш Ledger должен быть подключен, и приложение Ledger Monero должно работать.

6. Ваш демон (`monerod.exe`) должен корректно работать и быть полностью синхронизированным, либо вы должны подключиться к удаленной  ноде.

Теперь, когда мы подготовлены, давайте начинать!

1. Используйте Finder для перехода в каталог / папку где находится `monero-wallet-cli` (CLI v0.12.2.0).

2. Перейдите на рабочий стол.

3. Откройте окно терминала (если вы не знаете, как открыть терминал, ознакомьтесь со следующим руководством [здесь](https://apple.stackexchange.com/a/256263)).

4. Перетащите папку с `monero-wallet-cli` в терминал. Он должен добавить полный путь к окне терминала. Не нажимайте enter.

5. Введите:

`--generate-from-device <new-wallet-name> --subaddress-lookahead 3:200`

Обратите внимание, что <new-wallet-name> это параметр для фактического имени кошелька. Если вы, например, хотите назвать свой кошелек `MoneroWallet`, то команда будет следующей:

`--generate-from-device MoneroWallet --subaddress-lookahead 3:200`

Обратите внимание, что вышеупомянутый текст будет добавлен к полному пути `monero-wallet-cli`. Таким образом, прежде чем вы нажмете enter, ваш текст в окне терминала должен выглядеть следующим образом:

`/full/path/to/monero-wallet-cli --generate-from-device <new-wallet-name> --subaddress-lookahead 3:200`

Где полный путь - это фактически путь к каталогу на вашем Mac OS X.

7. CLI после выполнения вышеупомянутой команды запросит пароль. Обязательно установите надежный пароль и подтвердите его.

8. Ledger спросит, хотите ли вы экспортировать приватный ключ просмотра. Прежде всего, стоит понимать, что ваши средства не могут быть скомпрометированы только с помощью приватного ключа просмотра. Экспорт приватного ключа просмотра позволяет клиенту (на компьютере - Monero v0.12.2.0) сканировать блоки, принадлежащие вашему кошельку / адресу. Если этот параметр не используется, устройство (Ledger) сканирует все блоки, что будет значительно медленнее. Однако есть одно предостережение - если приватный ключ просмотра экспортирован и ваша система будет скомпрометирована, злоумышленник потенциально сможет нанести ущерб вашей конфиденциальности. Это практически невозможно, если ключ приватного просмотра не экспортируется в Ledger.

9. Возможно, вам потребуется дважды подтвердить операцию, прежде чем начнется процесс.

10. Теперь будет создан ваш Ledger Monero кошелек. Обратите внимание, что это может занять до 5-10 минут. Кроме того, следует понимать, что немедленной синхронизации с CLI и с Ledger не будет.

11. `monero-wallet-cli` начнет обновлять данные. Подождите, пока он полностью не закончит.

12. Поздравляем, теперь вы можете использовать Ledger Monero кошелек совместно с CLI.

### 3. Linux
Сначала мы должны убедиться, что мы достаточно подготовлены. Это влечет за собой следующее:

1. В этом руководстве предполагается, что вы уже инициализировали свой Ledger кошелек и, таким образом, создали мнемоническую seed-фразу из 24 слов.

2. Вам нужно запустить / использовать клиент CLI версии v0.12.2.0 или новее, который можно скачать <a href="{{site.baseurl}}/downloads/">здесь</a>.

3. Вам необходимо установить приложение Ledger Monero и настроить свою систему. Инструкции можно найти [здесь](https://github.com/LedgerHQ/blue-app-monero/blob/master/doc/user/bolos-app-monero.pdf) в частности, разделы 3.1.1 и 3.2.3). Кроме того, убедитесь, что сеть переключена в `Mainnet`

4. Ваш Ledger должен быть подключен, и приложение Ledger Monero должно работать.

5. Ваш демон (`monerod.exe`) должен корректно работать и быть полностью синхронизированным, либо вы должны подключиться к удаленной  ноде.

Теперь, когда мы подготовлены, давайте начинать!

1. Перейдите в каталог / папку где находятся файлы monerod.exe и monero-wallet-cli.exe.

2. Откройте новое окно терминала

3. Введите:

`./monero-wallet-cli --generate-from-device <new-wallet-name> --subaddress-lookahead 3:200`

Обратите внимание, что <new-wallet-name> это параметр для фактического имени кошелька. Если вы, например, хотите назвать свой кошелек `MoneroWallet`, то команда будет следующей:

`./monero-wallet-cli --generate-from-device MoneroWallet --subaddress-lookahead 3:200`

4. CLI после выполнения вышеупомянутой команды запросит пароль. Обязательно установите надежный пароль и подтвердите его.

5. Ledger спросит, хотите ли вы экспортировать приватный ключ просмотра. Прежде всего, стоит понимать, что ваши средства не могут быть скомпрометированы только с помощью приватного ключа просмотра. Экспорт приватного ключа просмотра позволяет клиенту (на компьютере - Monero v0.12.2.0) сканировать блоки, принадлежащие вашему кошельку / адресу. Если этот параметр не используется, устройство (Ledger) сканирует все блоки, что будет значительно медленнее. Однако есть одно предостережение - если приватный ключ просмотра экспортирован и ваша система будет скомпрометирована, злоумышленник потенциально сможет нанести ущерб вашей конфиденциальности. Это практически невозможно, если ключ приватного просмотра не экспортируется в Ledger.

6. Возможно, вам потребуется дважды подтвердить операцию, прежде чем начнется процесс.

7. Теперь будет создан ваш Ledger Monero кошелек. Обратите внимание, что это может занять до 5-10 минут. Кроме того, следует понимать, что немедленной синхронизации с CLI и с Ledger не будет.

8. `monero-wallet-cli` начнет обновлять данные. Подождите, пока он полностью не закончит.

Поздравляем, теперь вы можете использовать Ledger Monero кошелек совместно с CLI.

### 4. Несколько заключительных замечаний

Мы настоятельно рекомендуем сначала протестировать полный процесс. То есть отправьте небольшое количество монет на кошелек и затем восстановите его (используя вышеупомянутое руководство). Обратите внимание, что после создания / восстановления кошелька вы должны добавить флаг `-restore-height` (с высотой блока до совершения вашей первой транзакции на кошелек) к команде на шаге 3 (Windows), шаге 5 (Mac OS X) или шаге 3 (Linux). Более подробную информацию о высоте восстановления и порядке ее масштабирования можно найти [здесь](https://monero.stackexchange.com/questions/7581/what-is-the-relevance-of-the-restore-height).

2. Если вы используете удаленную ноду, добавьте флаг `-daemon-address host:port` к команде на шаге 3 (Windows), шаге 5 (Mac OS X) или шаге 3 (Linux).

3. При желании вы можете вручную настроить значение `--subaddress-lookahead`. Первое значение - это количество учетных записей, а второе значение - количество субадрессов на одну учетную запись. Таким образом, если вы хотите, создать 5 учетных записей со 100 субадрессами, используйте `--subaddress-lookahead 5: 100`. Имейте в виду, что чем больше субадрессов вы создаете, тем больше времени уйдет на то, чтобы Ledger сгенерировал ваш кошелек.

4. Вам нужно только один раз использовать флаг -generate-from-device (т. е. при создании кошелька). После этого вы можете воспользоваться им точно так же, как в CLI. То есть:
   1. Убедитесь, что ваш Ledger включен, а приложение Monero запущено.
   2. Откройте `monero-wallet-cli`.
   3. Введите имя вашего Ledger Monero кошелька.
   4. Введите пароль, чтобы открыть кошелек.

   Если файлы кошелька Ledger находятся не в том же каталоге, где располагается `monero-wallet-cli`, вы должны открыть файл `monero-wallet-cli` с флагом `-wallet-file /path/to/wallet.keys/file`. Вы можете скопировать файлы кошелька Ledger в тот же каталог, что и `monero-wallet-cli`.

5. Если у вас есть дополнительные вопросы или вам нужна помощь, пожалуйста, оставьте комментарий к оригинальному ответу на [StackExchange](https://monero.stackexchange.com/questions/8503/how-do-i-generate-a-ledger-monero-wallet-with-the-cli-monero-wallet-cli).

Автор: dEBRUYNE
Редактор: el00ruobuob
