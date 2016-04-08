#Xamarin.Android

###Fundamentals
Key Concepts

- Activities
- Views
- Fragments
- Intents
- Adapters



####Activities
Typical windows based applications have a single point of entry, 
usually defined by a main method.

```c#

    public static void main()
    {
        DoSomethingCool();
    }   

```

Android apps are built around activities. An activity is a single focused thing that a user can do. In android developement any
 activity can be set to start (or in windows terms be the main point of entry).
This can be done by setting an attribute property `MainLauncher = true` 

```c#
[Activity(Label = "App1", MainLauncher = true, Icon = "@drawable/icon")]
    public class MainActivity : Activity
    {

        protected override void OnCreate(Bundle bundle)
        {
           
        }
    }
```

- Each activity must inherit from the base class Activity
- `OnCreate(Bundle bundle)` is where you initialize your activity
- Each activity can set the view associated with it by using the method `SetContentView(Resource.Layout.Main);`

####Views

