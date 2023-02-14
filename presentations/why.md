---
theme: uncover
style: |
  .small-text {
    font-size: 0.75rem;
  }
  code.language-elixir {
    background: #000;
    color: #f8f8f8;
  }
  span.hljs-comment,
  span.hljs-quote,
  span.hljs-meta {
    color: #7c7c7c;
  }
  .hljs-keyword,
  .hljs-selector-tag,
  .hljs-tag,
  .hljs-name {
    color: #f96a6a;
  }
  .hljs-attribute,
  .hljs-selector-id {
    color: #ffffb6;
  }
  .hljs-string,
  .hljs-selector-attr,
  .hljs-selector-pseudo,
  .hljs-addition {
    color: #a8ff60;
  }
  .hljs-subst {
    color: #daefa3;
  }
  .hljs-regexp,
  .hljs-link {
    color: #e9c062;
  }
  .hljs-title,
  .hljs-section,
  .hljs-type,
  .hljs-doctag {
    color: #f0f05b;
  }
  .hljs-symbol,
  .hljs-bullet,
  .hljs-variable,
  .hljs-template-variable,
  .hljs-literal {
    color: #ffc57a;
  }
  .hljs-number,
  .hljs-deletion {
    color:#ff73fd;
  }
  .hljs-emphasis {
    font-style: italic;
  }
  .hljs-strong {
    font-weight: bold;
  }
  li {
    font-size: 32px;
  }
paginate: true
footer: 'Курс по Elixir 2023, ФМИ'
backgroundImage: "linear-gradient(to bottom, #E0EAFC, #CFDEF3)"
marp: true

---
## Функционално програмиране с Elixir

---
![Image-Absolute](assets/elixir-logo.png)

---
### Кои сме ние?

* Ние ползваме Elixir в свободното си време.
* Ние ползваме професионално Elixir.
* Това е третата година на курса.
* Създаваме материали и код свързани с курса.  

---
![Image-Absolute](assets/sofia_elixir.png)

---
![Image-Absolute](assets/bulgaria_elixir.png)

---
### Кои сте вие?

* Искате да разберете защо напоследък се говори за Erlang/Elixir (в определени среди)?
* Фенове сте на Elixir/Erlang и искате да учите Elixir?
* Искате да изкарате курс от типа 'Програмиране с език...', за да си обогатите познанията?

---
### Кои сте вие?

* Искате да запишете курс от типа 'Програмиране с език...' за лесни кредити?
* Като чуете 'Функционално програмиране' си представяте типови системи и монади???

---
### Защо да учим нов език?!

* Нали си знам PHP JAVA C# Ruby Python Това-с-което-(ще-)си-вадя-хляба?
* Тези хипстъри, дето всяка година учат нов език, за нищо не стават! 
* Всяка година, не, всяка седмица нова 'технология', то не може всичко я!

---
![Image-Absolute](assets/Haters_gonna_hate.jpg)

---
### Защо да учим Elixir?

* Всички твърдения от предния слайд са вярни. Не всичко работи за всички.
* Няма сребърен куршум, но за всичко си има набор от добри инструменти.
* Дайте шанс и време на този набор от инструменти?

---
### Какво е Elixir?

* Elixir е език, който върви на BEAM.
* BEAM e виртуалната машина на Erlang. 
* Ахаа! Значи нещо като Scala, както се отнася към Java? 
* И да, и не. 
* Elixir е Erlang. Но и нещо повече.

---
### Какво е Erlang?

![Image-Absolute](assets/what_is_erlang.png)

---
### Erlang е създаден с цел: писане на телеком програми

* Конкурентни (едно устройство трябва да може да поддържа хиляди едновременни транзакции).
* Толерантни към грешки и проблеми - както софтуерни, така и хардуерни. 
* Практически нулев downtime. 
* Кодът им трябва да може да се заменя с по-нови версии, докато той работи. 

---
#### А какви проблеми имаме днес?
![Image-Absolute](assets/internet.jpeg)

---
![Image-Absolute](assets/fun1.jpg)

---
![Image-Absolute](assets/fridge.jpg)

---
![Image-Absolute](assets/social_media.gif)

