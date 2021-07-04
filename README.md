# FOC-of-PMSM-MInor-Project

## Introduction

Electric motors are extremely important to modern-day life and are used in many different applications ranging from vacuum cleaners, dishwashers, computer printers, fax machines etc. A permanent-magnet synchronous motor (PMSM) uses permanent magnet embedded in the steel rotor to create a constant magnetic field. The stator carries windings connected to an AC supply to produce a rotating magnetic field.
PMSM operations were first restricted to basic DC motor circuits with minimal power input and high performance index. However, due to the later improvements in machines and because of their advantages such as compactness, cost performance, power density, lower size, and improved efficiency, permanent magnet synchronous motors (PMSM) have become widespread in industry. This motor is best used in situations where high speed performance is required. With elimination of a commutator, PMSM is become more reliable than a DC motor and become more efficient than an induction motor because the production of the rotor flux is from a permanent magnet. The image below shows the construction of PMSM.

![PMSM](https://user-images.githubusercontent.com/67676040/124380763-2c5adc00-dcdc-11eb-93e9-a4777df9ce3c.png)

However, the PMSM system is not easy to control because it is a nonlinear multivariable system and its performance can be highly affected by parameters variations in the run time. For applications which require fast dynamic response for speed and torque changes, sophisticated control techniques are required. The various control techniques that are used to regulate speed of PMSM drive are explained below: 

1. Scalar control: The principle of the scalar control is to maintain a constant V/Hz ratio almost through the whole speed range operation since only the magnitude and frequency of the supply voltages is controlled. It is only useful for applications which does not require high dynamic performance like fans, pumps, blowers, etc.

2. Vector Control: When compared to scalar control, vector control performs better. Vector control solves practically all of scalar control's drawbacks. The primary goal of vector control is to regulate not only the magnitude and frequency of supply voltages, but also their angle. In other words, the magnitude and angles of the space vectors are regulated. There are several types of vector controls, the most prevalent of which are DTC and FOC.

    - Direct torque control (DTC) is high performance control strategy. In a DTC drive applications, electromagnetic torque and flux linkage are controlled directly and independently by the selection of optimum inverter switching modes of operation.
    - Field oriented control (FOC) technique is used for synchronous motor to evaluate as a DC motor. The stator windings of the motor are fed by an inverter that generates a variable frequency variable voltage. Here instead of controlling the inverter frequency independently, phase of the output wave and the frequency are controlled using a position sensor. The position information can either be retrieved by a sensor or using sensor less control algorithms based on back-emf information or signal injection.

This project focuses on the closed loop field oriented control (FOC) of PMSM.

## Objectives

- Mathematical modelling of PMSM.
- Mathematical model implementation in Simulink.
- Field oriented control of PMSM in MATLAB.

## Algorithm

1. Measure the motor phase currents.
2. Transform them into the two phase system (a, b) using Clarke transformation.
3. Calculate the rotor position angle.
4. Transform stator currents into the d, q-coordinate system using Park transformation.
5. The stator current torque (i_sq) and flux (i_sd) producing components are controlled separately by the controllers.
6. The output stator voltage space vector is transformed back from the d, q-coordinate system into the two phase system fixed with the stator by inverse Park transformation.
7. Using the space vector modulation, the output three-phase voltage is generated.
8. Calculate mechanical speed after every discrete PWM cycles.

## Block Diagram

![image](https://user-images.githubusercontent.com/67676040/124380871-e8b4a200-dcdc-11eb-829f-b376740b81cd.png)

## Implementation in MATLAB/Simulink

Permanent Magnet Synchronous Motor Model in Simulink:

![image](https://user-images.githubusercontent.com/67676040/124380921-34674b80-dcdd-11eb-82bd-e039023ea8a7.png)

Field Oriented Control of PMSM in Simulink:

![image](https://user-images.githubusercontent.com/67676040/124380953-814b2200-dcdd-11eb-84fe-228b05732f18.png)

Theory about Space Vector Pulse Width Modulation: https://www.youtube.com/watch?v=nh9TD2M2r-o&t=234s 

# Conclusion

The simulation files of both PMSM and PMSM with FOC are uploaded in the repository along with a couple of test results. The simulations are done in MATLAB 2021a.

Hence, we can conclude that FOC is the standard regulator for Permanent Magnet Synchronous Motors. The chief constituents of this algorithm for example SVPWM and PI controllers are error less models with constant performance defined over a set of parameters.

