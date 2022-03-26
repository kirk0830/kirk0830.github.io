---
layout: default
---
<!-- post是一个保留文件名称。post用来管理_posts的默认使用模板 -->

<h1>{{ page.title }}</h1>
<!-- 访问当前页面的title并显示以1级标题 -->
<!-- 以p来引导正文内容 -->
<p>
  <!-- p标签是paragraph -->
  {{ page.date | date_to_string }}
  <!-- 显示page的时间到屏幕上，并且把date转换成为string，其中post每个文件的date实际上依赖于文件名 -->
  <!-- 即文件名具有固定格式 YYYY-MM-DD-Title.md ，之后日期会自动从文件名中抓取作为page.date -->
  {% assign cate = site.categories | where: 'short_name', page.category | first %}
  <!-- assign实际上是用来匹配： -->
  <!-- 取site.categories里所有的文件，按照其中short_name总结成句柄，之后只留下和当前页面 -->
  <!-- page.category数据成员相同的 -->
  {% if cate %}
    <!-- 如果确实还有东西留下，即使用assign确实给cate变量赋值到了东西 -->
    - <a href="{{ cate.url }}">{{ cate.name }}</a>
  {% endif %}
</p>

{{ content }}