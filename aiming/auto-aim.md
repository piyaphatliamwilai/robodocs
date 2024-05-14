# MakeX: Auto Aim
> Written by Piyaphat Liamwilai and the CS6th team.
> Updated, 14/5/24.
### Concept
The concept of auto aim that we are talking about in this writeup is the ability for the robot to calculate the most optimal angles when the robot detected a target so that the robot can rotate to the angles and shoot at the target.
### But how?
While the concept may sounds like a dream but is it really possible? We would need to calculate a lot of trigonometry and even then, we have to know the robot position. Is it actually possible? 
### Finding out the robot position
This is possibly the most problometic part of the whole entire process. Because without the position of robot, it's almost impossible to calculate any of the values. So then, how do we find out the robot?
### Using the built-in accelerometer
After a little bit of searching in the official documentation of NovaPi, the board used in the MakeX Challenger competition. We are able to find out that there are accelerometer built into the board and are even able to find out the acceleration of all the dimensions (X, Y, Z). But, we only have the acceleration values. Not the X, Y, Z. Then how are we going to use this values to substitute instead of the normal X, Y, Z coordinates.
### Utilizing the accelerometer
Now instead of just using the acceleration value in the trigonometry calculation. Instead, we are going to track the acceleration and keep updating the values with every acceleration updates.
```py
# position values
pos_x = 0
pos_y = 0
pos_z = 0

def update_position():
  global pos_x, pos_y, pos_z
  # adding each acceleration values
  pos_x += novapi.get_acceleration("x") 
  pos_y += novapi.get_acceleration("y")
  pos_z += novapi.get_acceleration("z")

while True:
  update_position() # call in a while loop
```

---
