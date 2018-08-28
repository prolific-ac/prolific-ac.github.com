---
layout: page
title: The Prolific Academic Blog
---
<!-- <div class="container content">		 -->
<div class="row">    
    <!-- Left Sidebar -->
	<div class="col-md-8 col-md-offset-2">
    <div class="page-header">
        <h1 style="font-family: 'Century Gothic'">The Prolific Academic Blog</h1>
        <h2>Our blog has a new home: <a href="https://blog.prolific.ac">"https://blog.prolific.ac"</a> </h2>
    </div>
        <!--Blog Post-->    
        {% for post in site.posts %}
		  {% unless post.draft %}
		  <div class="blog margin-bottom-40">
		  <h2><a style="font-family: 'Century Gothic'" href="{{ post.url }}">{{ post.title }}</a></h2>
		  <h4>{{ post.date | date: "%B %e, %Y" }}</h4> 
		  <div class="blog-post-tags">
                <ul class="list-unstyled list-inline blog-info">
                    <li><i class="fa fa-calendar"></i> {{ post.date | date_to_long_string }}</li>
                    <li><i class="fa fa-pencil"></i> {{post.post_author}}</li>
                    <!-- <li><i class="fa fa-comments"></i> <a href="#disqus_thread"> Comments</a></li> -->
                </ul>
                <ul class="list-unstyled list-inline blog-tags">
                    <li>
                        <i class="fa fa-tags"></i> 
                        {% for tag in post.tags %} 
                        <!-- <a href="{{ BASE_PATH }}{{ site.JB.tags_path }}#{{ tag }}-ref">{{tag}}</a>  -->
                        <a href="#">{{tag}}</a>
                        {% endfor %}
                        
                    </li>
                </ul>                                                
            </div>
            <!-- <div class="blog-img">
                <img class="img-responsive" src="https://prolificacademic.co.uk/assets/img/posts/2.jpg" alt="">
            </div> -->
             {{ post.content  | strip_html| truncatewords:75 }}
            <p><a class="btn-u btn-u-small" href="{{ post.url }}"><i class="fa fa-plus-sign"></i>Read More</a></p>
			</div>				  
		  {% endunless %}
		{% endfor %}   
    </div>
</div>
<!-- </div> -->


    
    