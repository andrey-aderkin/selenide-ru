<ul class="main-menu-pages">
  <li><a href="{{ BASE_PATH }}/quick-start.html">С чего начать?</a></li>
  <li><a href="{{ BASE_PATH }}/documentation.html">Док</a></li>
  <li><a href="{{ BASE_PATH }}/faq.html">ЧАВО</a></li>
  <li><a href="{{ BASE_PATH }}/blog.html">Блог</a></li>
  <li><a href="{{ BASE_PATH }}/javadoc.html">Javadoc</a></li>
  <li><a href="{{ BASE_PATH }}/users.html">Пользователи</a></li>
  <li><a href="{{ BASE_PATH }}/quotes.html">Отзывы</a></li>
  <li style="display:none;"><a href="{{ BASE_PATH }}/thanks.html">Мы говорим спасибо</a></li>
</ul>

<div class="news">
  <div class="news-line"><a href="/2015/11/30/selenide-3.0/">Вышла Selenide 3.0!</a></div>
  <!--<div class="news-line"><a href="/2015/11/30/selenide-2.25/">Зарелизили Selenide 2.25!</a></div>-->
  <!--<div class="news-line"><a class="video" href="//www.youtube.com/watch?v=BjEW08vDUfI">Презентация Selenide на Devoxx 2015</a></div>-->
  <!--<div class="news-line"><a href="/2015/11/08/selenide-2.24/">Зарелизили Selenide 2.24</a></div>-->
  <!--<div class="news-line"><a href="/2015/09/23/selenide-on-seleniumconf/">Доклад о Selenide на SeleniumConf 2015</a></div>-->
  <!--<div class="news-line"><a href="https://t.co/Ih8FQ7VJMj">Презентация Selenide на SeleniumConf 2015 в Портленде!</a></div>-->
  <!--<div class="news-line"><a class="video" href="//vimeo.com/106867878">Как написать UI тест за 10 минут</a></div>-->
</div>

<h3 style="display:none">Блог</h3>
<div class="archive" style="display:none">
  {% assign posts_collate = site.posts %}
  {% include JB/posts_collate %}
  <a href="{{ BASE_PATH }}/archive.html" class="right small">Блог</a>
</div>
