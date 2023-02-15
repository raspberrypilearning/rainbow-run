## Create a ball 

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Create a ball using a **UV sphere** object. Style the ball and make it bounce.
</div>
<div>
![The ball game object is shown in the centre of the Scene view. The view is close up.](images/bouncyball-zoom.png){:width="300px"}
</div>
</div>

--- task ---

**Right-click** in the 'Hierarchy' and choose 'Create->GameObject->Sphere'.

**Name** the new Sphere object 'Ball'.

![A screenshot of the menu in the hierarchy window. Create GameObject and Sphere are highlighted.](images/new-sphere.png)

--- /task ---

--- task ---

Set the scale of the 'Ball' to X=`0.25`, Y=`0.25`, Z=`0.25`.

![A screenshot highlighting the stated scale values for the 'Ball' GameObject.](images/ball-scale.png)

--- /task ---

### Use gravity

--- task ---

Position the ball using the **transform gizmo** so that it is slightly above the top of the ramp. 

Alternatively, you can use the transform positions X=`-1`, Y=`6`, Z=`-7.7`.

![A screenshot highlighting the ball positioned at the top of the ramp.](images/ball-position.png)

--- /task ---

--- task ---

With the 'Ball' GameObject selected, choose 'Add Component' in the inspector window and enter the text 'RigidBody'. Select the 'RigidBody' component. This adds a gravity effect to your ball. 

![A screenshot showing the RigidBody component selected in the inspector window.](images/rigid-body.png)

--- /task ---

--- task ---

Right-click on the 'MainCamera' object in the 'Hierarchy'.

Choose 'Align with view'. This will match your Scene view and your Main Camera view. 

![A screenshot showing the 'Align with view' option highlighted in the GameObject menu.](images/align-with-view.png)

--- /task ---

--- task ---

Click **Play** and watch your ball roll slowly down the ramp. 

--- /task ---

### Make the ball bounce

--- task ---

In the Project window select 'Materials' and then 'PhysicsMaterials'. Right-click in the window, click 'Create' and select **Physic Material**. 

![A screenshot showing menu with 'Create' and 'Physic Material' highlighted.](images/create-physic-material.png)

--- /task ---

--- task ---

Name the material 'Bounce'.

![A screenshot showing the newly created 'Bounce' physics material.](images/bounce-material.png)

--- /task ---

--- task ---

Change Bounciness to `1`.

![A screenshot showing the 'Bounciness' property set to '1'.](images/bounciness-one.png)

--- /task ---

--- task ---

Select the 'Ball' GameObject and go to the Inspector window.

Find the 'Sphere Collider' properties and click on the small circle in the 'Material' section. 

![A screenshot showing the small circle to the right of 'Material'.](images/add-physics-material.png)

Double-click on your new 'Bounce' physics material.

![A screenshot showing the the 'Bounce' physics material highlighted.](images/bounce.png)

--- /task ---

--- task ---

Click **Play** and watch your ball bounce as it lands on the ramp.

![Animation showing ball dropping and bouncing on the ramp before rolling downwards.](images/ball-bounce.gif)

--- /task ---

### Style your ball

--- task ---

In the Project window go to **Materials > BallMaterials**. 

Right-click in the folder and select **Create > Material**.

Name your new material **BouncyBall**:

![The BallMaterials folder with new 'BouncyBall' material.](images/bouncyball-material.png)

--- /task ---

--- task ---

Go to the Inspector window and select the small circle next to **Albedo**. Type `BouncyBall` to find the texture that has been included in your asset package. 

Click on the texture to add it to your new material.

![The Inspector showing the 'Albedo' property and beneath it a popup window with the words 'BouncyBall' typed into the search. The BouncyBall texture has appeared in the search results.](images/bouncyball-material.png)

--- /task ---

--- task ---

Drag your new 'BouncyBall' material to the ball in the Scene view. 

**Tip:** Use <kbd>shift</kbd> and <kbd>f</kbd> on your keyboard to zoom in to the ball object so you can see the material clearly. 

![The ball game object is shown in the centre of the Scene view. The view is close up.](images/bouncyball-zoom.png)

--- /task ---