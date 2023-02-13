## Build the track

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will build a track from parts and add colourful materials.
</div>
<div>
![A track made from colourful parts leading down to an end goal with three smaller tracks.](images/rainbow-track.png){:width="350px"}
</div>
</div>

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
Some popular <span style="color: #0faeb0">**rolling ball games**</span> made with Unity include <span style="color: #0faeb0">**Super Monkey Ball Banana Mania**</span>, <span style="color: #0faeb0">**Katamari Damacy REROLL**</span>, <span style="color: #0faeb0">**Hop**</span> and <span style="color: #0faeb0">**Rush**</span>. In some rolling ball games and apps you control the ball and in others you tilt the floor to move the ball. Have you played any games with a rolling ball or marble?
</p>

### Create a project with the starter package

A Unity project needs graphics and sound 'Assets'.  

--- task ---

Download and unzip the [More Unity starter package](https://rpf.io/p/en/rainbow-run-go){:target="_blank"} to your computer. 

**Tip:** Choose a sensible location such as your Documents folder. 

--- /task ---

--- task ---

Launch the Unity Hub and click **Projects** then select **New project**:

![A screenshot of the black bar at the top of the Unity Hub with the 'New Project' button highlighted in red.](images/new-project.png)

From the list choose **All templates** then select **3D Core**:

![A screenshot of the left pane in the Unity Hub. The 3D core option is highlighted in red.](images/3D-core.png)

Edit the project settings to give your project a sensible name and save it to a sensible location. Then click **Create project**:

![A screenshot of the right pane in the Unity Hub. The filename and the 'Create Project' sections are highlighted in red.](images/create-project.png)

Your new project will open in the Unity Editor. It may take some time to load.

--- /task ---

--- task ---

The Unity starter package you downloaded contains a number of **Assets** for you to use in your project.

To import them into your new project, click on the **Assets menu** and select **Import package > Custom Package…** then navigate to the downloaded Unity starter package.

[[[unity-importing-a-package]]]

--- /task ---

--- task ---

Right-click on **SampleScene** in the Hierarchy and choose **Save Scene As**: 

![The scene icon in the Hierarchy window with the right-click menu expanded.](images/right-click-scene.png)

In the pop-up window, name your Scene `Rainbow run`:

A new file will appear in the Assets folder in the Project window:

![Project window with Rainbow run scene in the Assets folder.](images/rainbow-run-scene.png)

--- /task ---

### Add a floor

--- task ---

Right-click on your scene (named Rainbow run) in the Hierarchy window and choose **GameObject > 3D Object > Plane**.

This will create a ground for your track to sit on.

--- /task ---

--- task ---

Resize the **Z Scale** of the plane in the Inspector window to `2`:

![The Transform pane in the Inspector window with Scale properties X=1, Y=1, and Z=2.](images/plane-transform.png)

--- /task ---

--- task ---

In the Project window, click on **Materials > Obstacle Materials**.

**Drag** the 'Concrete floor' material to the plane: 

Your scene should look like this:

![The Scene View with a rectangle plane covered in a grey textured material.](images/concrete-plane.png)

--- /task ---

### Create the track

--- task ---

Right-click on **Persp** in the Scene gizmo and choose 'Top' to switch to top-down view:

![Then Persp menu is selected with the 'Top' option highlighted.](images/persp-top.png)

You should now see your project from the top view. 

![The Scene view with plane viewed from a top down angle.](images/plane-top.png)

--- /task ---

--- task ---

In the Projects window, open the **Parts** folder and drag a 'Goal' into the Scene view. Position the goal near to the top-right of the plane. 

**Tip:** You can either use the 'Move' tool to position the goal or enter the transform position numbers X=`3`, Y=`0`, Z=`8`:

![The transform position for the goal.](images/goal-transform.png)

Your goal should now look like this:

![The goal positioned in the top right corner.](images/goal-position.png)

--- /task ---

--- task ---

From the **Parts** folder, drag a 'Ramp_StraightDown' into the Scene view. Position the ramp in front of the goal. 

**Tip:** You can either use the 'Move' tool to position the ramp or enter the transform position numbers X=`3`, Y=`1.5`, Z=`-3.3`:

--- /task ---

It is difficult to see the angle of the ramp from the top view.

--- task ---

Change the perspective to 'Right' using the Scene gizmo. 

You can move your view of the scene to see it from different angles. The best angle to view your track from is slightly higher than the pieces but angled down:

[[[unity-scene-navigation]]]

**Tip:** Remember, after navigating to the view you like best your view won't look exactly the same as our examples.

![The plane and ramp viewed from the right side and above.](images/scene-above.png)

--- /task ---

--- task ---

From the **Parts** folder, drag a 'Ramp_Spiral' into the Scene view. Position the spiral so it connects closely with the Ramp_StraightDown. 

You can connect vertices (points) of two different objects in Unity, by holding down the **V** key, hovering close to a vertex, and then dragging it towards the object you want to align with.

![An animated image shown the top corner of the Ramp_Spiral lower edge being selected and dragged to the top corner of the Ramp_StraightDown upper edge .](images/vertex-pieces.gif)

<mark>generic Vertex snapping ingredient</mark>


**Tip:** An alternative way to position these two pieces together is to set the transform position of the Ramp_Spiral to X=`3`, Y=`1.5`, Z=`-3.25`.
--- /task ---

--- task ---

--- /task ---

--- task ---

--- /task ---


**Tip:** Your scene will autosave. You can also use 'File->Save' or <kbd>Ctrl+S</kbd> to save at any time. 

--- save ---
