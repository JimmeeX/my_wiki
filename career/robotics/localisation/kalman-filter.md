# Kalman Filtering

Kalman Filtering is one type of localisation that determines the robot's current state \(eg, position, velocity, bearing\) through a combination of sensors and its state model \(eg, dead-reckoning\).

## A Simplification

Suppose that the robot moves in a 1D plane. It starts from the initial position, $x=0$, and moves at a constant velocity $v$. We can estimate the distance after $t$ seconds to be $x\_t=vt$. This represents our state model.

In the real-world, $x\_t=vt$ can approximate the distance travelled. However, in any robot application there will be errors. What if the ground isn't perfectly flat? What if there is friction that wasn't accounted for? What if the robot wasn't travelling at $v$, but a value close to it \(ie, encoding-based errors\)?

These issues will result in our state model $x\_t=vt$ to be inconsistent with the real location of the robot. This inconsistency or error will be small in the beginning, but it will slowly accumulate to bigger errors over time.

Kalman Filtering aims to reduce these errors by using one important feature on most robots...sensors! Suppose the robot had a sensor that could detect its distance from a wall placed at $x=10$. For example, if the robot's sensor gives a value of 3, we know roughly that the robot should be around $x=10-3=7$. This will add another way of estimating its position on top of the state model!

Now we know that the state model $x=vt$ is not perfectly accurate, but how about the sensor values? Nope, it is not perfect either! The sensor could sometimes pick up irrelevant things in the environment \(ie, noise\) that affects its readings as well.

Now let's consider the same situation. Let's assume the state model predicts the robot to be at $x=5$. The sensor on the robot predicts the robot to be at $x=6$. What can we do? Intuitively, we would take the average and say the robot is at $x=5.5$! This is ultimately what Kalman Filtering does behind its seemingly complicated maths.

## Resources

[Here](https://www.youtube.com/watch?v=bm3cwEP2nUo) is a humorous and informative explanation of Kalman Filtering using Pokemon.