---
Joe Armstrong (създател на Erlang) нарича Erlang "език за конкурентно-ориентирано програмиране".

---
#### То се базира на няколко правила.!

* Кодът върви в процеси, които са на ниво език.
* Тези процеси не споделят памет - имат собствен стек и собствен heap.* Много а евтини за създаване и си комуникират чрез размяна на съобщения.* Лесно могат да си комуникират помежду си, дори да са на различни машини.
* Ако един процес 'умре', другите продължават да живеят. Може нов да го замести, зависи от стратегията.

---
### Erlang върви на BEAM

* BEAM е способна да използва всички ядра на процесора без проблем.
* BEAM-level процесите са много малки 1KB-2KB при създаването си.
* Можем да създаваме огромен брой процеси без да се притесняваме. Говорим за милиони. 
* Scheduler-ите на BEAM използват стратегия, различна от стратегиите в други езици - превантивна стратегия. 

---
### Let it CRASH!!!
![Image-Absolute](assets/let_it_crash.jpg)

---
### Кой ползва Erlang?
* Amazon - за базата данни SimpleDB
* Yahoo! - за URL bookmarking 
* WhatsApp - написана на Erlang, real-time съобщения, купена от Facebook 

---
### Кой ползва Erlang?
* T-Mobile, Motorola, Ericsson - за SMS услуги и 3G/4G мрежи. Ericsson са създатели на Erlang.
* RabbitMQ - AMQP имплементация 
* CouchDB - популярна база данни 
* Riak - data store 

---
### Та какво е Elixir??

* Elixir наследява всички специфики и идеологии на Erlang. Все пак върви на BEAM.
* Elixir може да използва всичко писано на Erlang.
* Elixir идва с много добър инструментариум.
* Elixir има много добро и бързо-растящо общество.
* Elixir е модерен език, добър за уеб сървъри и IoT устройства.
* Споменахме ли, че е функционален език?

---
![Image-Absolute](assets/functional.jpeg)

---
### Началото

* Езикът се ползва някъде от 2013 (2011 първи копки) година, което го прави доста млад.
* Създателят на Elixir, Жозе Валим (José Valim), идва от ruby/rails света.
* Синтаксисът е инспириран от Ruby, метапрограмирането от Clojure, а всичко останало идва от Erlang.
* Бързо набира популярност сред рубистите и ерлангаджиите.

---
![Image-Absolute](assets/jose.jpg)

---
### Защо да учим Elixir?
* Защото можем да си напишем сървис, който ще поддържа хиляди потребителя online и ще живее в един OS процес.
* Защото имаме качествен инструментариум!

---
### Инструментариум

* Elixir идва с mix.
* Mix изпънява различни "задачи" - да речем прави нов Elixir проект.
* Много лесно е да си напишем и своя "задача".

---
### MIX
![Image-Absolute](assets/mix.jpg)

---
### Инструментариум

* Всъщност с mix можем да си направим собствена библиотека.
* И да я качим в hex, откъдето можем да сваляме библиотеки на други хора.
* Също така mix се справя страхотно с dependencies.
* Има вградена добра библиотека за тестване.
* Има лесен начин за генериране на HTML документация с връзки към кода.
* Идва с инструмент за автоматично форматиране на кода. (Използването му ще е задължително по време на курса)

---
### NOT MIX
![Image-Absolute](assets/npm.jpeg)

---
### Защо да учим Elixir?
* Защото можем да си напишем сървис, който ще поддържа хиляди потребителя online и ще живее в един OS процес.
* Защото имаме качествен инструментариум!
* Защото езикът е доста приятен и лесен за продуктивна работа!!

---
### Продуктивност

![Image-Absolute](assets/productivity.jpg)

---
### Езикът Elixir в няколко изречения:

* Модули, които са колекции от функции.
* Всичко е immutable.
* Кодът е изграден от композирани функции.
* Всичко върви в BEAM-процес.
* Кодът в тези BEAM-процеси е последователен, процесите вървят конкурентно един на друг.


---
#### Модули, колекции от функции:

```elixir
defmodule MyModule do
  import OtherModule

  def public_function(x) do
    x * private_function(x)
  end

  defp private_function(x) do
    x + other_module_public_function(x)
  end
end
```

