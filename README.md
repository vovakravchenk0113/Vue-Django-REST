# Django Vue Template ✌️ 🐍

![Vue Logo](/src/assets/logo-vue.png "Vue Logo")
![Django Logo](/src/assets/logo-django.png "Django Logo")

This template is a minimal example for an application using Vue and Django.

It's setup to have a clear separation: use Vue, Yarn, and Webpack to handle all frontend logic and assets bundling,
and use Django with Django REST framework to manage a Data Models, Web API, and serve static files.

While it's possible to add endpoints to serve django-rendered html responses, the intention is to use Django primarily for the backend, and have view rendering and routing and handled by Vue + Vue Router as a Single Page Application (SPA).

Out of the box, Django will serve the application entry point (`index.html` + bundled assets) at `/` ,
data at `/api/`, and static files at `/static/`. Django admin panel is also available at `/admin/` and can be extended as needed.

The application templates from Vue CLI `create` and Django `createproject` are kept as close as possible to their
original state, except where a different configuration is needed for better integration of the two frameworks.

#### Alternatives

If this setup is not what you are looking for, you might want look at other similar projects:

* [ariera/django-vue-template](https://github.com/ariera/django-vue-template)
* [vchaptsev/cookiecutter-django-vue](https://github.com/vchaptsev/cookiecutter-django-vue)

Prefer Flask? Checkout my [gtalarico/flask-vuejs-template](https://github.com/gtalarico/flask-vuejs-template)

### Demo

[Live Demo](https://django-vue-template-demo.herokuapp.com/)

### Includes

* Django
* Django REST framework
* Django Whitenoise, CDN Ready
* Vue CLI 3
* Vue Router
* Vuex
* Gunicorn
* Configuration for Heroku Deployment


### Template Structure
## Setup Template

```
$ git clone https://github.com/SmartDeveloper0124/Vue-with-Vuex-Django-RestFramework.git
$ cd django-vue-template
```

Setup
## Running Development Servers

```
$ python manage.py runserver
```

From another tab in the same directory:

```
$ yarn serve
```

The Vue application will be served from [`localhost:8080`](http://localhost:8080/) and the Django API
and static files will be served from [`localhost:8000`](http://localhost:8000/).

The dual dev server setup allows you to take advantage of
webpack's development server with hot module replacement.
Proxy config in [`vue.config.js`](/vue.config.js) is used to route the requests
back to django's API on port 8000.

If you would rather run a single dev server, you can run Django's
development server only on `:8000`, but you have to build build the Vue app first
and the page will not reload on changes.

```
$ yarn build
$ python manage.py runserver
```


## Deploy

* Set `ALLOWED_HOSTS` on [`backend.settings.prod`](/backend/settings/prod.py)
