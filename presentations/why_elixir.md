---
theme: uncover
style: |
  .small-text {
    font-size: 0.75rem;
  }
  li {
    font-size: 28px;
  }
  p.quote {
    line-height: 38px;
  }
  q {
    font-size: 32px;
    letter-spacing: 1px;
  }
  cite {
    text-align: right;
    font-size: 28px;
    margin-top: 12px;
    margin-bottom: 128px;
  }
paginate: true
footer: 'Курс по Elixir 2023, ФМИ'
marp: true

---
## Функционално програмиране с Elixir

![Image-Absolute](assets/elixir-logo.png)

---
### Кои сме ние?

* Ние ползваме Elixir в свободното си време.
* Ние ползваме професионално Elixir.
* Това е четвъртата година на курса, след 4 години без курс.
* Създаваме материали и код свързани с курса.

---
![Image-Absolute](assets/sofia_elixir.png)

---
### Кои сте вие?

* Искате да разберете защо напоследък се говори за Erlang/Elixir (в определени среди)?
* Фенове сте на Elixir/Erlang и искате да учите Elixir?
* Искате да изкарате курс от типа 'Програмиране с език...', за да си обогатите познанията?

---
### Защо да учим нов език?!

* Нали си знам PHP JAVA C# Ruby Python Това-с-което-(ще-)си-вадя-хляба?
* Тези хипстъри, дето всяка година учат нов език, за нищо не стават!
* Всяка година, не, всяка седмица нова 'технология', то не може всичко я!

---
![Image-Absolute](assets/Haters_gonna_hate.jpg)

___
## Защо да учим Elixir?

![Image-Absolute](assets/elixir-logo.png)

---
### Какво е Elixir?

* Динамично-типизиран, силно-типизиран функционален език.
* Изцяло съвместим с езика Erlang.
* Проектиран за конкурентни, толерантни на грешли и скалируеми програми.
* Свързват го с Actor модела.
* Има много мощно, просто и чисто метапрограмиране.
* Preemptive scheduling.
* Уникален начин за справяне с грешки.
* High observability.

---
### Какво е Erlang?

![Image-Absolute](assets/what_is_erlang.png)

---
### Какво е Erlang?

* Език създаден 1986.
* Целта му е да реши проблемите на телекомуникационната индустрия през 80-те.
  1. Concurrency;
  2. Scalability;
  3. Distributability;
  4. Error tolerance;
  5. Updating without service interruption;
  6. Quick response even when under high stress;
* Горе долу телекомуникационните проблеми на 80-те са web server-ните проблеми днес!

---
![Image-Absolute](assets/social_media.gif)

---
### Elixir е Erlang!

* Кодът се трансформира до Ernag-ският абстрактен формат (Erlang Abstract Format).
* След то се трансформира към byde code, който върви на BEAM виртуалната машина.
* Всички библиотеки написани на Erlang, могат да бъдат ползвани директно.

---
### Elixir е Erlang!

![Image-Absolute](assets/elixir_using_erlang.png)

---

![Image-Absolute](assets/joes_thesis.png)

---

<p class="quote"><q>You get simplicity by finding a slightly more sophisticated building block to build your theories out of.</q></p>
                                                                    <cite>Alan Kay, "Power of Simplicity", 2015</cite>
<p class="quote"><q>Simplicity is a great virtue but it requires hard work to achieve it and education to appreciate it. And to make matters worse: complexity sells better.</q></p>
                                            <cite>Edsger W. Dijkstra, "On the nature of Computer Science", 1984</cite>

---
### Функционално програмиране

![Image-Absolute](assets/functional.jpeg)

---
### Функционално програмиране

* Непроменими (immutable) данни.
* "Pure(er)" функции.
* Програмиране с трансформации вместо с мутации.
* Рекурсия вместо цикли.
* Кода е съставен и организиран от функции.
* Операторът "=" е опеаратор за съпоставяне (match operator), не е оператор за присвояване на стойност (Elixir).
* Прави кодът декларативен, което за някои хора значи - по-прост за четене и разбиране

---
### Функционално програмиране

![Image-Absolute](assets/functional_vs_what.png)

---
### Actor модела

* Математически модел за [конкурентни изчисления](https://en.wikipedia.org/wiki/Concurrent_computing), повлиян от физиката
* Появил се е с идеята да подпомага системи с висока конкурентност
* Не е имплементиран от език извън академични проекти на 100%
* [Swift Concurrency Manifest](https://gist.github.com/lattner/31ed37682ef1576b16bca1432ea9f782#introduction)

---
### Actor модела

* Всичко е Actor (подобмо на "всичко е обект").
* Един Actor може:
  * Да изпраща краен брой съобщения до други Actor-и.
  * Да създава краен брой нови Actor-и.
  * Да прави локални решения.
  * Да дефинира поведение, което ще се изпълни, кога се получи ново съобщение.
* Съобщенията се пращат асинхронно.

---
### Actor модела

![Image-Absolute](assets/actor_model.png)

---
### Actor модела

![Image-Absolute](assets/actor_model_working.png)

---
### Слоевете на Elixir

* Можем да разгледаме Elixir като език/технология от 4 слоя:
  * Функционален - Простият език, който върви вътре в процесите;
  * Конкурентен - Процесите, които вървят и си пращат собщения на една инстанция на BEAM (node);
  * Структуриран - Изграден от "поведения" и добри практики, идващи с езика, които спомагат да пишем стабилни, 99.999% online и fault-толерантни програми;
  * Дистрибутиран - Системата върви на множество node-ове и процесите в тях могат да си комуникират;

---
### Elixir не е имплемантация на Actor модела!

* Създателите на Erlang не са били запознати с Actor модела.
* Създателите на Actor модела и създателите на Erlang са били повлияни от едни и същи идеи.
* Процесите се държат в голяма степен като Actor-и.
* Вътрешността на процесите не следва Actor модела.

---
![Image-Absolute](assets/kotlin_vs_elixir.png)

---
### Конкурентност в стила на BEAM

* Блоковете за построяване на конкурентност са процесите в BEAM.
* Целият код се изпълнява в тези процеси.
* Един процес е:
  * Дефиниран на ниво виртуална машина, не го бъркайте с OS процес;
  * Много лек като заемане на памет (начално ~2kb);
  * Много лек като използване на процесорно време (да смени контекст се нужда е от 3 промени в регистрите, процес на OS ниво от към ~700);
  * Изолиран от другите процеси, има си собствен стек, хийп и кутия за съобщения;
  * Комуникира чрез асинхронни съобщения - праща и получава;

---
### Конкурентност в стила на BEAM

* Процесите се държат като Actor-и, защото могат:
  * Да пращат асинхронно съобщения;
  * Да създават нови процеси;
  * Да решават какво ще се изпълни при получаване на следващото съобщение;
  * Да получават асинхронно съобщения в кутията си за съобщения
* "Communicate by sharing state" vs "Share state by communicating"

---
### Конкурентност в стила на BEAM

![Image-Absolute](assets/beam_style.png)

---
### Amdahl’s Law

<q>Parallel programs only go as fast as their slowest sequential part</q>

![Image-Absolute](assets/amdahl.png)
