---
layout: page
title :
header : Документация
group: navigation
cssClass: docs
header-text: >
  <h4>Плохой софт <span class="bold">не имеет</span> документации.
  Отличный софт <span class="bold">не нуждается</span> в документации.</h4>

  Мы с гордостью заявляем, что Selenide настолько прост, что вам не нужно читать тонны документации, чтобы начать с ним работать.<br/>
  Вся работа с Selenide состоит всего из трёх простых вещей:
---
{% include JB/setup %}

## Три простые вещи:
<strong>1.</strong>  Открыть страницу   <br>
<strong>2.</strong>  $(элемент).совершитьДействие()<br>
<strong>3.</strong>  $(элемент).проверитьУсловие()<br>

```java
  open("/login");
  $("#submit").click();
  $(".message").shouldHave(text("Привет"));
```

## Используй мощь IDE!

Весь Selenide API состоит из небольшого числа классов. Мы предлагаем прекратить читать, открыть вашу любимую IDE и просто начать печатать.

Просто набери: `$(selector).` - и IDE предложит все возможные опции.

<img src="{{ BASE_PATH }}/images/ide-just-start-typing.png" alt="Selenide API: Просто начни писать"/>

Используй всю мощь современных средств разработки вместо того, чтобы забивать себе голову документацией!

<br/>

## Selenide API

Здесь можно найти <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}" target="_blank">Selenide javadoc</a>.

Для справки, ниже приведены некоторые классы Selenide, которые вам, возможно, придётся использовать:

<h3>com.codeborne.selenide.Selenide
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/Selenide.java">[src]</a>
  <a target="_blank" href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selenide.html">[javadoc]</a>
</h3>

Ядро библиотеки Selenide. Два основных метода - это `open` и `доллар`:
<ul>
  <li><a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selenide.html#open(java.lang.String)">open(URL)</a>, и</li>
  <li><a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selenide.html#$(java.lang.String)">$(String cssSelector)</a>   - возвращает первый SelenideElement</li>
  <li><a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selenide.html#$(org.openqa.selenium.By)">$(By)</a>   - возвращает первый SelenideElement</li>
  <li><a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selenide.html#$$(java.lang.String)">$$(String cssSelector)</a>   - возвращает список элементов</li>
  <li><a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selenide.html#$$(org.openqa.selenium.By)">$$(By)</a>   - возвращает список элементов</li>
</ul>

Обычно, когда вы получаете с помощью доллара объект SelenideElement, вы можете либо
совершить с ним какое-то действие (click, setValue), либо проверить какое-то условие: `shouldHave(text("abc"))`.

И есть ещё несколько методов, которые тоже иногда нужны:
<a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selenide.html#sleep(long)">sleep()</a>,
<a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selenide.html#refresh()">refresh()</a>,
<a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selenide.html#title()">title()</a>.

<h3>com.codeborne.selenide.SelenideElement
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/SelenideElement.java">[src]</a>
  <a target="_blank" href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/SelenideElement.html">[javadoc]</a>
</h3>

Класс SelenideElement - обёртка вокруг Selenium WebElement, добавляющая ему несколько весьма полезных методов:

*  should(Condition)
*  shouldBe(Condition)
*  shouldHave(Condition)
*  shouldNot(Condition)
*  shouldNotBe(Condition)
*  shouldNotHave(Condition)<br/>
*  waitUntil(Condition, milliseconds)
*  waitWhile(Condition, milliseconds)<br/>
*  find(String | By)
*  findAll(String | By)<br/>
*  setValue(String)
*  val(String)
*  append(String)
*  pressEnter(String)<br/>
*  val()
*  data()
*  text()
*  isDisplayed()
*  exists()<br/>
*  selectOption(String text)
*  selectOptionByValue(String value)
*  getSelectedOption()
*  getSelectedText()
*  getSelectedValue()<br/>
*  uploadFromClasspath(String fileName)
*  toWebElement()

<h3>com.codeborne.selenide.Condition
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/Condition.java">[src]</a>
  <a target="_blank" href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Condition.html">[javadoc]</a>
</h3>

*   visible | appear   // например, $("input").shouldBe(visible)
*   present | exist
*   hidden | disappear | not(visible)
*   readonly           // например, $("input").shouldBe(readonly)
*   attribute(String)
*   name               // например, $("input").shouldHave(name("fname"))
*   value              // например, $("input").shouldHave(value("John"))
*   type               // $("#input").shouldHave(type("checkbox"))
*   id                 // $("#input").shouldHave(id("myForm"))
*   empty              // $("h2").shouldBe(empty)
*   options
*   cssClass(String)
*   focused
*   enabled
*   disabled
*   selected
*   matchText(String regex)
*   text(String substring)
*   exactText(String wholeText)
*   textCaseSensitive(String substring)
*   exactTextCaseSensitive(String wholeText)

<br/>
Вы можете легко добавлять свои условие, реализовав подкласс `com.codeborne.selenide.Condition`.

Например:

```java
public static Condition css(final String propName, final String propValue) {
    @Override
    public boolean apply(WebElement element) {
      return propValue.equalsIgnoreCase(element.getCssValue(propName));
    }

    @Override
    public String actualValue(WebElement element) {
        return element.getCssValue(propName);
    }
};

// Example usage:
$("h1").shouldHave(css("font-size", "16px"));
```


<h3>com.codeborne.selenide.Selectors
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/Selectors.java">[src]</a>
  <a target="_blank" href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selectors.html">[javadoc]</a>
</h3>

Класс содержит некоторые `By` селекторы для поиска элементов по тексту или атрибуту (которых не хватает в стандартном Selenium WebDriver API):

*   <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selectors.html#byText(java.lang.String)">byText</a>     - поиск элемента по точному тексту
*   <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selectors.html#withText(java.lang.String)">withText</a>   - поиск элемента по тексту (подстроке)
*   <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selectors.html#by(java.lang.String, java.lang.String)">by</a>    - поиск элемента по атрибуту
*   <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selectors.html#byTitle(java.lang.String)">byTitle</a>   - поиск по атрибуту "title"
*   <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/Selectors.html#byValue(java.lang.String)">byValue</a>   - поиск по атрибуту "value"

<h3>com.codeborne.selenide.ElementsCollection
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/ElementsCollection.java">[src]</a>
  <a target="_blank" href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/ElementsCollection.html">[javadoc]</a>
</h3>

Этот класс, который возвращает метод `$$`. Содержит список веб-элементов и несколько полезных методов::

*   <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/ElementsCollection.html#shouldBe(com.codeborne.selenide.CollectionCondition)">shouldBe</a>     - e.g. `$$(".errors").shouldBe(empty)`
*   <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/ElementsCollection.html#shouldHave(com.codeborne.selenide.CollectionCondition)">shouldHave</a>     - e.g. `$$("#mytable tbody tr").shouldHave(size(2))`
*   <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/ElementsCollection.html#find(com.codeborne.selenide.Condition)">find</a>     - e.g. `$$("#multirowTable tr").findBy(text("Norris"))`
*   <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/ElementsCollection.html#filter(com.codeborne.selenide.Condition)">filter</a>     - e.g. `$$("#multirowTable tr").filterBy(text("Norris"))`
*   <a href="http://selenide.org/javadoc/{{site.SELENIDE_VERSION}}/com/codeborne/selenide/ElementsCollection.html#exclude(com.codeborne.selenide.Condition)">exclude</a>     - e.g. `$$("#multirowTable tr").excludeWith(text("Chack"))`


Более подробно эти и другие классы описаны в [javadoc]({{ BASE_PATH }}/javadoc.html)