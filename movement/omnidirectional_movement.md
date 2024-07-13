# Omnidirectional movement using the mecanum wheels and angle from the joystick.
> Written by Piyaphat Liamwilai, Gemini team, Feng Shui Robotics team, based on the documents written by [Seamonsters](https://seamonsters-2605.github.io/archive/mecanum/)
### Concept
Mecanum wheel is a type of wheel, but what made it difference from all the other wheel is that it's omnidirectional. This is due to the rollers attached to the wheel that's exactly placed at 45 degrees. The concept that
will be talked about in this write-up is the ability to move in any direction using the angle that's calculated from the joystick.
### Knowing the radians
Most of joystick will returns only their x and y coordinates. We first have to calculate the radians of the x and y coordinates given from the joystick. To do this, you would have to do a little trigonometry. That is
arctan of y/x. To do this in Python, you would have to use `math.atan2(y, x)` that is in the `math` library of Python.
