# Map-in-python-with-Folium
A simple maps and tutorials to Folium library of python.

Step 0 — First things first

We will construct our web map using Python and Folium. You all are aware of Python so let me brief you about Folium. It is basically a Data Visualization library to visualize geospatial data or data that involves coordinates and locations. You will find more about folium on its official project page. Moreover, If you are completely new and don’t know how to install external libraries, I recommend you using ‘pip’, which is a package/library management system, used by most of us.

To install pip, run the following command in your terminal.

	#Python 3.x
	sudo apt install python3-pip
	#Python 2.x
	sudo apt install python-pip

Great! You just installed pip and now you are ready to install your first external library. To install folium library, executing following command in your terminal.

	pip install folium
Perfect. All the dependencies (fancy term for necessary tools required to run the program, duh) are installed and you are ready to roll.




Step 1 — Creating a Base Map

There is a proverb that says, “Don’t use a lot where a little will do,” while adding my philosophy to that, I came up with, “Start from the basics and don’t use a lot where a little will do.” It is of extreme importance that we start from the basics. Whether it be learning a programming language, or learning how to drive. Basics first. Then add little by little. Always.

Let’s create a base map. First, we import the library. Now, we create our map with folium.Map which takes the location at which you want your map to start with. You can add additional parameters such as pre-defined zoom and how the map will look like but more on that later. Now you have created your basic map. I believe this is the easiest way to create a map. Save the map, name it as you like and run the code and you will have your first map with folium.

Note — Once you execute the map.save() command, the map is saved in your current working directory. Hence, you have to hit up the file manager, go to the directory you are working in and run the “map1.html” file from there with help of a browser.




Step 2 — Add Marker

Marker, a point on the map, is the most important feature of entire map terminology. Let’s add a marker to our map with folium.Marker which also takes the location at which you want to point with some additional parameters such as what popup will display and how the icon will look. Easy stuff. Now the important thing, you see that .add_to(map)? We are adding the marker we created to the map we created earlier. Without this, the marker will be created but won’t be added to our map. Hence, you will see the same blank base map we created earlier.

‘tiles’ is a parameter to change the background of the map or to change what data is presented in the map, i.e. streets, mountains, blank map, etc. That’s it, your map is ready with a marker and minimal design. Because less is more.



Step 3 — Add Multiple Markers

Adding multiple markers is easy. All you have to do is run a for loop with all the coordinates you want to show. As discussed earlier, the basics, let’s just start with two.




Step 4 — Adding Markers from Data

First, we load data with help of Pandas, which is a commonly used data manipulation library. The data file includes columns such as the name of the volcano, where it is, elevation, latitude, and longitude. We need latitude and longitude to plot markers and to display a popup, we are going to need elevation. Therefore, we’ll extract it and store it into our variables. Run a for loop and there it is, all the markers with just 2 lines of code.





Step 5 — Colors (not by Jason Derulo)

You’ve added all the markers, but they all are in the same color which doesn’t tell much of a story. So, let’s group them by elevation <1000, between 1000 and 3000, and > 3000 and set color to green, orange and red, respectively.

You have to create a function using the simple if-else loops and call it in place of defining a color.




Step 6 — Change Icons

Let’s admit that the current icon might appear good but it’s not the best. It’s big and feels like we are creating the map in the ’90s. So let’s change them. I hope this is self-explanatory.

Now it looks good. I mean not great, but good. What do we do to make it great? Any ideas? I have got one. Presenting you, The Dark mode. To turn yours into all black, use tiles= “CartoDB dark_matter”




Step 7 — Cluster all Markers

It looks nice but what if you have 300 markers per state? Then it looks all messy. For that, we have to cluster all markers and as we zoom into the map, the cluster unfolds.

In order to do that, first, we have to create a cluster using MarkerCluster method which you will find under the library folium.plugins, and rather than adding all the markers to our map via .add_to(map), we will add them to our cluster via .add_to(name of the cluster), which in our case is .add_to(marker_cluster). Which will look something like shown below. As you zoom in and out of the map, all the clusters will unfold and fold automatically and it will look something like this.