---
#### Кодът е изграден от композирани функции:

```elixir
[1, 2, 3, 4, 5]
|> Enum.map(fn n -> n * n end)
|> Enum.filter(fn n -> n > 10 end)
|> Enum.reduce(1, &(&1 + &2))

# -> 42
```

---
#### Кодът е изграден от композирани функции:

```elixir
File.stream!("path/to/some/file")
|> Stream.flat_map(&String.split(&1, " "))
|> Enum.reduce(%{}, fn word, acc ->
  Map.update(acc, word, 1, & &1 + 1)
end)
|> Enum.to_list()
```

---
#### Pipes

![Image-Absolute](assets/pipes.jpg)

---
#### Функционален език:
```elixir
4 = 4                 # Интерпретира се без грешка
5 = 4                 # Грешка - MatchError
a = 4                 # Няма грешка, 'a' има стойност 4
4 = a                 # Също няма грешка
{d, e, 5} = {7, 6, 5} # d става 7, e става 6

f = fn (x) -> x * x end
f.(3)
# -> 9
```

---
#### Функционален език:
```elixir
f = fn
  (5) -> {:ok, 5}
  (x) -> {:error, x}
end
{:ok, x} = f.(5)     # Успех, x получава стойност 5
{:ok, x} = f.(6)     # Грешка, резултатът е {:error, 6}

Map.put(%{a: 3}, :b, 4)
# %{a: 3, b: 4} -> Нов map
```

---
#### Процеси:
Процесите в Elixir/Erlang се създават със `spawn`.

```elixir
# Тази функция ще се изпълни в нов процес:
pid = spawn fn -> 2 * 21 end

Process.alive?(pid)
# false, тъй като функцията се изпълнява бързо.

# Можем да ползваме pid-а на текущия процес с:
self()
Process.alive?(self()) # true
```

---
#### Процеси:

```elixir
pid = spawn(fn ->
  receive do
    {:howdy, message} -> IO.puts(message)
    {_, message} -> IO.puts("Няма значение")
  end
end)

send pid, {:howdy, "Как си?"}
```

---
Parallel map(collection):

```elixir
defmodule PEnum do
  def pmap(collection, mapper) do
    collection
    |> Enum.map(&(Task.async(fn -> mapper.(&1) end)))
    |> Enum.map(&Task.await/1)
  end
end
```

---
No shared state, threads and locks.

![Image-Absolute](assets/suffer.jpg)

---
### Защо Elixir?
* Защото можем да си напишем сървис, който ще поддържа хиляди потребителя online и ще живее в един OS процес.
* Защото имаме качествен инструментариум!
* Защото езикът е доста приятен и лесен за продуктивна работа!!
* Защото с Elixir сме МЕТА!

---
### Metaprogramming

![Image-Absolute](assets/metaprogramming.jpg)

---
### Metaprogramming

* Всъщност defmodule е макро.
* Както и def за функция.
* Както и почти всичко, което ще ползвате.

---
### Metaprogramming

##### Elixir е написан на Elixir

![Image-Absolute](assets/elixir_is_elixir.png)

---
### Metaprogramming

##### Позволява ни да правим такива неща
```elixir
from Post,
  where: [category: "fresh and new"],
  order_by: [desc: :published_at],
  select: [:id, :title, :body]
```

---
### Metaprogramming

##### Това пък е резултат от неуспешен тест

![Image-Absolute](assets/exunit.png)

---
### Защо Elixir?
* Защото можем да си напишем сървис, който ще поддържа хиляди потребителя online и ще живее в един OS процес.
* Защото имаме качествен инструментариум!
* Защото езикът е доста приятен и лесен за продуктивна работа!!
* Защото с Elixir сме МЕТА!
* Защото обществото около Elixir ще ви приветства!

---
#### Обществото
* Elixir обществото раздвижи Erlang обществото.
* Erlang се развива, Elixir програмисти правят PR-и, помагат.
* Имаме и ще имаме множество чудесни библиотеки.

---
### В Elixir/Erlang има бъдеще

