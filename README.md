# JupyterHub Templates

This repository contains templates used for JupyterHub.
* `templates` contains customized templates

Note: By default, JupyterHub already has these files in `/usr/local/share/jupyterhub/templates`

# Customised Errors
The `custom/error.html` is extending https://github.com/jupyterhub/jupyterhub/blob/master/share/jupyterhub/templates/error.html

the Structure of the template is
```python
  {% block h1_error %}
  {% endblock h1_error %}

  {% block error_detail %}
  {% endblock error_detail %}
```
use `{{ super() }}` to inherit original message, or leave it out to completely override the `{% block %}`.

## 404
### template code snippet 

### Sandbox error html render
```html
<div class="error">
  <h1>
    404 : Not Found
  </h1>
<p>Jupyter has lots of moons, but this is not one...</p>
</div>
```

## 403

## 401
### template code snippet 
```python
{% elif status_code == 401 %}
<p>
    Session has expired: Please <a href="https://{{ domain_name }}/hub/logout">login</a> again.
</p>
```

### Sandbox error html render
```html
<div class="error">
  <h1>401 : Unauthorized</h1>
  <p>Session has expired: Please <a href="https://sandbox.dev.dea.ga.gov.au/hub/logout">login</a> again.</p>
</div>
```

## 400

## 500