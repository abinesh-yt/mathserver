# Ex.05 Design a Website for Server Side Processing
# Date: 30-09-2025
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
html
```
<html>
<body style="background: linear-gradient(to left , violet , indigo , blue, green , yellow , orange, red);"">
    <center>
   <h2>Incandescent Bulb Power Calculator</h2>
   <form method="post">
       {% csrf_token %}
       <label>Current (I):</label>
       <input type="text" name="current" required>
       <br><br>
       <label>Resistance (R):</label>
       <input type="text" name="resistance" required>
       <br><br>
       <button type="submit">Calculate Power</button>
   </form>
  
       <h3>Power of Lamp Filament = {{ power }} W</h3>
       </center>
   </body>
</html>

```

urls.py
```

from django.contrib import admin
from django.urls import path
from powerapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.calculate_power,name='abinesh'),
]

```
views.py
```
from django.shortcuts import render

def calculate_power(request):
    power = None
    if request.method == "POST":
        current = float(request.POST.get("current"))
        resistance = float(request.POST.get("resistance"))
        power = (current ** 2) * resistance
        # Print in console for debugging
        print(f"Current: {current} A, Resistance: {resistance} Ω, Power: {power:.2f} W")
    return render(request, 'power.html', {'power': power})

```



# HOMEPAGE:
<img width="1918" height="936" alt="image" src="https://github.com/user-attachments/assets/223ba4bb-032b-44f7-ae4c-5025220ab58b" />

# RESULT:
The program for performing server side processing is completed successfully.
