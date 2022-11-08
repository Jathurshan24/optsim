# Opt-Sim
<h4>  Scope and Purpose of the project </h4>

We are developing a project for optical lenses experiment simulation.
It will be like getting image and ray diagram for object's position from lenses like biconvex, biconcave, 
Plano-Convex, Convex-Concave, Meniscus, Plano-Concave.
We made that dynamic like we can drag the object towards or backward from lenses.
We used Html5, kineticjs (JavaScript library) and CSS3 to develop this.
We are contributing this project for Mozilla Science Lab.<br/>
Click below to check our project site and demo<br/>
<a class="btn btn-primary btn-lg" href="http://uojopendesk.com/opt-sim/" role="button">See Demo</a></p>

<h4>	Process Overview project </h4>
  
It works in two main categories. Fist one is one lens experiment. Other one is two lenses experiment.
In one lens experiment, there are six categories with biconvex, biconcave, Plano-Convex, Convex-Concave,
Meniscus, Plano-Concave lenses. In two lenses experiment, there are numerous categories with the pairs like
(biconvex, biconvex), (biconcave, biconcave), (biconvex, biconcave), (biconcave, biconvex) and etc. 
Each categories works five different cases such as object beyond 2F, object between F and 2F, object at 2F, 
object at F, object within F.

<h4>	Introduction the Structure of Interface </h4>
This application consist Experimental area, Lenses Toolbar, Objects Toolbar and Help button.
We can perform simulation in this Experimental Area.
In the lenses toolbar types of lenses are shown such as biconvex, biconcave, Plano-Convex, Convex-Concave,
Meniscus, Plano-Concave. 
In the object toolbar there are three objects, they are Arrow, Triangle and Polygon.
To get Help, there is an icon with question mark. 

<h4>How to insert Lens and Object to the experimental	area </h4>

There is horizontal line placed in the experimental area and that is center axis of lens. 
We can drag and drop lens from lens toolbar. We can have maximum of two lenses in experimental area.
You can add them by drag and drop wherever you want and which order you want. You can replace these lenses
by drag and drop the wanted lens over or near to the existing lens. After you added lens the ‘F’ and ‘2F’ will 
be added in both side of the lens. If you add second lens, F and 2F of each lens’s color will be different.
So, you can easily identify F, 2F for corresponding lens. 
In objects tool bar three objects are placed. You can select one of these objects by clicking the 
corresponding icon to get the object in experimental area. You can add only one object at a time. 
if you click on the other object, the existing object will be replaced by new object


<h4>	How to adjust Lens and Object </h4>
Lenses will be placed in center of the experimental area and they can drag only in horizontal axis. You can drag the lens within the range of between object and end of the experimental area. If there are two lenses, first lens can move between object and second lens’s position. Second lens can move between first lens’s position and end of the experimental area. So we can change the distance between the lenses. 
Object can be move between starting of the experimental area and lens’s position. So, we can change the distance from the lens. And you can identify the object’s position such as beyond 2F, between 2F and F, within F by looking at theF,2F marks. 
While you drag lens or object you can see the ray diagram and the image generated by lens for corresponding object will appear dynamically

<h4>	How to remove Lens  </h4>
To remove a lens from the experimental area just double click on the lens. 

<h3> Developer's Guide </h3>

<h4> Project Directory Structure </h4>

This project contains files and folders. The structure of the contents of this folder is outlined below:<br/>

Images used by the lens_experiment.html file.<br/>
•	js/<br/>
This contains the JavaScript files used.<br/>
lens.js - This contains all JavaScript code used by the project.<br/>

•	lens_experiment.html<br/>
•	style.css – Style Sheet for this project<br/>
This contains all HTML code used by the project.<br/>

<h4> The lens.js File </h4>

The lens.js file contains all main functionality functions used by this project .These are defined with several method and variables, explained below.
Methods<br/>
Intersect() – Find the intersection point of two rays.<br/>
Deleteray(), deleteray2() – To remove previously drawn ray lines when dragging the lens or object.<br/>
dragDrop() – This function works after the lens drag from toolbar & drop into the container.<br/>
drawImage() – When dragging object or lens, It is used to draw all set of ray lines and image of object for one lens, two lens experiment. This two categories works five different cases such as object beyond 2F , object between F and 2F , object at 2F , object at F , object within F.<br/>
document.getElementById('object_arrow').addEventListener('click', function() {}) – When click the object in the toolbar, the object will be created into the container.<br/>
arrow_object.on("dragmove", function() {}) –When drag the arrow object, this function will work. It limits the dragging area of object up to first lens.<br/>
triangle_object.on("dragmove", function() {}) –When drag the triangle object, this function will work. It limits the dragging area of object up to first lens.<br/>
square_object.on("dragmove", function() {}) –When drag the square object, this function will work. It limits the dragging area of object up to first lens.<br/>
image.on("dragmove", function(evt) {}) –When drag the lens, this function will work. If we drag the first lens, it limits the dragging area between object and second lens. If we drag the second lens, it limits the dragging area of object up to first lens.<br/>
image.on('dblclick', function(evt){}) – When double click the lens, clicked lens, related ray lines, related f,2f  will be deleted.<br/>

