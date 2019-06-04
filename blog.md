---
title: Blog
layout: page
pageTitle: Blog
pageSubTitle: Latest news and updates from Andrew Pitter
homePageImage:
menu:
  header:
    weight: 3
    identifier: about

---

<section class="site-section">
  <div class="container">
    <div class="row">

    <!-- This loops through the paginated posts -->
    {% for post in paginator.posts %}
      <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
      <p class="author">
        <span class="date">{{ post.date }}</span>
      </p>
      <div class="content">
        {{ post.content }}
      </div>
    {% endfor %}

    <!-- Pagination links -->
    <div class="pagination">
      {% if paginator.previous_page %}
        <a href="{{ paginator.previous_page_path }}" class="previous">
          Previous
        </a>
      {% else %}
        <span class="previous">Previous</span>
      {% endif %}
      <span class="page_number ">
        Page: {{ paginator.page }} of {{ paginator.total_pages }}
      </span>
      {% if paginator.next_page %}
        <a href="{{ paginator.next_page_path }}" class="next">Next</a>
      {% else %}
        <span class="next ">Next</span>
      {% endif %}
    </div>
      <div class="col-md-8">
        <div class="row mb-5">
          <div class="col-md-6 col-lg-6 mb-4 mb-lg-4">
            <div class="h-entry">
              <img src="images/img_6.jpg" alt="Image" class="img-fluid">
              <h2 class="font-size-regular"><a href="#">Warehousing Your Packages</a></h2>
              <div class="meta mb-4">Theresa Winston <span class="mx-2">&bullet;</span> Jan 18, 2019<span class="mx-2">&bullet;</span> <a href="#">News</a></div>
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Natus eligendi nobis ea maiores sapiente veritatis reprehenderit suscipit quaerat rerum voluptatibus a eius.</p>
            </div>
          </div>

        </div>
        <div class="row">
          <div class="col-12">
            <div class="custom-pagination text-center">
              <span>1</span>
              <a href="#">2</a>
              <a href="#">3</a>
              <span class="more-page">...</span>
              <a href="#">10</a>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-3 ml-auto">
        <div class="mb-5">
          <h3 class="h5 text-black mb-3">Categories</h3>
          <ul class="list-unstyled">
            <li class="mb-2"><a href="#">Lorem ipsum dolor sit amet</a></li>
          </ul>
        </div>
      </div>

    </div>
  </div>
</section>
<script>
var posts = [
  {% for post in site.posts %}
    {
      "title": "{{ post.title }}",
      "category": "{{ post.category }}",
      "url": "{{ post.url }}",
      "image": "{{post.post_image}}",
      "author": "{{post.author}}",
      "date": "{{post.date}}"
    }
    {% unless forloop.last %},{% endunless %}
  {% endfor %}
];
</script>
