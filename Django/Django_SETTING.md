# πDjango Project Setting(1)



## μ¬μ  μ€μ 



### .gitignore

- `.gitignore` (μ ν)

<https://www.toptal.com/developers/gitignore> μ μ ν νλ‘μ νΈμ λ§λ μ€μ  μ μ©

![image-20210902134435451](Django_SETTING.assets/image-20210902134435451.png)

κ°μνκ²½μ μν `venv`, μΈμ΄ νκ²½μ μν `Python`, `Django`, `VisualStudioCode`, `Windows` μΆκ°

μμ±λ κ²°κ³Όλ₯Ό `.gitignore`νμΌμ νλ‘μ νΈ ν΄λμ μμ± ν μμ±





### κ°μνκ²½ venv

- `venv`

bash μ°½μ venv μμ± μ»€λ§¨λ μμ±

cmd μ°½ νμλ₯Ό μν΄ `$` λ₯Ό ν΄λ¨μΌλ―λ‘, μ€μ λ‘ bashμ μμ±μ ν  λλ μ°μ§ λ§ κ²

```
$ python -m venv venv
```

κ°μ νκ²½ νμ±ν

```
$ source venv/Scripts/activate
```

![image-20210902135732018](Django_SETTING.assets/image-20210902135732018.png)

μλ¨μ `(venv)` νμλ₯Ό ν΅ν΄ κ°μνκ²½ νμ±ν μ¬λΆ νμΈ κ°λ₯



Django λͺ¨λ μ€μΉ ν `pip list`λ₯Ό ν΅ν΄ μ€μΉ μ¬λΆ νμΈ

```
$ pip install django
```

μ€μΉλ λͺ¨λ νμΈ λ°©λ²

```
$ pip list
```

![image-20210902140444507](Django_SETTING.assets/image-20210902140444507-16305590869091.png)



μ€μΉλ λͺ¨λ λ¦¬μ€νΈλ₯Ό μ μ₯νλ λ°©λ²(`requirements.txt` μ μ μ₯)

```
$ pip freeze > requirements.txt
```

μ£Όμ΄μ§ λͺ¨λ λ¦¬μ€νΈλ€μ ν΅ν΄ λͺ¨λμ μ€μΉνλ λ°©λ² (`requirements.txt`μ μ μ₯λμ΄μλ€λ κ°μ )

```
$ pip install -r requirements.txt
```





## πνλ‘μ νΈ μμνκΈ°

- Project
  - Applicationμ μ§ν©
  - μ¬λ¬ μ±μ΄ ν¬ν¨λ  μ μμ
  - μ±μ μ¬λ¬ νλ‘μ νΈμ μμ μ μμ



- νλ‘μ νΈ μ΄λ¦μ `crud` λ‘ λ§μ΄ μ€μ 

```
$ django-admin startproject crud .
```

νλ‘μ νΈκ° μμ±λλ©΄, λ€μκ³Ό κ°μ΄ `crud` ν΄λμ `manage.py` νμΌμ΄ μμ±λ κ²μ νμΈν  μ μλ€.

![image-20210902142721657](Django_SETTING.assets/image-20210902142721657.png)

- `__init__.py`

Pythonμκ² μ΄ λλ ν λ¦¬λ₯Ό νλμ Python ν¨ν€μ§λ‘ λ€λ£¨λλ‘ μ§μ

- `asgi.py`

Asynchronous Server Gateway Interface

django μ΄νλ¦¬μΌμ΄μμ΄ λΉλκΈ°μ μΉ μλ²μ μ°κ²° λ° μν΅νλ κ²μ λμμ€

- `settings.py`

μ΄νλ¦¬μΌμ΄μμ λͺ¨λ  μ€μ (μ€μβ)

- `urls.py`

μ¬μ΄νΈμ urlκ³Ό μ μ ν viewsμ μ°κ²°μ μ§μ 

- `wsgi.py`

Web Server Gateway Interface

django μ΄νλ¦¬μΌμ΄μμ΄ μΉμλ²μ μ°κ²° λ° μν΅νλ κ²μ λμμ€

