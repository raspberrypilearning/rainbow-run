## Create a ball 

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Create a ball using a **UV sphere** object. Make a script to control the camera and follow the ball down the track.
</div>
<div>
![An animated image of the Game view with the camera following the ball down the track. The camera is rotating to the left and right.](images/camera-control.gif){:width="300px"}
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

--- /task ---

--- task ---



--- /task ---

--- task ---



--- /task ---

--- task ---



--- /task ---

--- task ---



--- /task ---

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

Go to the Hierarchy window. Right-click on the 'Main Camera' and select **Align With View**. 

--- /task ---

### Control your camera 

--- task ---

Go to the Inspector window for the 'Main Camera' and click on the **Add Component** button. Type `script` and select **New Script**. Name your new script `CameraController`, then press <kbd>Enter</kbd>.

![The new CameraController script component on the Main Camera.](images/camera-component.png)

--- /task ---

--- task ---

Go to the Project window. The new script will be saved in the Assets folder:

![The new CameraController script in the Assets folder.](images/camera-assets.png)

Drag the new script to the 'Scripts' folder to organise your files:

![The new CameraController script now in the Scripts folder.](images/camera-script.png)

--- /task ---

--- task ---

Double click on 'CameraController' script. The script will open in a separate code editor. 

Copy or type this code to make the Main Camera look at the ball and move with the ball as the ball rolls down the track:

--- code ---
---
language: cs
filename: CameraController.cs
line_numbers: true
line_number_start: 1
line_highlights: 
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CameraController : MonoBehaviour
{
  public GameObject ball;
  private Vector3 prevBallPos;

  void Start()
  {
      // Calculate where the camera is in relation to the player (ball)
      transform.LookAt(ball.transform);
      prevBallPos = ball.transform.position;
  }

void LateUpdate()
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

Find the 'Ball' property of the Main Camera's CameraController script in the Inspector window.

Click on the circle to the right of the Ball property and choose the 'Ball' GameObject':

![The CameraController script component on the Main Camera with Ball property dropdown menu and 'Ball' selected.](images/ball-script.png)

--- /task ---

--- task ---

**Test:** Select the Game view tab and click on the 'Play' button to run your project.  

The ball will roll down the track and the camera will follow it. 

![An animated image of the Game view with the camera following the ball down the track.](images/camera-follow.gif)

--- /task ---

--- task ---

Press the 'Play' button again to stop running your project. 

Double click on 'CameraController' script and add code to use the mouse position to control the camera rotation angle:

--- code ---
---
language: cs
filename: CameraController.cs
line_numbers: true
line_number_start: 1
line_highlights: 7, 20, 21, 22, 23
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CameraController : MonoBehaviour
{
  public float sensitivity = 5f;
  public GameObject ball;
  private Vector3 prevBallPos;

  void Start()
   {
       // Calculate where the camera is in relation to the player (ball)
       transform.LookAt(ball.transform);
       prevBallPos = ball.transform.position;
   }

void LateUpdate()
   {
       float mouse = Input.GetAxis("Mouse Y");
       transform.Rotate(new Vector3(mouse * sensitivity * -1, 0, 0));
       float look = Input.GetAxis("Mouse X") * sensitivity;
       transform.RotateAround(ball.transform.position, Vector3.up, look);
       // Moves the camera by the same amount the ball has moved
       transform.Translate(ball.transform.position - prevBallPos, Space.World);
       prevBallPos = ball.transform.position;
   }
}

--- /code ---

--- /task ---

--- task ---

**Test:** Save your script and switch back to the Unity Editor. Select the Game view tab and click on the 'Play' button to run your project.  

The camera will still follow the ball down the track but you can now control the view by moving your mouse to the left and right, up and down. 

![An animated image of the Game view with the camera following the ball down the track. The camera is rotating to the left and right.](images/camera-control.gif)

--- /task ---