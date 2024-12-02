# Ex.05 Design a Website for Server Side Processing
## Date:02/12/2024

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
math.html
<html>
<head>
<style>
.cube
{ display: block;
margin-top: 400px;
margin-bottom: auto;
margin-left: auto;
margin-right: auto;
border-style: dotted dashed solid double;
border-color: rebeccapurple;
background-color: powderblue;
padding-top: 60px;
padding-right: 60px;
padding-bottom: 60px;
padding-left: 70px;
width: 30%;
flex-direction: column;
}
body{
background-color: palevioletred;
}
div.formelt
{
font-size: 170%;
color: misty;
}
div.box
{
color: mediumvioletred;
text-align: center;
font-style: unset;
}
input
{
padding: 10px;
border: 1px solid;
border-radius: 3px;
width: 30%;
align-items: center;
}
</style>
</head>
<body>
<div class="cube">
<div class="box">
<h1>CALCULATING POWER OF LAMP</h1>
<form method="POST">
{% csrf_token %}
</div>
<h2>               <center>R.Lokeshwaran  (24011606)</center></h2>
<div class="formelt">
                   <br>
                   Intensity : <input type="text" name="Intensity" value=25
              
               "formelt">
                   <br>
                   Resistance : <input type="text" name="Resistance" value=7
              >
               
               <div  class="formelt">
                   <br>
                   <input type="submit" value="calculate"></input><br>
               </div>
               <div class="formelt">
                   <br>
               power : <input type="text" name="power" value="{{power}}"></
               </div>

           </form>
   </div>
</body>
</html>

views.py

from django.shortcuts import render 
def powerbulb(request): 
   context={} 
   context['power'] = "0" 
   context['I'] = "0" 
   context['R'] = "0" 
   if request.method == 'POST': 
       print("POST method is used")
       I = request.POST.get('Intensity','0')
       R = request.POST.get('Resistance','0')
       print('request=',request) 
       print('Intensity=',I) 
       print('Resistance=',R) 
       power = (int(I) * int(I))*int(R)
       context['power'] = power 
       context['I'] = I
       context['R'] = R
       print('power=',power) 
   return render(request,'mathapp/math.html',context)

   urls.py

from django.contrib import admin 
from django.urls import path 
from mathapp import views 
urlpatterns = [ 
path('admin/', admin.site.urls), 
path('powerofalamp/',views.powerbulb,name="powerofalamp"),
path('',views.powerbulb,name="powerofalamp")]

```




## SERVER SIDE PROCESSING:
![alt text](<Screenshot (60).png>)

![alt text](<Screenshot (61).png>)

![alt text](<Screenshot (62).png>)

![alt text](<Screenshot (63).png>)


## HOMEPAGE:
![alt text](<Screenshot (59).png>)

## RESULT:
The program for performing server side processing is completed successfully.
