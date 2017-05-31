1. Let’s create a ground plane for MazeRobo to move about on! Start by adding a **Quad** to be the ground (**GameObject > 3D Object > Quad**). Change the name of this object from "Quad" to "Ground" using the **inspector**.
 
2. In the **inspector** for this object under **transform** set the **X** **rotation** to 90. In the **transform**'s **scale** section, enter the values of: 

 * X=40.96
 * Y=40.96
 * Z=1
 
3. Gah! MazeRobo’s stuck halfway into the ground! Move her up by one meter! Select MazeRobo and, in the **inspector** under **transform** set the following coordinates: 

  * X=0
  * Y=1
  * Z=0
 
4. Now we’ll add a wall to start our maze! 
Create a Cube (GameObject > 3D Object > Cube) 
Give the Transform Position the values X=-2, Y=1.5 and Z=0. 
Make the Y Scale 3 and rename the object to ‘Wall’!
 
4. We’ll make a new material for the Wall (Assets > Create > Materials) - now rename it WallBlue and give it a (surprise!) Blue colour! Later on, we’ll turn this wall into a maze for MazeRobo to explore!
