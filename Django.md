 # Django
 
 - pip 업그레이드
 ```
 python -m pip install --upgrade pip
 ```

- Django 설치
 ```
 pip install Django
 ```
  
 - Django 업그레이드
 ```
 pip install Django --upgrade
 ```
 
 - Django 설치경로
 ```
 python -c "import django; print(django.__path__)"
 ```
  - Django 프로젝스 생성
 ```
 django-admin startproject tempPjt
 ```
 - Django App 등록
 ```
 //
 'students.apps.StudentsConfig',
 ```
 
 
 
 - migrate
 ```
 python manage.py migrate
 ```
 
- Django 관리자 계정생성
```
python manage.py createsuperuser
```

- Django 서버 구동
```
python manage.py runserver 0.0.0.0:8000
```

- 테이블 생성  
1.models.py 클래스 정의  
```
from django.db import models

class Student(models.Model):
	s_name = models.CharField(max_length=100)
	s_major = models.CharField(max_length=100)
	s_age = models.IntegerField(default=0)
	s_grade = models.IntegerField(default=0)
	s_gender = models.CharField(max_length=30)
	
	def __str__(self):
		return self.s_name
```
2.admin.py 에 등록 
```
from django.contrib import admin
from students.models import Student

admin.site.register(Student)
```
3.DB변경사항 반영
```
cmd>
python manage.py makemigrations

cmd>
python manage.py migrate
```





 
