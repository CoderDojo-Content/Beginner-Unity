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
  Let's look at what you've got here. You can ignore the first three lines, for now. They're just the program setting up things it needs. Then you've got 
  
  ```cs
    public class RoboMover : MonoBehaviour {
  ```

  This is the start of a **class** (a blueprint of code) called "RoboMover". Don't worry about the `: MonoBehaviour` bit for now. Everything between this first `{` and the last `}` is inside the "RoboMover" class.

  Then you have two empty **functions** called "Start" and "Update". Right now, they're exactly the same except for their names, so let's just look at one quickly:
  
  ```cs
    void Update() {
    
    }
  ```

  A function is a set of instructions to do something, wrapped up in a label for the task that makes it easy to remember. For example, for a human, "Make a cup of tea" is a function. We know there are lots of steps to it and, at the end, you have a cup of tea. It would be silly to have to tell someone every step every time you wanted them to make you some tea. The same is true of asking the computer to do something. Much easier to teach it once, in one place, and then get it to do it over and over agin later!
  
  The first word in this **function** declaration is `void`. That means the **function** doesn't **return** anything. That is, it gives nothing back. "Make me a cup of tea" **returns** a cup of tea once all the instructions are done, but "Add milk" doesn't return anything, it just changes the cup of tea that already exists. So "Add milk" would be a `void` function!
  
  Next comes the name of the **function**, that easy label you can use to **call** the function from elsewhere in your code. Notice the brackets `()` beside it though. They're empty now, but they can be used to **pass** information into the function. For example: "Make me a cup of tea (with milk, two sugars)".
  
  Finally, you have the curly braces `{}`. Everything inside them is the set of instructions the program will follow when the **function** is called. For "Make me a cup of tea" that would be things like:
    * Boil water
    * Put water in teapot
    * Add teabag
    * etc.
    


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