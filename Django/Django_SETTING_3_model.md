# Django Project Setting (3) 

- Model 
- Migrations
- ๋ชจ๋ธ ์์ 



## ๐Model ์ด๋?

- ์น ์ดํ๋ฆฌ์ผ์ด์์ ๋ฐ์ดํฐ๋ฅผ ๊ตฌ์กฐํํ๊ณ  ์กฐ์ํ๊ธฐ ์ํ ๋๊ตฌ
- ๋จ์ผํ ๋ฐ์ดํฐ์ ๋ํ ์ ๋ณด
  - ์ฌ์ฉ์๊ฐ ์ ์ฅํ๋ ๋ฐ์ดํฐ๋ค์ ํ์์ ์ธ ํ๋์ ๋์ ํฌํจ
- ์ ์ฅ๋ DB์ ๊ตฌ์กฐ
- django๋ model์ ํตํด ๋ฐ์ดํฐ์ ์ ์ ๋ฐ ๊ด๋ฆฌ ๊ฐ๋ฅ
- ์ผ๋ฐ์ ์ผ๋ก ๊ฐ๊ฐ์ ๋ชจ๋ธ์ ํ๋์ DB table์ mapping



## ๐models.py

- DB ์ปฌ๋ผ๊ณผ ์ด๋ค ํ์์ผ๋ก ์ ์ํ  ๊ฒ์ธ์ง์ ๋ํด django.db ๋ชจ๋์ models ์์
  - ๊ฐ ๋ชจ๋ธ์ django.db.models.Model ํด๋์ค์ ์๋ธ ํด๋์ค๋ก ํํ

- ์ฌ์ฉํ๊ณ ์ ํ๋ ๋ชจ๋ธ์ Field ํ์ฉ์ <https://docs.djangoproject.com/en/3.2/ref/models/fields/> ์ฐธ์กฐ

- ๊ฐ ๋ณ์๋ ๋ชจ๋ธ์ ํ๋๋ฅผ ๋ํ๋



- `CharField(max_length=None, **options)`
  - ๊ธธ์ด์ ์ ํ์ด ์๋ ๋ฌธ์์ด ๋ฃ์ ๋ ์ฌ์ฉ
  - max_length๋ ํ์ ์ธ์
- `TextField(**options)`
  - ๊ธ์์ ์๊ฐ ๋ง์ ๋ ์ฌ์ฉ



#### articles/models.py

![image-20210902161618643](Django_SETTING_3_model.assets/image-20210902161618643.png)





## ๐Migrations

- django๊ฐ model์ ์๊ธด ๋ณํ๋ฅผ ๋ฐ์ํ๋ ๋ฐฉ๋ฒ

- `makemigrations`๋ฅผ ํ ์ดํ์ `migrate`์ ํด์ผ ํจ



### makemigrations

- model์ ๋ณ๊ฒฝํ ๊ฒ์ ๊ธฐ๋ฐํ ์๋ก์ด migration์ ๋ง๋ค ๋ ์ฌ์ฉ

```
$ python manage.py makemigrations
```

- `articles/migrations/`ํด๋์ `0001_initial.py`๊ฐ ์๊ธด ๊ฒ์ ํ์ธํ  ์ ์์

![image-20210902162255236](Django_SETTING_3_model.assets/image-20210902162255236.png)

![image-20210902162353137](Django_SETTING_3_model.assets/image-20210902162353137.png)



#### articles/migrations/0001_initial.py

- ์๋ ์ฌ์ง์์ ์ ์ ์๋ฏ์ด, `models.py`์์ ๋ง๋ค์ง ์์๋ `id`๋ถ๋ถ์ด ๊ฐ์ด ์์ฑ๋๊ณ  ์๋ ๋ชจ์ต์ ๋ณผ ์ ์์
  - `id`๋ ๊ฐ ํ์ ๊ณ ์ ๊ฐ์ธ `PK(primary key)`๋ฅผ ์ํ ๊ฐ

![image-20210902162517599](Django_SETTING_3_model.assets/image-20210902162517599.png)





### migrate

- migration์ DB์ ๋ฐ์ํ๊ธฐ ์ํด ์ฌ์ฉ

- ์ค๊ณ๋๋ฅผ ์ค์  DB์ ๋ฐ์ํ๋ ๊ณผ์ 

```
$ python manage.py migrate
```

์ปค๋งจ๋๋ฅผ ์คํํ๋ฉด ๋ค์๊ณผ ๊ฐ์ ๊ฒฐ๊ณผ๋ฅผ ๋ณผ ์ ์๋ค.

- `0001_initial.py` ์ค๊ณ๋๊ฐ ์ค์  DB์ ๋ฐ์๋๊ณ  ์์

![image-20210902162742300](Django_SETTING_3_model.assets/image-20210902162742300.png)





### sqlmigrate

- ํด๋น migrations ์ค๊ณ๋๊ฐ SQL ๋ฌธ์ผ๋ก ์ด๋ป๊ฒ ๋์ํ๋์ง ๋ฏธ๋ฆฌ ํ์ธ

```
$ python manage.py sqlmigrate articles 0001
```

![image-20210902163032517](Django_SETTING_3_model.assets/image-20210902163032517.png)





### showmigrations

- migrations ์ค๊ณ๋๋ค์ด migrate ๋๋์ง ์๋๋์ง ์ฌ๋ถ ํ์ธ

```
$ python manage.py showmigraitons
```

- `X` ํ์๋ migrate์ด ๋์์์ ๋งํจ

![image-20210902163711100](Django_SETTING_3_model.assets/image-20210902163711100.png)





## ๐Model ์์ 

- ๋ค์๊ณผ ๊ฐ์ด `models.py`์ ์ถ๊ฐ์ ์ธ ๋ด์ฉ ์์ฑ

![image-20210902164013307](Django_SETTING_3_model.assets/image-20210902164013307.png)

- `auto_now_add`๋ ์ต์ด ์์ฑ ์ผ์, `auto_now`๋ ์ต์ข ์์  ์ผ์
- model์ ๋ณ๊ฒฝ์ฌํญ์ด ๋ฐ์ํ ๊ฒฝ์ฐ, `makemigrations`์ `migrate`์ ๋ค์ ํด์ฃผ์ด์ผ ํ๋ค.



```
$ python manage.py makemigrations
```

- created_at ํ๋์ ๊ดํ ์ค์ ์ด ๋ฐ์ํ๋๋ฐ, default ๊ฐ ํ์ฉ์ ์ํด 1)์ ์ ์ฉ

![image-20210902164156509](Django_SETTING_3_model.assets/image-20210902164156509.png)

- timezone.now ์๋ ์ค์  ์ํด ๋น ์ํ์์`enter`

![image-20210902164316460](Django_SETTING_3_model.assets/image-20210902164316460.png)

- ๊ฒฐ๊ณผ

![image-20210902164421587](Django_SETTING_3_model.assets/image-20210902164421587.png)



#### articles/migrations/0002_auto_20210902_1643.py

- ์์ฑ์๊ฐ์ ๋ฐ๋ผ ํ์ผ ์ด๋ฆ์ ๋ค๋ฅด๊ฒ ์์ฑ๋จ

![image-20210902164554072](Django_SETTING_3_model.assets/image-20210902164554072.png)



- DB ๋ฐ์

```
$ python manage.py migrate
```

![image-20210902165602979](Django_SETTING_3_model.assets/image-20210902165602979.png)

