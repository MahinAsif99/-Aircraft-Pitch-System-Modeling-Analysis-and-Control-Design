# -Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design
An autopilot that controls the pitch of an aircraft.

1.Introduction

Aircraft or Airplane is the transport which is most commonly used by the military, navy, anarmy, etc. Aircraft movement control is a highly non-linear process. But the control of directionand movement plays a vital role in the airplane industry so as to avoid accidents, damage and soon. In aircraft, the stability and control are important parameters. There are three angles whichcan be used to control the motion such as yaw, roll and pitch for stability. In this project, themain focus is to control the pitch of the aircraft by making use of the PID controller. Pitchcontrol will help the plane to descend or ascend. Controlling of pitch can be done by adjustingthe elevator which is present at the rear side of the plane. Elevators are Flight Control Surfaces(FCS). Aircraft pitch is driven based on longitudinal dynamics. To control the pitch, theoptimization methods in particularly Firefly Algorithm and Particle Swarm Optimization areused to obtain optimized results. Comparison between above mentioned algorithms is done basedon the performance criteria and the optimization technique for the Aircraft pitch control isdetermined. A PID controller is an instrument used in industrial control applications to regulatetemperature, flow, pressure, speed and other process variables. PID (proportional integralderivative) controllers use a control loop feedback mechanism to control process variables andare the most accurate and stable controller.

2.Problem Statement
To design a feedback controller to satisfy the given design specifications.  
a.Overshoot less than 8%. 
b.Rise time less than 2 seconds. 
c.Settling time less than 8 seconds. 
d.Settling state error less than 2%. 

2.1 Literature Survey
Stability and control are much more complex for an airplane, which can move freely in three 
dimensions, than for cars or boats, which only move in two. A change in any one of the three 
types of motion affects the other two. 
•	AXIS OF FLIGHT: 
Imagine three lines running through an airplane and intersecting at right angles at the airplane’s 
center of gravity. 
 
a.Rotation around the front-to-back axis is called roll. The Ailerons Control Roll. 

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/d6121e4e-62fe-4519-bfe4-9a83553c1a0b)

b.Rotation around the side-to-side axis is called pitch. The Rudder Controls Yaw. 

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/516a0eeb-29a0-464d-a731-b990d905d1fe)

c.Rotation around the vertical axis is called yaw. The Elevator Controls Pitch. 

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/b28d87e5-67a2-422d-a436-57ae6d3b35de)

3.MATHEMATICAL MODELING: 
The basic coordinate axes and forces acting on an aircraft are shown in the figure given below. 

 ![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/af275223-7010-44a5-aff8-a219487eb434)

We will assume that the aircraft is in steady-cruise at constant altitude and velocity; thus, thethrust, drag, weight and lift forces balance each other in the x- and y-directions. We will alsoassume that a change in pitch angle will not change the speed of the aircraft under anycircumstance (unrealistic but simplifies the problem a bit). Under these assumptions, thelongitudinal equations of motion for the aircraft can be written as follows.

For this system, the input will be the elevator deflection angle δ(s) and the output will be the pitch angle θ(s) of the aircraft. The transfer function is given below:  
  ![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/1143db25-ef9c-4d23-baaf-5ccd077c4482)

4.CONTROLLER DESIGN 
A. ROOT LOCUS DESIGN: 

Root locus design is a common control system design technique in which you edit thecompensator gain, poles, and zeros in the root locus diagram. As the open-loop gain, k, of acontrol system varies over a continuous range of values, the root locus diagram shows thetrajectories of the closed-loop poles of the feedback system. For example, in the followingtracking system:

 ![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/4b70f4eb-9751-4d21-9049-056d8e02ae34)

 P(s) is the plant, H(s) is the sensor dynamics, and k is an adjustable scalar gain .The closed-loop poles are the roots of 
                                                                    𝛥(𝑠)=1+𝑘𝑃(𝑠)∗𝐻(𝑠) 
The root locus technique consists of plotting the closed-loop pole trajectories in the complex plane as ‘k’ varies. You can use this plot to identify the gain value associated with a desired set of closed-loop poles. 
•	A root locus plot shows all possible closed- loop pole locations as a parameter (usually a proportional gain K) is varied from 0 to infinity.  
•	We will employ the root locus to design our controller to place our system's closed-loop poles in locations that will result in behavior that satisfies our given requirements. 
•	We will specifically use MATLAB's SISO Design Tool to modify the system. 

B. PID DESIGN CONTROLLER: 
We will implement combinations of proportional (Kp), integral (Ki), and derivative (Kd) control 
in the unity feedback to achieve the desired system behavior. In PID controller design we use 
SISO TOOL. 
The PID controller is widely employed because it is very understandable and because it is quite 
effective. One attraction of the PID controller is that all engineers understand conceptually 
differentiation and integration, so they can implement the control system even without a deep 
understanding of control theory. Further, even though the compensator is simple, it is quite 
sophisticated in that it captures the history of the system (through integration) and anticipates the 
future behavior of the system (through differentiation).  
 
 ![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/4dc28304-0f2b-4b05-bce1-c024ac3dcd6e)

 ![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/ecad6d3d-ada2-447b-b01e-8f41225bf232)

5.PERFORMANCE EVALUATION: 
 
Initially plotting the root locus of the system to take a close look if the system is stable or not. 
Open loop is unstable and Close loop system is stable.  Then plotting the Bode plot since it 
lets to a frequency response at multiple frequencies. By doing that we can see the phase and 
gain margin of the system. 

5.1 Output
By implementing the code in matlab, we get:

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/175cc6c6-3eaa-4303-b4e3-76c203c4517c)

5.1.1 GRAPHS FOR OPEN LOOP SYSTEM: 
![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/6cc19917-8e79-447a-b517-6ebde44fc34d)

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/fc7705d1-874d-466a-b2d0-1597da670690)

Since it’s an open loop system, the system is unstable. 

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/13d27ec1-4961-4dd8-96c2-647055c7eb58)

infinite gain margin:  close loop will always be stable no matter how many gain we add. It is for unity feedback system. 

5.1.2 GRAPHS FOR Closed LOOP SYSTEM: 

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/32106e27-f808-40b7-ba54-afe7137f9cfb)

Since it’s an closed loop system, the system is stable. 

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/2247169e-7eeb-4fa4-b1de-aa26e866a663)

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/9ef4a759-7c8f-4ab3-b625-006ac831f9ac)

6. Simulink Model

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/cbe17a99-51ec-401f-9acf-334411cbd705)

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/2353ea7b-065d-4f66-9613-4dd4d8e6b073)

Since it’s a type 1 system, there is zero error.

7.Compensator:

For using a compensator, we introduce a gain, we get:

k=10; 
bode(Go) % open loop 
hold on 
bode(k*Go) 

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/06b2a211-d623-4cd0-8158-229d715b1e1c)

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/244f6d4c-7f60-420e-a4c5-496483ca6c12)

When the phase margin decreases, there is an overshoot in the system. Rise time has decreased since we have actually up the gain of the system. Settling has also come down.

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/f0698e47-21d8-435b-8f42-8f694e7d1018)

Decrease in Phase margin, causes increase in overshoot. This means that we need a PID controller. This will increase the Phase and shift gain to the RIGHT. We get a hight phase which means low overshoot and improved response time.  

sisotool('rlocus', Go)

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/a85bdaaf-c740-47d4-a242-a6c3616e7a41)

![image](https://github.com/MahinAsif99/-Aircraft-Pitch-System-Modeling-Analysis-and-Control-Design/assets/148430248/e67d08b0-2c8b-4b5d-a504-825585a6b880)


















