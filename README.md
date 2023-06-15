# Blog

## 14.06.23

How learning F# changed the way I think about programming

👋 Hi everyone! I recently completed a course on functional programming using F#, and I want to share my experience and thoughts about this language. F# is a universal programming language for writing succinct, robust and performant code. It is based on OCaml, and belongs to the ML family of languages. It is open source, cross-platform and interoperable with other .NET languages.

👉 Here are some of the key takeaways from my learning journey:
- Functional programming develops the ability to design programs correctly. For example, elite universities like Oxford prefer F# or Haskell as the first programming language. Learning F# helped me to structure my code better and avoid unnecessary complexity.
- The main skill that I acquired was the ability to think recursively, step by step reducing the problem to an elementary form. Interestingly, because of the fact that when writing a recursive function you have to use it itself to write the algorithm, you always have to first understand what it should do in the end, and only then implement it. This skill improved my problem-solving abilities and made me more confident in tackling challenging tasks.
- Thanks to the combination of pattern matching and recursion, functions in F# are very concise, easy to read and understand. Also, it is harder to make a mistake in F# code (less code - less errors 😊), because F# has a strong type system, which allows you to set such constraints that are impossible to implement in popular programming languages today. Writing concise and expressive code in F# made me appreciate the beauty and elegance of functional programming.
- F# is not a pure functional language, it gives you the opportunity to write in an object-oriented or imperative style if necessary, which simplifies its application in real projects. Learning F# showed me how different concepts can be used to solve the same problem, and how to choose the best one for each case.

🚀 Finally, I have some plans for the future in the field of programming in F#. Usually F# is not used to write projects entirely, but only separate modules that you want to make purely functional, and use this language in conjunction with other .NET languages. At the moment I am considering the possibility of learning C# and getting closer acquainted with backend development, then maybe in the future I will be able to apply F# in practice.

## 30.01.22

Продолжаю баловаться нейросетями) Последние 2 недели разбирался с библиотекой глубокого обучения Keras, запилил нейросетку-бота для игры в го (китайские шашки такие). В качестве датасета сам себе нагенерировал игр методом Монте-Карло и скормил их нейросети. Простой перцептрон предсказал правильный ход в 2,5% случаев, а вот сверточная нейросеть показала уже 8% точности при вероятности случайного угадывания 1,2%.  Честно говоря, думал что нейросеть покажет результат получше, наверное большая часть ошибки кроется в некачественных обучающих данных: хоть алгоритм Монте-Карло и выдает более-менее осмысленные ходы, все-таки они получается довольно случайными. Позже попробую скачать данные с какого-нибудь игрового сервера, результат должен быть сильно лучше)

Пока писал нейросеть, познакомился с кучей новых технологий:
-	библиотека Keras, которая позволяет делать очень сложные вещи очень простым способом. Пока писал нейросеть с нуля, получил нокаут математикой от одного только алгоритма обратного распространения ошибки в плотных слоях, эту же тему в сверточных слоях я бы точно не пережил.
-	библиотека Tensorflow, которая трудится под капотом у Keras, может за минуту обучить нейросеть, которая в ином случае может обучаться несколько часов. Оптимизация происходит на всех уровнях – программном, аппаратном и даже математическом (используются продвинутые техники вычислений с тензорами). Пришлось правда разобраться с зависимостями и накатить пару служебных библиотек по несколько гигов каждая, но это того стоило.
-	Познакомился с новыми видами слоев, функциями активации и функциями ошибки для нейросети. Кажется, теперь эта тема стала для меня еще интереснее, чем когда я только начал ей заниматься.
-	Хоть это и забавно, но пока писал нейросети, узнал кое-что новое и о языке Python: познакомился с парсером аргументов командной строки, которого мне раньше сильно не хватило, и который в будущем точно буду использовать)

С 1 февраля записался на курс по машинному обучению от ods.ai, следующие 3 месяца буду заниматься им, а потом - пробовать свои силы на Kaggle)


## 10.01.22

Решил тут с нового года заняться наконец изучением машинного обучения, а то уже долго откладываю это дело на потом. Год назад даже с работы уволился чтобы серьезно в эту тему вкатиться, но потом фронтенд засосал меня обратно) Хочу в ближайшие несколько месяцев освоить базовые штуки в ML, чтобы пойти на Kaggle и попробовать взять там какие-нибудь медальки. Буду писать сюда что узнал нового/интересного раз в неделю, надеюсь это меня немного дисциплинирует)

На новогодних праздниках сидел читал как сделать простую последовательную нейросеть с нуля, без использования библиотек. Первое что бросилось в глаза -  алгоритмы, используемые в ML, отличаются от алгоритмов в классическом программировании тем, что для понимания их работы обязательно нужно понимать математику, которая лежит в их основе. В основе алгоритмов классического программирования тоже лежит математика, но для повседневной работы ничего кроме, наверное, О-нотации знать не обязательно. С алгоритмами машинного обучения ситуация совершенно иная: без понимания математической модели невозможно понять, что делает тот или иной кусок кода. Например, для обновления параметров сети после очередного прохода данных нужно проделать следующую эквилибристику: для выбранной функции ошибки (в моем случае – среднеквадратическая ошибка), посчитать производную в точке, чтобы определить градиент многомерной поверхности, на которой мы ищем точку с минимальным значением, и чтобы передать эту информацию всем слоям обратно по сети, нужно продифференцировать градиент еще по разу на каждом слое. В коде все это реализуется парой несложных формул, глядя на которые невозможно понять, что они делают) Хорошо, что я уже после института немного занимался математикой: смотрел курсы по статистике, дискретной математике, мат. анализу, но все равно с дифференцированием немного застрял. В итоге запилил нейросетку для распознавания рукописных цифр. С задачей справляется на троечку, и обучается на процессоре очень долго. На этой неделе почитаю про сверточные нейросети для улучшения работы с изображениями и про библиотеку Keras, с помощью нее можно обучать модель на GPU, это должно исправить ситуацию.
