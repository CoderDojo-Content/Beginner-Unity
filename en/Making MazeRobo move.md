1. Create a new folder (**Assets > Create > Folder**) inside the Project Pane "Assets" folder (you make need to click on this in the **projects** section first), and call it "Scripts".
Create a new C# script (**Assets > Create >  C# Script**) in this folder and call it "RoboMover".

2. Double-click on "RoboMover" to open it in your editor. In the editor. You should see code like this:
	
	```cs
	using System.Collections;
	using System.Collections.Generic;
	using UnityEngine;
	
	public class RoboMover : MonoBehaviour {
	
		// Use this for initialization
		void Start () {
			
		}
		
		// Update is called once per frame
		void Update () {
			
		}
	}
	```

Add a public float called moveSpeed and initialise it at 4.0f
Add a public Rigidbody called rb - this will be how we refer to the Rigidbody component!
Add a public Transform called tf - and this is how we refer to the Transform component!
Remove the Start section, we don’t need it here.
In the Update function,
Get the direction you want from the input (controller stick or keyboard) -> Create a new Vector3 called desiredDirection and assign it the input from the player.			Vector3 desiredDirection = new Vector3(Input.GetAxis("Horizontal"), 0.0f, Input.GetAxis("Vertical"));
Multiply the desiredDirection by the movement speed we set for MazeRobo -> Assign desiredDirection the moveSpeed multiplied by desiredDirection.				desiredDirection = moveSpeed * desiredDirection;
Multiply the desiredDirection by a special value that makes the character move at the desired speed no matter what computer it's on -> Assign desiredDirection the Time.deltaTime value multiplied by desiredDirection.					desiredDirection = Time.deltaTime * desiredDirection;
Tell the rigidbody to add our new direction to our current position - so our body moves! rb.MovePosition(rb.position + desiredDirection);
That should do it - we’re close to getting MazeRobo moving now!

Back in Unity, drag and drop your RoboMover script from the scripts folder and onto the MazeRobo gameobject in the Hierarchy. You can see that script is now present in MazeRobo’s inspector, under the Rigidbody.
 
There are two empty fields in the RoboMover script - Rb and Tf. These stand for Rigidbody and Transform - and if we click-and-drag the names of these components from their places in the Inspector and into their respective fields, RoboMover (the script) will have all the info it needs to move MazeRobo!

 
Get back into Unity and click on the big ‘Play’ button on the top centre of the Unity interface...
MAZEROBO MOVES!
