---
layout: post
title: "分页测试"
---

一个博客不可能只有几篇文章，如果所有文章全部放在一个页面中，在文章不多的情况下也许较为直观，一旦文章数量增加，不仅加大了用户需要加载的数据量，也为用户检索文章造成了障碍，所以基本上每个博客都会有文章的分页。一般的分页都是通过像JSP的模板引擎直接在从数据库中分页取出时生成动态生成页面，或者通过ajax从数据库分页取出传递到前端。但现在github+jekyll是静态的页面，没有数据库。好在jekyll支持分页功能

### 开启分页功能

首先我们需要在jekyll中开启分页功能，在jekyll的_config.yml中加入分页配置：

    paginate: 5
    paginate_path: "page:num"
        
第一行定义了每页的文章数量，而第二行则定义了在分页的结果，比如在/index.html中使用分页，定义为page:num，则第二页的路径将是/page2/index.html，第三页的路径将是/page3/index.html，以此类推

### 需要注意的几个点：
* 分页只在html文件中起作用
* paginate_path同时定义了需要被分页的文件，本人测试这个叫index.html，具体目录由paginate_path中的路径定义，如果定义的目录没有，则会向上寻找index.html，直到根目录的index.html，具体机制官网上没有详细说，所以还需要进一步实验

