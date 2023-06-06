## Control the camera

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will create a script to control the camera and follow the ball down the track.
</div>
<div>
![An animated image of the Game view with the camera following the ball down the track. The camera is rotating to the left and right.](images/camera-control.gif){:width="300px"}
</div>
</div>

### Position your camera

--- task ---

Go to the Hierarchy window. Click on the 'Main Camera'. A small Main Camera view window will appear showing the view the camera sees:

![The Scene view with the main camera view window in the bottom right corner.](images/camera-window.png)

Change the transform position and rotation of the Main Camera to:

Position: X=`-2.5` , Y=`7`, Z=`-7.9`
Rotation: X=`24` , Y=`90`, Z=`0`

The camera should be behind the ball and facing slightly down the ramp. 

![The Main Camera view window showing that the camera view is behind the ball and above the ramp.](images/camera-positioned.png)

--- /task ---

--- task ---

Go to the Hierarchy window. Right-click on the 'Main Camera' and select **Align View to Selected**. 

--- /task ---

### Follow the ball 

--- task ---

Go to the Inspector window for the 'Main Camera' and click on the **Add Component** button. Type `CameraFollow` and press <kbd>Enter</kbd> **twice** to create a new script called `CameraFollow`.

![The new CameraController script component on the Main Camera.](images/camera-component.png)

--- /task ---

--- task ---

Go to the Project window. The new script will be saved in the Assets folder:

![The new CameraController script in the Assets folder.](images/camera-assets.png)

Drag the new script to the 'Scripts' folder to organise your files:

![The new CameraController script now in the Scripts folder.](images/camera-script.png)

--- /task ---

--- task ---

Double click on 'CameraFollow' script. The script will open in a separate code editor. 

Copy or type this code to make the Main Camera look at the ball and move with the ball as the ball rolls down the track:

--- code ---
---
language: cs
filename: CameraFollow.cs
line_numbers: true
line_number_start: 1
line_highlights: 
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CameraFollow : MonoBehaviour
{
  public GameObject ball;
  private Vector3 prevBallPos;

  void Start()
  {
      // Calculate where the camera is in relation to the player (ball)
      transform.LookAt(ball.transform);
      prevBallPos = ball.transform.position;
  }

  void Update()
  {
       // Moves the camera by the same amount the ball has moved
       transform.Translate(ball.transform.position - prevBallPos, Space.World);
       prevBallPos = ball.transform.position;
  }
}

--- /code ---

--- /task ---

--- task ---

Save your script and switch back to the Unity Editor and click on the 'Main Camera' GameObject in the Hierarchy window.

Find the 'Ball' property of the Main Camera's CameraFollow script in the Inspector window.

Click on the circle to the right of the Ball property and choose the 'Ball' GameObject:

![The CameraController script component on the Main Camera with Ball property dropdown menu and 'Ball' selected.](images/ball-script.png)

--- /task ---

--- task ---

**Test:** Select the Game view tab and click on the 'Play' button to run your project.  

The ball will roll down the track and the camera will follow it. 

![An animated video of the Game view with the camera following the ball down the track.](images/camera-follow.gif)

--- /task ---

### Control the view

--- task ---

Press the 'Play' button again to stop running your project.

Select the 'MainCamera' object in the Hierarchy window again. 

In the 'Inspector' click on the **Add Component** button, Type `CameraRotate` and press <kbd>Enter</kbd> **twice** to create a new script called `CameraRotate`.

Move the new script from the 'Assets' folder to the 'Scripts' folder to organise your files.

Double click on `CameraRotate` script and add code to use the mouse position to control the camera rotation angle:

--- code ---
---
language: cs
filename: CameraRotate.cs
line_numbers: true
line_number_start: 1
line_highlights:
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CameraRotate : MonoBehaviour
{
  public GameObject ball;
  public float sensitivity = 5f;

  void Start()
  {
      // Focus the camera on the Ball
      transform.LookAt(ball.transform);
  }

  void Update()
  {
      //If the left mouse button held down, rotate the camera using mouse position
      if (Input.GetKey("mouse 0"))
      {
          float mouse = Input.GetAxis("Mouse Y");
          transform.Rotate(new Vector3(mouse * sensitivity * -1, 0, 0));
          float look = Input.GetAxis("Mouse X") * sensitivity;
          transform.RotateAround(ball.transform.position, Vector3.up, look);
      } 
  }
}

--- /code ---

--- /task ---

--- task ---

Save your script and switch back to the Unity Editor.

In the Inspector set the 'Ball' variable of the `CameraRotate` script by dragging the Ball from the Hierarchy window onto the box. 

![The CameraRotate component with the Ball object set correctly.](images/camera-rotate-component.png)

--- /task ---

--- task ---

**Test:** Select the Game view tab and click on the 'Play' button to run your project.  

The camera will still follow the ball down the track but you can now control the view by moving your mouse to the left and right, up and down. 

**Tip:** You can change the sensitivity value in the inspector window to adjust the camera rotation speed. Remember that if you change this whilst in play mode the value will not be saved so you will need to update this once play has stopped. 

![An animated image of the Game view with the camera following the ball down the track. The camera is rotating to the left and right.](images/camera-control.gif)

Press the 'Play' button again to stop running your project. 

--- /task ---