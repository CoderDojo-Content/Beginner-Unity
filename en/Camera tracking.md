1. MazeRobo moves, but the camera always stays in the same place. That's going to be a problem if you try to add anything outside of the camera's initial field of vision. You can fix it though! Select the **main camera** and set the **transform** properties in the **inspector** as follows:
    
    * Position
        * X: 0
        * Y: 9
        * Z: -5
    * Rotation
        * X: 60
        * Y: 0
        * Z: 0
    * Scale
        * X: 1
        * Y: 1
        * Z: 1
        
2. Now you've changed the camera's angle (run the game to test it if you like!) but it still doesn't follow MazeRobo. To make that happen you'll have to update the camera's location every frame and to make that happen, you'll need another **script**. Create one (**Assets > Create > C# Script**) and call it "CameraMover". Put it in the "Scripts" folder.

3. At the start of the script, just inside the "CameraMover" class, add three **variables** like so:

    ```cs
        public class CameraMover : MonoBehaviour {
        
            public Transform tf;
	    public Transform playerTransform;
	    public Vector3 distanceBetweenPlayerAndCam;      
    ```
   
  These track the position of the camera (`tf`), the position of the player/MazeRobo (`playerTransform`) and the distance, in x,y,z terms, from the player to the camera (`distanceBetweenPlayerAndCam`).  

4. Now you need to set the initial distance between the player and the camera as the one you want to keep. Do this inside the `Start` function like so:

  ```cs
    void Start () {
      distanceBetweenPlayerAndCam = tf.position - playerTransform.position;
    }
	
  ```
