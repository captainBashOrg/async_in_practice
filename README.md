async def start_strongman(name, power):
    print(f'Силач {name} начал соревнования. Его сила {power}')
    for i in range(1, 6):
        print(f'Силач {name} поднял {i}')
        await asyncio.sleep (1/power) # имитация задержки
    print(f'Силач {name} закончил соревнования.')


async def start_tournament():
    task1 = asyncio.create_task(start_strongman ('Pasha', 3) )
    task2 = asyncio.create_task(start_strongman ('Denis', 4) )
    task3 = asyncio.create_task(start_strongman ('Apolo', 50) )
    await task1
    await task2
    await task3

async def main():
    print("Beginning!")
    await start_tournament()
    print("Finishing!")

if __name__ == '__main__':
    asyncio.run(main () )
