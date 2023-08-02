# SRAF-network
В этом проекте проводится сравнительный анализ свёрточных нейронных сетей для бинарной классификации изображений. В исследуемом датасете имеется всего два класса: **"SRAF"** и **"NO SRAF"**. Цель работы состоит в том, чтобы использовать нейронные сети для автоматической классификации большого массива данных. 

## Терминология
`SRAF(от sub-resolution assist features)` - вспомогательные непечатаемые структуры, которые размещаются на топологии микросхемы
для сохранения конраста РЭМ-изображения(РЭМ - растровый электронный микроскоп) при смещении дозы или фокуса экспонирования. 

## Для чего нужна классификация? 
Заключение о пропечатке SRAF-структур при анализе большого числа изображений требует значительных временных затрат инженера-конструктора. Применение алгоритмов глубокого обучения для классификации изображений("SRAF" и "NO SRAF") позволило автоматизировать процесс фильтрации снимков, а также подобрать оптимальный порог их проявления.

## Обучение
* Для обучения использовался собственно сформированный датасет из 290 изображений, разделённый на тренировочную, валидационную и тестовую выборки в соотношении 204:52:34;
* Оптимизатор Adam с начальным learning rate равным 0.001;
* Кроссэнтропийная функция потерь;
* Аугментации: `RandomResizedCrop`, `RandomHorizontalFlip`, `Normalization`

## Результаты
Критерием достижения поставленной задачи было получения точности классификации ("accuracy") выше 90%. Модель AlexNet показала точность в 98% на валидационном датасете. Визуальная оценка предсказаний на тестовом датасете показала хороший результат. 
