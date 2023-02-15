## Add moving obstacles 

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Create a marble using a **UV sphere** object. Add a new material to the sphere.
</div>
<div>
![The output of step 2.](images/step2-output.PNG){:width="300px"}
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

**Test:** Press 'Play' and collide with the capsule to see the bounce material on both the ball and the obstacle combine to bounce the ball away from the obstacle. 

Press the 'Play' button again to stop running your project. 

--- /task ---