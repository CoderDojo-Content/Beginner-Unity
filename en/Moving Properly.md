1. MazeRobo moves, but it's a little... weird. It doesn't turn around to see where it's going. You can fix that! Go back into the "RoboMover" script and add this new  line under `rb.MovePosition`, like so:
  ```cs
    rb.MoveRotation (Quaternion.LookRotation (desiredDirection, Vector3.up));
  ```
  This line makes MazeRobo look where it's going! Run the game and check it out!

2. MazeRobo does look where it's going, but as soon as you release the controls it springs back to looking in the original direction. You can fix this too! The problem is that direction is essentially 0 and when there's no active input from the player, the input is 0. You need to set it up so that MazeRobo will only turn based on active player input. The check you'll use for this in the code is: **if** the player's input is bigger than a very small number (0.01) **then** move and turn. So nothing will happen on that default 0.

3. The first thing you'll need to do is wrap all your existing direction change code in an **if** statement, which only runs the code inside it if the condition in the brackets is **true**.

  ```cs
    // Update is called once per frame
    void Update () {
    
    	if (true) {
    		Vector3 desiredDirection = new Vector3 (Input.GetAxis ("Horizontal"), 0.0f, Input.GetAxis ("Vertical"));
    		desiredDirection = moveSpeed * desiredDirection;
    		desiredDirection = Time.deltaTime * desiredDirection;
    		rb.MovePosition (rb.position + desiredDirection);
    		rb.MoveRotation (Quaternion.LookRotation (desiredDirection, Vector3.up));
    	}
    }
  ```
  
  Right now, you're forcing the statement to be **true** by actually passing it `true` as the condition. Run the game and check it's all still working.