# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App.

### Step 4:
Create python programs for views and urls.

### Step 5:
Create a HTML file of forms.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```<!DOCTYPE html>
<html>
    <head>
        <title>
            www.volume.html
        </title>
    </head>
<style>
    *{
        box-sizing: border-box;
         }

    body{
    background-color;
    color: black;
    }

   .container{
    width: 1080px;
    height: 350px;
    margin-top: 100px;
    margin-left: auto;
    margin-right: auto;
    border-radius: 25px;
    border: 10px solid black;
    
    
    }
    h1{
        color: rgb(0, 0, 0);
        text-align: center;
    }
    .calculate{
        padding-top: 10px;
        padding-bottom: 10px;
        padding-left: 10px;
        padding-right:10px;
        text-align: center;
        font-size: 20px;
        padding-top: 7px;
        font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    }
</style>
    <body>
        <div class="container">
        <h1>TO CALCULATE VOLUME</h1>
        <form method="POST">
            {% csrf_token %}
            <div class="calculate"> 
                Height:<input type="text" name="height" value={{h}}></input><br/>
            </div>
            <div class="calculate">
                Length:<input type="text" name="length" value={{l}}></input><br/>
            </div>
            <div class="calculate">
                Width:<input type="text" name="width" value={{w}}></input><br/>
            </div>
            <div class="calculate">
                <input type="submit" value="Calculate Volume"></input><br/>
            </div>
            <div class="calculate">
                Volume:<input type="text" name="volume" value={{volume}}></input>
            </div>
        </form>
    </div>
    </body>
</html>

views.py
from django.shortcuts import render
def rectarea(request):
    context={}
    context['area'] = "0"
    context['l'] = "0"
    context['b'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        l = request.POST.get('length','0')
        b = request.POST.get('breadth','0')
        print('request=',request)
        print('Length=',l)
        print('Breadth=',b)
        area = int(l) * int(b)
        context['area'] = area
        context['l'] = l
        context['b'] = b
        print('Area=',area)
    return render(request,'myapp/math.html',context)


urls.py
from django.contrib import admin
from django.urls import path
from myapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaofrectangle/',views.rectarea,name="areaofrectangle"),
    path('',views.rectarea,name="areaofrectangleroot")
] 
```

## OUTPUT:
file:///home/sec/Pictures/Screenshots/homeoutput.png![image](https://user-images.githubusercontent.com/118343395/213204309-095c82ec-8bf8-4e6c-ad96-7879ed42dd4c.png)


### Home Page:
file:///home/sec/Pictures/Screenshots/home.png![image](https://user-images.githubusercontent.com/118343395/213204192-37b5b5f8-1f08-4717-b2ac-bed12bddc839.png)


## Result:
The program for implementing server side processing is completed successfully
