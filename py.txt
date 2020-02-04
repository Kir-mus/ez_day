import random
from time import sleep

eat = {-1: 'бутер, кофе', 0: 'кофек, кашка', 1: 'супчик, хлебушек', 2: 'шот сладкое', 3: 'макарошки с пюрешкой',
       4: 'шо хочу я заслужил!'}
time_eat = ['09:00', '12:00', '17:00', '18:00', '22:00']
work = ['08:00', '12:00', '15:00', '21:00']
sleept = '00:00'
time = ''
if random.randint(0, 1) == 1:
    time = '07:00'
    print('проспал на час время ' + time + ' НАДО СПЕШИТЬ\n')
    for i in range(4):
        sleep(2.4)
        time = time_eat[i]
        print(time)
        if time_eat[i] == work[i]:
            print('покушать во время работы, {}'.format(eat[i - 1]))
        else:
            print('покушать.. {}'.format(eat[i]))
        time = work[i]
        print('работа..', time)
        print('--------------------------------\n')
        if time == '21:00':
            print('пора домой...')
            sleep(2.4)
            print('можно покушать ' + eat[i])
            time = time_eat[i + 1]
            sleep(2.4)
            print(sleept)
            print('можно и спать\nZ..z..z.z')
else:
    time = '06:00'
    print('проснулся в ' + time, ' \n')
    for i in range(4):
        sleep(2.4)
        time = time_eat[i]
        print(time)
        if time_eat[i] == work[i]:
            print('покушать во время работы, {}'.format(eat[i]))
        else:
            print('покушать, {}'.format(eat[i]))
        time = work[i]
        print('работа..', time)
        print('--------------------------------\n')
        if time == '21:00':
            print('пора домой...')
            sleep(2.4)
            print('можно покушать ' + eat[i + 1])
            k = input('что ты хочешь? ')
            print(k + '..вкускно ~~~')
            time = time_eat[i + 1]
            sleep(2.4)
            print(sleept)
            print('можно и спать\nZ..z..z.z')
