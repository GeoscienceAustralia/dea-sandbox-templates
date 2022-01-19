# JupyterHub Templates

This repository contains templates used for JupyterHub.
* `templates` contains customized templates

Note: By default, JupyterHub already has these files in `/usr/local/share/jupyterhub/templates`

## Template Variables

`templatevars` can be set https://github.com/jupyterhub/zero-to-jupyterhub-k8s/blob/main/jupyterhub/values.yaml#L118

The templates extends from all templates in https://github.com/jupyterhub/jupyterhub/tree/main/share/jupyterhub/templates

Our templates supports the following template variables

**templatevars**|**type**
:-----|:-----
color_theme|string
html_title|string
announcement_pdf|http url to a file
feedback_endpoint|http url
login_error|error message
domain_name|full domain name without protocol like http:// or https:// for jupyterhub



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