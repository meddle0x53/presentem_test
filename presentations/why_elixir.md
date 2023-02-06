---
theme: uncover
style: |
  .small-text {
    font-size: 0.75rem;
  }
  li {
    font-size: 30px;
  }
paginate: true
footer: 'Курс по Elixir 2023, ФМИ'
backgroundImage: "linear-gradient(to bottom, #E0EAFC, #CFDEF3)"
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
