# BezierCurve_Assignment
Bézier Curve Math & Physics
Bézier Curve

The curve shown in this project is a cubic Bézier curve built from four control points. The two outer points define the fixed ends of the rope, while the two inner points control how the curve bends.

Each point on the curve is calculated manually using the standard cubic Bézier equation:
B(t)=(1−t)^3 P0​+3(1−t)^2 tP1​+3(1−t)t^2 P2​+t3P^3
To draw the curve, the parameter  t is stepped from 0 to 1 in small increments, and the resulting points are connected on the screen.

Tangents

To visualize the direction of the curve, tangent vectors are computed using the derivative of the Bézier function:
B′(t)=3(1−t)^2 (P1​−P0​)+6(1−t)t(P2​−P1​)+3t^2(P3​−P2​)
These vectors are normalized and drawn as short line segments at several positions along the curve.

Motion & Physics

The middle control points move using a simple spring and damping model instead of snapping directly to the input. Each frame, a force pulls the point toward its target position while damping reduces oscillation:
acceleration = -k * (currentPosition - targetPosition) - damping * velocity
Velocity and position are updated over time, producing smooth, elastic motion that makes the curve behave like a flexible rope.​
