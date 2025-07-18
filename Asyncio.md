# Asyncio

**Asyncio** - библиотека, работающая в одном потоке `Event Loop`. 
Требуется для решения задач типа `I\0`, т.е. задачи ввода\вывода данных

> **Yield** - используется в генераторах. Приостанавливает работу функции для возвращения значения.
Затем продолжает выполнять код

Раньше асинхронность была только для генераторов, но после 3.5 
появились `async\await`

`Корутина` - асинхронная функция

```python
import asyncio


async def func(a):  # корутина
    await a
    a+=1
```

`await` позволяет выполнить другую корутину, а после продолжить код


Код ниже показывает то, как работать с асинхронными функциями. Есть исходная функция `count`, которая приостанавливает процесс выполнения каждую 0.01 секунду.
Две другие функции - печатаю результат работы `count` каждые **1** и **5** секунд

В функции `main` объявляются переменные, функции обрабатываются через `asyncio.gather` для параллельного запуска. 
```python
import asyncio

async def count(counter: list[int]):
    print(len(counter))

    while True:
        await asyncio.sleep(1/100)
        counter.append(1)


async def print_every_sec(counter):
    while True:
        await asyncio.sleep(1)
        counter.append(1)
        print(f"- 1: {len(counter)}")


async def print_every_five_sec(counter):
    while True:
        await asyncio.sleep(5)
        counter.append(1)
        print(f"----- 5: {len(counter)}")
async def main():
    counter = []

    tasks = [
        count(counter),
        print_every_sec(counter),
        print_every_five_sec(counter)
    ]

    await asyncio.gather(*tasks)


asyncio.run(main())
```