# Digital Control
Digital control is a field that deals with phenomena occurring in a sample based system.

Classically, control algorithms are implemented through electrical circuits or hydraulic devices, and many s domain based control techniques are well known. However, due to the development of microprocessors, including DSPs, almost all of the control systems are now implemented in digital. Thus, digital control has begun to differ from conventional control in the continuous time domain. An examples are the zero order hold, which maintains the output signal for one sample, or the approximation of the controller in the s domain in the z domain. 

Therefore, when using the controller design method or the system analysis method in the s domain as it is, slight error occurs.
To design the controller to minimize this error or analyze the cause of the error in the designed system, everything must be done in the z domain rather than the s domain. 

There are several ways to convert s domain to z domain (detail explanations :  [link](http://kr.mathworks.com/help/control/ug/continuous-discrete-conversion-methods.html?requestedDomain=www.mathworks.com#bs78nig-8))
- Zero-Pole Matching Equivalents Transformation
- Tustin Approximation Transformation
- Zero-Order Hold Transformation (Backward Transformation)
- Zero-Order Hold  Reconstruction System Transformation

**Zero-Pole Matching Equivalents Transformation** is most likely the result of z transformation after sampling a continuous time domain signal or system.

![pole-zero-matched](https://user-images.githubusercontent.com/12868848/35570748-6e77b8a4-0613-11e8-8b38-a306ea169a16.PNG)

**Tustin Approximation Transformation** is a method that uses the bilinear approximation and is the best matching method in the frequency domain. It is mainly used when you want to make the frequency response the most uniform in systems where exponential is difficult to implement.

![tustin_method](https://user-images.githubusercontent.com/12868848/35570756-75e09b2e-0613-11e8-8a37-fafe452c541a.PNG)

**Zero-Order Hold Transformation** is a method also called backward transformation which represents the situation when the continuous time domain signal is discretized by the sample and hold method.

![backward](https://user-images.githubusercontent.com/12868848/35570779-80cced80-0613-11e8-9e83-426757d43ae0.PNG)

**Zero-Order Hold  Reconstruction System Transformation** is a zero-pole matching equivalents transformation method for a DAC block reconstructing a continuous time domain signal for a signal received through a zero order hold sampling. In fact, it is not a continuous to digital transformation method but a z domain representation method for a specific system. However, there are many places where this method is introduced as part of the c2d transformation method called "zero order hold transformation". Therefore, I will define the terms as "Zero-Order Hold  Reconstruction System Transformation" in this post separately.

![image](https://user-images.githubusercontent.com/12868848/35571319-1a14a90a-0615-11e8-8873-2cbca07a6371.png)

In this post, we will divide into the following two situations and explain in each case what kind of transformation is appropriate to apply
- system implementation
- system analysis

"System implementation" means implementation of filter or controller, and "system analysis" means analysis of stability of implemented system using frequency domain analysis techniques.