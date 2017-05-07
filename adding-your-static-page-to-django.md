# Adding your static page to Django

After you have finished the Djangogirls tutorial you might want to add your static webpage into your Django project. Maybe it can be the about page of your blog. In this chapter we will explain how to do that.

## Putting the files into the django project structure

The first thing to do is moving your .html and .css files in the right place in your django project. The image below shows what your Django project structure looks like right now.

> Note: If you want to keep your static website available on the github.io url, you should keep the files in the original location as well, so in this case, you should copy them rather than move them.

You can add your .html files in the blog/templates/blog folder and the css-file in blog/static/css folder. So basically you add the .css file to the folder that already contains a .css file, and the .html file to the folder that already contains your django-html templates. During this process it is a good idea to rename the index.html file to some name  that is a bit more explanatory, such as about.html \(In the rest of this tutorial we will assume that you renamed your html file to about.html and that you want it to appear under the .../about url\)

## Adding a url and a simple view

Now lets make it possible to access this page through Django the same was we access the other pages, using urls.py and views.py

To do this we have to add the following to urls. py in the urlpatterns list:

blog/urls.py

```
urlpatterns = [
    ...
    url(r'^about/$', views.about_page, name='about_page'),
]
```

The View you have to at is also very simple. It lookl like this:

blog/views.py

```
def about_page(request):
    return render(request, 'blog/about.html', {})
```

This should make your static about page available on localhost:8000/about

## Integrating with the base.html template

So now you have made your static page available inside your Django project. But it still looks totally different than the pages of your blog, and it doesn't use the base.html template containing the navigation that we have used in our blog. So now it is time decide which parts of the layout of which project you want to keep. Here are some tips on how to unify your layout:

It is a good idea to keep using bootstrap as you did in your django blog project. Bootstrap can help you make a nice looking website quicker. If you want to know more about using bootstrap you can look in the official documentation on [http://getbootstrap.com](http://getbootstrap.com) \(the css and components parts are an interesting place to start\) or follow a bootstrap tutorial \(for example on codecademy:  [https://www.codecademy.com/courses/web-beginner-en-yjvdd/0/1\](https://www.codecademy.com/courses/web-beginner-en-yjvdd/0/1\)\)

Add the  \{% extends 'blog/base.html' %} \{% block content %} and \{%endblock content %} templatetags to your about.html page. The ...extends... tag should come at the very top and the block tags should surround your actual page content.

Remove the parts of the about page that are allready in the base.html such as the outer &lt;html&gt; tags, everything between the &lt;head&gt;...&lt;/head&gt; tags, as well as the &lt;body&gt; tags and any navigation if you have made some and don't want to use it anymore. If you want to keep using parts of your static css files you need to either add those parts to the blog.css file, or you need to copy the line where you link this css file from the about.html into the base.html head.

