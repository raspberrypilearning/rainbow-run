## Add moving obstacles 

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will create bouncy and spinning obstacles along your track.
</div>
<div>
![An animated image showing the spinning capsule rotating around the Y axis.](images/spinning-capsule.gif){:width="300px"}
</div>
</div>

### Bouncy capsules

--- task ---

**Right-click** in the 'Hierarchy' and choose **3D Object > Capsule**.

Set the **scale** of the 'Capsule' to X=`0.5`, Y=`0.5`, Z=`0.5`.

Set the **position** of the 'Capsule' to X=`1`, Y=`4.7`, Z=`-7`.

![A screenshot the Capsule transform component showing updated values.](images/capsule-transform.png)

--- /task ---

--- task ---

Click on the circle next to the Material property in the Capsule Collider component and select 'Bounce':

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

Right-click on the Capsule GameObject in the Hierarchy window and select 'Duplicate'.

Use the move tool to drag the new capsule to another position. 

![An animated image showing the duplication and moving of a second capsule obstacle.](images/multiple-capsules.gif)

**Choose:** Add more coloured bouncy capsule obstacles. You can add as many as you like - but remember there has to be a way for your ball to get through.

**Tip:** You can change the scale of each capsule to add variety to your track.

![A series of coloured capsule obstacles at the top of the track.](images/multiple-capsules.png)

--- /task ---

### An obstacle that spins

--- task ---

**Right-click** in the 'Hierarchy' and choose **3D Object > Capsule**.

Set the **position** of the 'Capsule' to X=`3`, Y=`0.8`, Z=`4.2`.

Set the **rotation** of the 'Capsule' to X=`10`, Y=`0`, Z=`0`.

Set the **scale** of the 'Capsule' to X=`1`, Y=`0.4`, Z=`0.2`.

![A screenshot the Capsule transform component showing updated values.](images/capsule-properties.png)

![A screenshot the Capsule at the bottom of the ramp.](images/spin-location.png)

--- /task ---

--- task ---

Rename the capsule object to 'SpinningCapsule'.

--- /task ---

--- task ---

**Choose:** a material to for your spinning capsule. 

--- /task ---


--- task ---

Go to the Inspector window for the 'SpinningCapsule' and click on the **Add Component** button. Type `Spin` and  press <kbd>Enter</kbd> **twice** to create a new `Spin` script.

--- /task ---

--- task ---

Go to the Project window. The new script will be saved in the Assets folder.

Drag the new script to the 'Scripts' folder to organise your files.

--- /task ---

--- task ---

Double click on the 'Spin' script. Copy or type this code to make the capsule spin when your game is in play:

--- code ---
---
language: cs
filename: Sin.cs
line_numbers: true
line_number_start: 1
line_highlights:
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Spin : MonoBehaviour
{
    public Vector3 rotation;

    // Start is called before the first frame update
    void Start()
    {
       
    }

    // Update is called once per frame
    void Update()
    {
        transform.Rotate(rotation * Time.deltaTime); 
    }
}

--- /code ---

--- /task ---

--- task ---

Save your script and switch back to the Unity Editor. Go to the Inspector for the SpinningCapsule. In the 'Spin' script component change the Rotation Y value to `50`: 

![A screenshot the Spin component showing the Rotation on Y with updated value.](images/y-rotation.png)

--- /task ---

--- task ---

**Test:** Press 'Play' and navigate to the end of your track. 

![An animated image showing the spinning capsule rotating around the Y axis.](images/spinning-capsule.gif)

Press the 'Play' button again to stop running your project. 

--- /task ---

--- task ---

**Choose:** You can use the Spin component to change the Rotation on X, Y or Z. Try spinning on a different axis or changing the value to increase or decrease the speed. 

--- /task ---

