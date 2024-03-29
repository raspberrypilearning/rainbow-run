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
Marble run games have been around for centuries. The concept of guiding marbles through intricate tracks can be traced back to ancient civilisations, where children used materials like carved stone or wooden ramps to create their own marble runs. The great inventor and artist <span style="color: #0faeb0">**Leonardo da Vinci**</span> was known to experiment with various mechanical devices, including marble run-like contraptions. His fascination with engineering and motion can be seen in his drawings and designs.
</p>

### Create a project with the starter package

A Unity project needs graphics and sound 'Assets'.  

--- task ---

Download and unzip the [More Unity starter package](https://rpf.io/p/en/rainbow-run-go){:target="_blank"} to your computer. 

**Tip:** Choose a sensible location such as your Documents folder. 

--- /task ---

--- task ---

Launch the Unity Hub and click **Projects** then select **New project**:

![A screenshot of the black bar at the top of the Unity Hub with the 'New project' button highlighted in red.](images/new-project.png)

From the list choose **All templates** then select **3D Core**:

![A screenshot of the left pane in the Unity Hub. The 3D Core option is highlighted in red.](images/3D-core.png)

Edit the project settings to give your project a sensible name and save it to a sensible location. Then click **Create project**:

![A screenshot of the right pane in the Unity Hub. The filename and the 'Create project' sections are highlighted in red.](images/create-project.png)

Your new project will open in the Unity Editor. It may take some time to load.

--- /task ---

--- task ---

The More Unity starter package you downloaded contains a number of **Assets** for you to use in your project.

To import them into your new project, click on the **Assets menu** and select **Import package > Custom Package…** then navigate to the downloaded **More Unity starter package**.

[[[unity-importing-a-package]]]

--- /task ---

--- task ---

Right-click on **SampleScene** in the Hierarchy window and choose **Save Scene As**: 

![The SampleScene icon in the Hierarchy window with the right-click menu expanded.](images/right-click-scene.png)

In the pop-up window, name your Scene `Rainbow run`:

A new file will appear in the Assets folder in the Project window:

![Project window with Rainbow run scene in the Assets folder highlighted in red.](images/rainbow-run-scene.png)

Drag the new `Rainbow run` Scene into the 'Scenes' folder to organise your files.

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

In the Project window, click on **Materials**.

**Drag** the 'Concrete floor' material to the plane: 

Your scene should look like this:

![The Scene view with a rectangle plane covered in a grey textured material.](images/concrete-plane.png)

--- /task ---

### Create the track

--- task ---

Right-click on **Persp** in the Scene gizmo and choose 'Top' to switch to top-down view:

![The Persp menu is selected with the 'Top' option highlighted in red.](images/persp-top.png)

You should now see your project from the top view. 

![The Scene view with plane viewed from a top down angle.](images/plane-top.png)

--- /task ---

--- task ---

In the Project window, open the **Parts** folder and drag a 'Goal' into the Scene view. Position the goal near to the top right-hand side of the plane. 

**Tip:** You can either use the 'Move' tool to position the goal or enter the Transform position numbers X=`3`, Y=`0`, Z=`8`:

![The Transform position for the goal.](images/goal-transform.png)

Your goal should now look like this:

![The goal positioned in the top right-hand corner.](images/goal-position.png)

--- /task ---

--- task ---

From the **Parts** folder, drag a 'StraightDown' into the Scene view. Position the ramp in front of the goal. 

**Tip:** You can either use the 'Move' tool to position the ramp or enter the Transform position numbers X=`3`, Y=`1.5`, Z=`-3.3`.

--- /task ---

It is difficult to see the angle of the ramp from the top view.

--- task ---

Change the perspective to 'Right' using the Scene gizmo. 

You can move your view of the scene to see it from different angles. The best angle to view your track from is slightly higher than the pieces but angled down:

[[[unity-scene-navigation]]]

**Tip:** Remember, after navigating to the view you like best, your view won't look exactly the same as our examples.

![The plane and ramp viewed from the right side and above.](images/scene-above.png)

--- /task ---

--- task ---

From the **Parts** folder, drag a 'Spiral' into the Scene view. Position the spiral so it connects closely with the 'StraightDown' part. 

You can connect vertices (points) of two different objects in Unity by holding down the **V** key, hovering close to a vertex, and then dragging it towards the object you want to align with.

![An animated image shown the outside corner of the Spiral lower edge being selected and dragged to the top outside corner of the StraightDown upper edge.](images/vertex-snapping.gif)

[[[unity-vertex-snapping]]]

An alternative way to position these two pieces together is to set the Transform position of the Spiral to X=`3`, Y=`1.5`, Z=`-3.3`. 

--- collapse ---
---
title: Why are the coordinates for both objects the same?
---

Objects in Unity have a **Pivot point** used for the Transform position coordinates.

In this case the Pivot point for 'StraightDown' is at the top of the ramp and the Pivot point for 'Spiral' is at the bottom. This means the coordinates are the same for both pieces. 

![Two images side by side showing the joining area of both objects — the first with the Transform gizmo on the 'StraightDown', the second with the Transform gizmo of the 'Spiral'.](images/pivot-point.png)

--- /collapse ---

--- /task ---

--- task ---

From the **Parts** folder, drag a 'CurveDown' into the Scene view. Position the curved ramp so it connects closely with the 'Spiral' part. 

Use **Vertex snapping** to position your part.

Alternatively, you can use the coordinates X=`-2.37`, Y=`5.1`, Z=`-7.8`.

--- /task ---

--- task ---

Your course should look like the image below. This screenshot was taken from the **right** perspective.

![The completed course from the right perspective.](images/course-complete.png)

--- /task ---

### Colour the track

--- task ---

Choose a material for each piece in your track. 

In the Project window, go to **Materials**. Drag a coloured material onto each piece in the Scene view.   

We added rainbow colours. What will you choose? 

![The completed course from the right perspective with each piece representing a colour of the rainbow.](images/rainbow-track.png)

--- /task ---

**Tip:** Your scene will autosave. You can also use **File > Save** or <kbd>Ctrl+S</kbd> to save at any time. 

--- save ---