<h4> Variables </h4>

object_name – Find the name of object in the container (Arrow, Triangle, Square).<br/>
principal_axis –Create principal axis line for the experiment.<br/>
arrow_object – Create Arrow object.<br/>
triangle_object – Create Triangle object.<br/>
square_object – Create Square object.<br/>
lense_id – After the dropping the lens into the container, find id of the dropped lens.<br/>
lense_1_name – Find the name of the fist lens in the container.<br/>
lense_2_name – Find the name of the second lens in the container.<br/>
twof_1 - Create left 2f of the first lens.<br/>
twof_2 - Create right 2f of the first lens.<br/>
focal_1 - Create left f of the first lens.<br/>
focal_2 - Create right f of the first lens.<br/>
twof_3 - Create left 2f of the second lens.<br/>
twof_4 - Create right 2f of the second lens.<br/>
focal_3 - Create left f of the second lens.<br/>
focal_4 - Create right f of the second lens.<br/>
object_position_x – Find the position of the object (Arrow, Triangle, Square).<br/>
lense_1_position – Find the position of the first lens.<br/>
lense_2_ position – Find the position of the second lens.<br/>
slope_1 - Find slope between principal axis and the central ray for first lens.<br/>
slope_2 - Find slope between principal axis and the refracted ray for first lens, if it is convex lens.<br/>
lense1_ray1_end_point_x – Find the end point x coordinate of central ray for first lens.<br/>
lense1_ray1_end_point_y – Find the end point y coordinate of central ray for first lens.<br/>
lense1_ray2_end_point_x – Find the end point x coordinate of refracted ray for first lens.<br/>
lense1_ray2_end_point_y – Find the end point y coordinate of refracted ray for first lens.<br/>
central_ray – Create the central ray.<br/>
incident_ray – Create the incident ray.<br/>
focal_point_lense_1 – Find the focal point of the first lens .According to the lens type. If convex lens = f, if concave lens = -f.<br/>
focal_point_lense_2 – Find the focal point of the second lens .According to the lens type. If convex lens = f, if concave lens = -f.<br/>
intersect_point_1 - Find intersected point of refracted ray and central ray of first lens for all three objects.<br/>
intersect_point_1_tri_squ - Find intersected point of refracted ray and central ray of first lens for triangle, square object’s left upper corner point.<br/>
image_1 – Create the image of the object for both lens, if it is one lens Experiment.<br/>
refracted_ray_convex – Create refracted ray, if the first lens is convex lens.<br/>
intersect_point_2 - Find intersected point of refracted ray and central ray of second lens if the first lens is Convex for all three objects.<br/>
intersect_point_2_tri_squ - Find intersected point of refracted ray and central ray of second lens if the first lens is Convex for triangle, square object’s left upper corner point.<br/>
image_2 – Create the image of the object, if the first lens is convex for two lens Experiment.<br/>
reflected_ray – Create reflected ray for the first lens, if it is convex.<br/>
slope_3 - Find slope between principal axis and the refracted ray for first lens, if it is concave lens.<br/>
refracted_ray_concave  – Create the refracted ray, if the first lens is concave lens.<br/>
reflected_ray_concave - Create reflected ray for the first lens, if it is concave.<br/>
intersect_point_3 - Find intersected point of refracted ray and central ray of second lens if the first lens is Concave for all three objects.<br/>
intersect_point_3_tri_squ - Find intersected point of refracted ray and central ray of second lens if the first lens is Concave for triangle, square object’s left upper corner point.<br/>
image_3 – Create the image of the object, if the first lens is concave for two lens Experiment.<br/>
reflected_ray_lense2_1, reflected_ray_lense2_2, reflected_ray_lense2_3, reflected_ray_lense2_4 – Create the reflected ray for the second lens.<br/>
lense2_ray1_end_point_y - Find the end point x coordinate of refracted ray for second lens.<br/>
lense_instance – Find the lens, When double click the object to remove.<br/>
lense_instance_id - Find id of the lens, when double click the object to remove.<br/>



