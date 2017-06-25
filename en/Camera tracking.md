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