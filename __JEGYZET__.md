# Django - foodOnline project

#### Python virtuális környezet létrehozása
```bash
python -m venv venv
```
#### Virtuális környezet aktiválása
```bash
source venv/Scripts/activate
```
#### Milyen modulokat tartalmaz a virtuális környezet?
```bash
pip freeze  # >>> nincsenek modulok telepítve...
```
#### Django telepítése a virtuális környezetbe
```bash
pip install django
```
#### Milyen modulok települtek fel?
```bash
pip freeze
asgiref==3.7.2
Django==4.2.3
sqlparse==0.4.4
typing_extensions==4.7.1
tzdata==2023.3
```
#### Hozzuk létre a projektet az aktuális könyvtárban...
```bash
# a . jelenti az aktuális könyvtárt
django-admin startproject foodOnline_main .
```
#### A projekt fejlesztéséhez indítsuk el a 'Visual Studio Code'-ot...
```bash
code .

# A VS Code elindul az aktuális konyvtár lesz a munkakönyvtára...
```
#### A 'Visual Studio Code'-ban állítsuk be a Git Bash terminált...
```bash
Terminal menü / New terminal...
Terminal ablak felső részén v legördítése / [Git Bash] kiválasztása
```
#### A külső Git Bash ablakban lépjünk ki a virt. környezetből...
```bash
deactivate  # majd zárjuk be az ablakot...
```
#### A VS Code termináljában aktiváljuk a virt. környezetet...
```bash
source venv/Scripts/activate
```
#### Indítsuk el a Django fejlesztői WEB-szerverét...
```bash
python manage.py runserver

# A web-szerver itt érhető el: http://127.0.0.1:8000/
```
#### Állítsuk át a kínált weboldal nyelvét magyarra...
Nyissuk meg szerkesztésre a projekt könyvtárban lévő **settings.py** fájlt, majd változtassuk meg a fájlban a következő két változó értékét. A módosítás mentése és az oldal frissítése után az oldal nyelve magyarra változik...
```bash
...
LANGUAGE_CODE = 'hu-hu'
TIME_ZONE = 'Europe/Budapest'
...
```
#### Saját nyitó oldal létrehozása...
Módosítsuk a projekt könyvtárban lévő **urls.py** tartalmát a következőre:
```python
from django.contrib import admin
from django.urls import path
from . import views                     # a views.py fájlt később hozzuk létre!!
                                        # a . az aktuális könyvtárat jelenti   
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.home, name='home'),  # a views.py fájl home() függvényére hivatkozunk,
]                                       # de ez a fájl még nem létezik...
```

Hozzuk létre a **views.py** fájlt  az urls.py fájl mellé a következő tartalommal:

```python
from django.shortcuts import render
from django.http import HttpResponse

def home(request):
    return HttpResponse('Helló World!')
```
A módosítások mentése és az oldal frissítése után a nyitó oldalon a 'Hello World!' látszik...

#### Github repo létrehozása a projekthez

Jelentkezzünk be a github-ra és készítsünk egy új repo-t **foodOnline** néven...

#### Készítsünk egy .gitignore fájlt a venv könyvtárral azonos szintre...
Látogassuk meg a https://gitignore.io helyet, írjuk be 'django' és generáljuk le a .gitignore javasolt tartalmát, majd ezt illesszük be a saját .gitignore fájlunkba...


#### A VS Code termináljában adjuk ki a következő parancsokat

```
git init

```

