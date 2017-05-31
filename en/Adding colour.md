1. Create a new folder (**Assets > Create > Folder**) and call it "Materials".
2. Now make two **materials** (**Assets > Create > Materials**) called "EyeBlack" and "NoseRed" and drag them into the the "Materials" folder in the "Project" pane at the bottom of the screen.
3. You can set the colour of a material by changing its **albedo** value in the **inspector**. Click on the rectangle next to the dropper icon and a colour picker should open.

  ![](/assets/colour picker.png)

  Make EyeBlack’s albedo value black and NoseRed’s albedo value red.

4. With the Shades object selected, look at the **Mesh Renderer** section of the **inspector** and expand the "Materials" subsection. Click on the small circle to the right of ‘Element 0’ and select EyeBlack. Now we have black shades!
Do the same for the Nose object as you did for the Shades object, only now select the NoseRed material. Now we have a red nose!
4. MazeRobo needs a Rigidbody component that we can use to move her about and interact with the physical world. With MazeRobo selected, click on Component > Physics > Rigidbody. In the Rigidbody, open up the Constraints dropdown and set Freeze Rotation X, Y and Z to True (tick the boxes! =). In Freeze Position, set Y to True (tick the box!).
