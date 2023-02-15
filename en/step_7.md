## Add moving obstacles 

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Create a marble using a **UV sphere** object. Add a new material to the sphere.
</div>
<div>
![The output of step 7.](images/step7-output.PNG){:width="300px"}
</div>
</div>

--- task ---

**Right-click** in the 'Hierarchy' and choose **3D Object > Capsule**.

Set the **scale** of the 'Capsule' to X=`0.5`, Y=`0.5`, Z=`0.5`.

Set the **position** of the 'Capsule' to X=`1`, Y=`4.7`, Z=`-7`.

![A screenshot the Capsule transform component showing updated values.](images/capsule-transform.png)

--- /task ---

--- task ---

Click on the circle next to the Material property in the Capsule Controller component and select 'Bounce':

![A screenshot of the Capsule Controller component showing the Bounce physic material has been added.](images/capsule-bounce.png)

--- /task ---

--- task ---

**Choose:** a material to style your capsule. 

In the Project window, go to **Materials > ObstacleMaterials**. Drag a coloured material onto the capsule in Scene view.   

![The coloured capsule obstacle on the track.](images/capsule-track.png)

--- /task ---

--- task ---

**Test:** Press 'Play' and collide with the capsule to see the bounce material on both the ball and the obstacle combine to bounce the ball away from the obstacle. 

Press the 'Play' button again to stop running your project. 

--- /task ---

--- task ---

**Choose:** Add more coloured bouncy capsule obstacles to the top of your track. You can add as many as you like - but remember there has to be a way for your ball to get through.

![A series of coloured capsule obstacles at the top of the track.](images/multiple-capsules.png)

--- /task ---