![Image-Absolute](assets/ouroboros-by-zarathus.jpg)

---
### Защо да учим Elixir?
* Защото можем да си напишем сървис, който ще поддържа хиляди потребителя online и ще живее в един OS процес.
* Защото имаме качествен инструментариум!
* Защото езикът е доста приятен и лесен за продуктивна работа!!
* Защото с Elixir сме МЕТА!
* Защото обществото около Elixir ще ви приветства!
* И всички тези mixture-и!

---
#### Plug & Phoenix

![Image-Absolute](assets/phoenix_and_plug.jpg)

---
#### Ecto

![Image-Absolute](assets/ecto.png)

---
#### И още и още

![Image-Absolute](assets/explore.png)

---
#### Ще си говорим и за доста advanced неща!

![Image-Absolute](assets/distribution.jpg)

---
### Кой ползва Elixir?

* Adobe - За колаборативна работа над фотографски материали.
* Discord - За voice/text чат за геймъри.
* Pinterest - Социална мрежа, написана на Elixir. За споделяне и тагване на хоби идеи по снимки.

---
### Кой ползва Elixir?

* Pivotal - RabbitMQ CLI е написан на Elixir.
* Slack - Сървърите, поддържащи видео разговорите, са на Elixir.
* http://elixir-companies.com - Списък с компании, ползващи Elixir.

---
### Защо да научим Elixir?
* Защото е модерен, конкурентен език.
* Защото хората зад и около него са опитни.
* Защото основата му, Erlang, е стабилна и доказана.
* Защото е функционален език.
* Защото е подходящ за писане и поддръжка на много типове приложения.
* Защото ще разшири кръгозора ви.
* Защото е почти завършен.
* Защо не?

---
## Малко информация за курса
![Image-Absolute](assets/Craft-Beer.jpeg)

---
## Добре дошли!
* Ако сте записали курса за да вземете някоя изборна, ОТПИШЕТЕ ГО, няма да ви е лесно.
* Ако смятате, че Обектно-ориентираното програмиране е единственият начин, този курс не е за вас.
* Ако нямате достатъчно време, което да отделяте също ще ви е трудно.
* Ако очаквате монади, комонади, апликативи, мощтни типови системи - не ги очаквайте.

---
## Философия на курс

There will be no foolish wand waving or silly incantations in this class. As such, I don't expect many of you to enjoy the subtle science and exact art that is potion making. However, for those select few, who possess the predisposition, I can teach you how to bewitch the mind and ensnare the senses. I can tell you how to bottle fame, brew glory and even put a stopper in death.

---
## Какво ще трябва да научите в курса
* Elixir
* да мислите и моделирате чрез функции, а не обекти
* да съпоставяте образци
* да изпозвате git
* да пиете тестове

---
## Организация на курса
* Курсът ще се провежда всеки Вторник и Четвъртък от 19&#58;15 до 21&#58;00. 
* Ще се стараем за всяка тема да имаме подробна публикация в блога ни.
* Обикновено на лекция ще имаме презентация, но винаги сме готови да обсъдим нещо, което не е включено в нея.

---
* Лекциите ще бъдат разделени в 3 основни блока
  * Първият блок ще бъде информация за самия език и неговите идиоми
  * Във втория ще говорим за паралелизъм и кокурентност (основно неща свързани с BEAM)
  * В края на семестъра ще говорим за различни библиотеки и за неща които смятаме за интересни
  * Доста често ще говорим за Erlang

---
## Оценяване
* Оценката се формира на база събрани от вас точки:
  * 6 домашни за общо 60 точки
  * проект, който може да е в една от 5 категории в зависимост от сложността (за 40, 50, 60, 70 или 80 точки)
  * трябва да изкарате поне 20 точки от финалния проект за да вземете курса

---
## Ресурси
* Имаме сайт http://elixir-lang.bg
* Имаме Facebook група https://www.facebook.com/groups/636900123169076/
* Имаме mail [course@elixir-lang.bg](mailto:course@elixir-lang.bg)
* Github https://github.com/ElixirCourse
* Discord https://discord.gg/EZx7y67


---
## Край
![Image-Absolute](assets/gimpy.jpg)
