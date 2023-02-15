## Control the ball

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will create a script that uses the keyboard to control the ball. Then add a reset button to respawn your ball at the top of the track.
</div>
<div>
![The output of step 2.](images/step2-output.png){:width="300px"}
</div>
</div>

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
Around the world people use different computer keyboard layouts and this can impact the common keys used for navigation. An example of this is in the <span style="color: #0faeb0">**<kbd>QWERTY</kbd>**</span> and <span style="color: #0faeb0">**<kbd>AZERTY</kbd>**</span> layouts. A <kbd>QWERTY</kbd> keyboard user will likely use keys <span style="color: #0faeb0">**<kbd>WASD</kbd>**</span> to move around in a game but an <kbd>AZERTY</kbd> keyboard user will likely use keys <span style="color: #0faeb0">**<kbd>ZQSD</kbd>**</span>. These are just two examples, which keys would you use? 
</p>

### Apply force on key press

--- task ---

Go to the Inspector window for the 'Ball' and click on the **Add Component** button. Type `script` and select **New Script**. Name your new script `BallController`, then press <kbd>Enter</kbd>.

--- /task ---

--- task ---

Go to the Project window. The new script will be saved in the Assets folder.

Drag the new script to the 'Scripts' folder to organise your files.

--- /task ---

--- task ---

Double click on 'BallController' script. Copy or type this code to make the Ball move to the left when you press <kbd>A</kbd> and right when you press <kbd>D</kbd>:

**Choose:** These instructions are based on using the keys <kbd>WASD</kbd> to control movement. If you want to use different keys you can change `Input.GetKey(KeyCode.A)` and `Input.GetKey(KeyCode.D)` to the keys you want to use. 

--- code ---
---
language: cs
filename: BallController.cs
line_numbers: true
line_number_start: 1
line_highlights: 
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;


public class BallController : MonoBehaviour
{
   private Rigidbody rb;
   public Transform cameraTransform;

   // Start is called before the first frame update
   void Start()
   {
       rb = this.GetComponent<Rigidbody>();
       rb.transform.forward = cameraTransform.forward;

   }

   // FixedUpdate is called once per fixed frame-rate frame
   void FixedUpdate()
   {  
       // Calculates cameraTransform.forward without the y value so the ball doesn't move up and down on the Y axis
       Vector3 forward = new Vector3(cameraTransform.forward.x, 0, cameraTransform.forward.z).normalized;
       Vector3 right =  Quaternion.AngleAxis(90, Vector3.up) * forward;
       Vector3 left = -right;

       if (Input.GetKey(KeyCode.D))
       {
           rb.AddForce(right * 5f);
       }

       if (Input.GetKey(KeyCode.A))
       {
           rb.AddForce(left * 5f);
       }
   } 
}

--- /code ---

--- /task ---

--- task ---

Save your script and switch back to the Unity Editor and click on the 'Ball' GameObject in the Hierarchy window.

Find the 'Camera Transform' property of the Ball's BallController script in the Inspector window.

Click on the circle to the right of the Camera Transform property and choose the 'Main' GameObject':

![The CameraController script component on the Main Camera with Ball property dropdown menu and 'Ball' selected.](images/ball-script.png)

--- /task ---

--- task ---



--- /task ---

--- task ---



--- /task ---

### Add a reset button

--- task ---



--- /task ---

--- task ---



--- /task ---