- `manage.py`

Django νλ‘μ νΈμ λ€μν λ°©λ²μΌλ‘ μνΈμμ©νλ μ»€λ§¨λλΌμΈ μ νΈλ¦¬ν°



## πApplication μμ±

- Application
  - μ€μ  μμ²­μ μ²λ¦¬νκ³  νμ΄μ§λ₯Ό λ³΄μ¬μ£Όλ λ±μ μ­ν  λ΄λΉ
  - νλμ νλ‘μ νΈλ μ¬λ¬ μ±μ κ°μ§
  - μΌλ°μ μΌλ‘ μ±μ νλμ μ­ν  λ° κΈ°λ₯ λ¨μλ‘ μμ±



- Application μ΄λ¦μ λ³΅μν κΆμ₯

μμλ `articles`λ‘ κ΅¬ν

```
$ python manage.py startapp articles
```

Applicationμ΄ μμ±λλ©΄, μ± μ΄λ¦μΌλ‘ λ ν΄λκ° μμ±λ κ²μ νμΈν  μ μλ€.

![image-20210902144006084](Django_SETTING.assets/image-20210902144006084.png)

- `admin.py`

κ΄λ¦¬μμ© νμ΄μ§λ₯Ό μ€μ 

- `apps.py`

μ±μ μ λ³΄κ° μμ±λ κ³³

- `models.py`

μ±μμ νμ©νλ Modelμ μ μ

- `tests.py`

νλ‘μ νΈμ νμ€νΈ μ½λλ₯Ό μμ±

- `views.py`

view ν¨μλ€ μ μ



### Application λ±λ‘

- **λ°λμ μμ± ν λ±λ‘**
  - λ¨Όμ  μμ±νκ³  μμ±νλ €λ©΄ μ±μ΄ μμ±λμ§ μμ
- `settings.py`μ `INSTALLED_APPS`μ μΆκ°
  - Local apps, Third party apps, Django appsμ μμλ‘ λ±λ‘νλ κ²μ κΆμ₯

![image-20210902144734108](Django_SETTING.assets/image-20210902144734108.png)



### μ μμ μΈ μμ± μ¬λΆ νμΈ

- μλ²μ€ν

```
$ python manage.py runserver
```

- <http://127.0.0.1:8000/> λ₯Ό ν΅ν΄ μ μμ μΌλ‘ μμ±λμλμ§ νμΈ κ°λ₯

- μ€ν κ²°κ³Ό

![image-20210902153946255](Django_SETTING.assets/image-20210902153946255.png)





## πbase.html μμ±

- htmlνμΌλ€μμ κ³΅ν΅μ μΈ νμμ΄ λνλ¨
- λ°λ³΅μ μΌλ‘ μμ±νλ κ²μ μ€μ΄κ³ μ `base.html`μμ± 

- `templates` ν΄λλ₯Ό μμ± ν, `base.html` νμΌ μμ±

![image-20210902145753834](Django_SETTING.assets/image-20210902145753834.png)



#### base.html

- Bootstrapμ νμ©νκΈ° μν΄, css, js νμΌ μ μ©
- `body`μͺ½ ννΈμ, λ΄μ©μ λ£κ³ μ `block` μμ± 

```django
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
</head>
<body>
  <div class="container">
    {% block content %}
    {% endblock content %}
  </div>
  
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
</body>
</html>
```



####  λλ ν λ¦¬ μΆκ°

- `settings.py`μ `TEMPLATES`μ λλ ν λ¦¬ μΆκ°
- `DIRS`μ μΆκ°
- `BASE_DIR`μ κ°μ₯ μμͺ½ λλ ν λ¦¬λ₯Ό λ§ν¨
  - νμ¬ μμΉμ parent(crud)μ parent

![image-20210902151008786](Django_SETTING.assets/image-20210902151008786.png)

- μΆκ°ν κ²°κ³Ό

![image-20210902150812126](Django_SETTING.assets/image-20210902150812126.png)

