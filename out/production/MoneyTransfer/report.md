 ##Отчёт о тестировании приложения "Money Transfer"
Некорректные данные на счете VIP-клиента при пополнении баланса.

**Краткое описание проведённой работы**  
  При пополнеении баланса счета на 500_000_000, сумма отобразилась в виде: -1794967296. До пополнения, на счету была сумма 2_000_000_000. Было установлено, что ошибки возникают при установленнии суммы счета более 2_147_483_647.  

**Описание тестов**
Было проведено позитивное тестирование с разными суммами пополнения счета. 
* Граничные и эквивалентные значения суммы пополнения: пополнение на 1, 500_000_001, 250_000_000
* Граничные значения типа целочисленных данных "int", в которых хранится сумма счета. Пополнение на 147_483_647, 147_483_648. 

**Результаты**  
Оформлен [баг-репорт]()  

**Общие рекомендации.**  
Пересмотреть требования к данным, на которых хранятся счета VIP-клиентов.  
По итогам тестирования, рекомендовано внести исправления в код программы. Для счетов VIP-клиентов использовать целочисленные типы данных "long", вместо используемых сейчас "int".