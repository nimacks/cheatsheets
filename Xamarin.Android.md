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

Building Blocks of Lists

ListView
Rows
Adapter

An adapter sits between the listView and the Collection of items to be displayed
We can't pass data directly to the ListView

ListView Uses an Adapter

Creating an adapter
ArrayAdapter - not used often

Implementing a Custom Adapter
Inherit from BaseAdapter<T>
Override the following methods
-GetItemId(int position)
-T this[int position]
- int Count
- View GetView(int position,View convertView, ViewGroup parent)

Row Resuse


Inflation is the process of generating objects based on xml 


Using In-built ListView
 public override View GetView(int position, View convertView, ViewGroup parent)
        {
            var item = items[position];

            if (convertView == null)
            {
                convertView = context.LayoutInflater.Inflate(Android.Resource.Layout.SimpleListItem1, null);
            }
            convertView.FindViewById<TextView>(Android.Resource.Id.Text1).Text = item.Name;
            return convertView;
        }


Android comes with a built in set of ListViews you can use
15 in built
For example:
SimpleListItem1
SimpleListItem2
TestListItem
ActivityListItem


Navigation patterns
Statck Navigation
Tab Navigation
Drawer

Intents
An intent is a discription of an action that needs to be described
Its the glue between activities
it allows you to start another activity
an intent can be seen as a messaging object
Some intents are explicit and others are implicit

Launching another activity
var intent = new Intent(This,typeof(HotDogDetailActivity));
startActivity(intent);

Every intent has a bundle which is comprised of Dictionary

passing data
var intent = new Intent(This,typeof(HotDogDetailActivity));
intent.PutExtra("selectedDogId",HotDogId);
startActivity(intent);

Tabs in Android
TabHost - Deprecated (don't use)
AppBar/ActionBar
ViewPager

Fragments
UiModule ~= usercontrol
promotes reusable
supports different resoulutions
have their own lifecyle

