# LavaBusiness
[![PyPi Package Version](https://img.shields.io/pypi/v/lavabusiness?style=flat-square)](https://pypi.python.org/pypi/lavabusiness)
[![PyPi status](https://img.shields.io/pypi/status/lavabusiness?style=flat-square)](https://pypi.python.org/pypi/lavabusiness)
[![Supported python versions](https://img.shields.io/pypi/pyversions/lavabusiness)](https://pypi.python.org/pypi/lavabusiness)
[![License](https://img.shields.io/github/license/lztrox/lavabusiness?style=flat-square)](https://opensource.org/licenses/MPL-2.0)
[![Downloads](https://img.shields.io/github/downloads/lztrox/lavabusiness/total?style=flat-square)](https://pypi.org/project/lavabusiness/)
[![Issues](https://img.shields.io/github/issues/lztrox/lavabusiness?style=flat-square)](https://github.com/lztrox/lavabusiness/issues)
[![Documentation](https://img.shields.io/readthedocs/lavabusiness?style=flat-square)](https://lavabusiness.readthedocs.io/en/latest/)

**LavaBusiness** is an asynchronous client for Lava.ru Business-API

**LavaBusiness** это асинхронный клиент для работы с Lava.ru Бизнес-API 

## Examples
<details>
  <summary>📕 Basic usage examples</summary>
  
### Создание счета
```python
import asyncio
from LavaBusiness import AioLava

SECRET_KEY = ""
PROJECT_ID = ""

api = AioLava(SECRET_KEY, PROJECT_ID)

async def main():
    invoice = await api.create_invoice(100)
    print(f'Pay url: {invoice.url}')
    print(f'Invoice_id: {invoice.invoice_id}')

asyncio.run(main())
```
  
### Проверка статуса счета
```python
import asyncio
from LavaBusiness import AioLava

SECRET_KEY = ""
PROJECT_ID = ""

api = AioLava(SECRET_KEY, PROJECT_ID)

async def main():
    INVOICE_ID = ""
    status = await api.api.invoice_status(INVOICE_ID)

    if status == 'success':
      print('Счет оплачен')
    elif status == 'expired':
      print('Счет просрочен')
    else:
      print('Счет ожидает оплаты')
    
asyncio.run(main())
```

### Больше примеров можно найти в директории [`examples/`](https://github.com/lztrox/LavaBusiness/tree/master/examples)

### Подробная документация расположена на сайте - https://lavabusiness.readthedocs.io/en/latest/
</details>

## ✔ TODO
- [ ] EN Translation
- [ ] .kz domain support
