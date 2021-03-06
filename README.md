# построение пути и навигации
## Реализации алгоритма A-Star
### О проекте:
Домашний проект по курсу "Искусственный интеллект".
Задача проекта: реализовать алгоритм A-Star

### Структура проекта:
1. В основной каталог проекта входят:
* Каталог Materials с материалами к объектам
* Каталог Prefabs с префабами проекта
* Каталог Scripts с программными реализациями проекта
2. В каталоге Scripts содержатся:
* Файл AStarAlgorithm: непосредственная реализация алгоритма A-Star
* Файл GenerationRules: описание всех динамических реализаций проекта (создание плоскости, узлов и препятствий)
* Файл NodeElement: структура узла
* Файл PriorityQueue: реализация очереди с приоритетом

### Описание работы проекта:
При запуске проекта на сцене есть только 5 объектов: камера, свет, Source, Nodes и Obstacles.
Nodes и Obstacles являются родительскими объектами для узлов и препятствий (во время динамической генерации).
Source - ключевой объект проекта с основными настройками.
![screen1](/Screen/1.png)

При запуске проекта на сцене сгенерируются необходимые объекты. И найдется путь от стартовой точки в конечную. В консоли будет оповещение о том, что путь найден.
![screen2](/Screen/2.png)

Через несколько секунд в определенные узлы упадут препятствия, которые символизируют перекрытие пути. Чтобы перестроить путь необходимо нажать кнопку **Пробел**. Тогда итоговый путь будет выглядеть иначе и в консоли появиться второе новое оповещение.
![screen3](/Screen/3.png)

Также запуск проекта можно осуществить заведомо с поиском несуществующего пути. Для этого на объекте Source необходимо выбрать mode = 2
![screen4](/Screen/4.png)

Тогда в консоли появиться сообщение, что путь не был найден, и маршрут не будет проложен
![screen5](/Screen/5.png)

Препятствия можно выкладывать вручную. Для удобства можно на объекте Source поставить mode = 3. Тогда тестовые препятствия не будут появляться.
Для изменения координат стартовой и конечной точек, необходимо задать новые значения соответствующих полей на объекте Source.
![screen6](/Screen/6.png)

## Обновление 1: 
1. Добавлен скрипт FlyCamera: управление камерой 
2. Добавлен скрипт PHB: попытка реализовать очередь с приоритетом в виде binary heap. Скрипту требуется доработка. Пока что он не используется.
3. Добавлены объекты terrain. Настройка через объект Source. Они могут заменить объект Floor.
4. В программной реализации алгоритма А* теперь учитывается высота нахождения нода при построении пути. 
5. Добавлены новые взаимодействия с клавиатурой: 
* Q - вернуть ноды на высоту генерации
* Z - сгенерировать определенные объекты препятствия
###### Ознакомительное видео [YouTube](https://youtu.be/ePpGRwC8Rgw)
