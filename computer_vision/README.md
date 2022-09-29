## **Цель проекта:**

Построить модель, которая по фотографии определит приблизительный возраст человека. В нашем распоряжении набор фотографий людей с указанием возраста. Необходимо построить модель со значением метрики качества MAE не больше 8.

В представленных нам исходных данных содержалась 7591 фотография с отмеченным на ней возрастом. Фотографии были разного качества, так же был скос распределения возрастов в сторону среднего возраста 20-40 лет. Нам требовалось построить такую модель, которая может предсказывать возраст покупателей по фото с требуемой целевой метрикой MAE не выше 8.

Наша нейронная сеть, построенная на архитектуре ResNET, c применённой дополнительной аугментацией в виде горизонтального отображения дала результат MAE = 6, что полностью удовлетворяет предъявленным требованиям.

<p><u><b>Добавление V1</b></u></p>

Перед нами ставились две бизнес-задачи:
 - 1) Анализировать покупки и предлагать товары, которые могут заинтересовать покупателей этой возрастной группы


 Полученная метрика MAE=6 позволяет нам произвести категоризацию клиентов по возрастным группам. Так возрастные группы в большинстве своем разбиты на рамки в 10-15 лет. Например, дети 0-18, молодежь 19-35, средний возраст 36-55, пенсионеры 55+. Более точную градацию категорий возрастов должны устанавливать маркетологи и аналитики для конкретных групп товаров, но МАЕ=6 позволяет им это сделать с большой долей точности и репрезентативности.


 - 2) Контролировать добросовестность кассиров при продаже алкоголя.


 По законодательству нашей страны, при продаже алкоголя лицам не достигшим 18 лет, накладываются существенные штрафы как физическому лицу, то есть непосредственно продавцу, так и юридическому лицу - магазину. Определять возраст клиента при покупке алкоголя только при помощи этой нейросети конечно не стоит, потому что ответственность всегда на человеке, нейросеть не отштрафуешь. Именно поэтому у кассиров за кассой кроме жирной пометки: Пакет! Акционные товары! Всегда есть еще надпись "Паспорт и дата рождения ниже которой идут возраста, который на текущий момент старше 18 лет. И поэтому в некоторых спорных случаях спрашивают и у клиентов 30+.

 Но проверять добросовестность продавцов избирательно конечно можно, просто категорезировать возраст покупателей до 30 лет и директору или старшему продавцу, или менеджеру выборочно проверять на записях камер, о том проверяют ли их продавцы паспорт у клиентов в группе "молодежь" при продаже алкоголя. Так можно выборочно проверять соблюдают ли сотрудники действующее законодательство РФ и внутреннние правила магазина.