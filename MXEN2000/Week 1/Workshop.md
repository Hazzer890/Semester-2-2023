“The output shaft of a motor-gearbox assembly produces a maximum power of 90kW, maximum torque 60kNm and maximum speed 6rad/s, and is used to pull a 20 tonne iron ore cart up a 10º flat slope. If the cart is pulled via a rope around a pulley of diameter 40cm, what is the cart’s maximum acceleration when the cart is travelling at 1km/hr? What is the maximum speed the cart can attain? ”
```Matlab
powerMax = 90000 %W
torqueMax = 60000 %Nm
speedMax = 6 %rad/s
cartMass = 20000 %kg
slopeAngle = 10*pi/180 %rad
pulleyDiameter = 0.4 %m
gravity = 9.8
```

## Cart’s maximum acceleration when the cart is travelling at 1km/hr:
```
pulleyRadius = pulleyDiameter/2;
velocity = 1000/3600;
```
$$\omega=\frac{velocity}{radius} $$
```
angularVelocity = velocity/pulleyRadius;
```
$$
Torque=T_{max}-\frac{T_{max}}{\omega_{max}}\omega
$$
```
torque = torqueMax - (torqueMax/speedMax)*angularVelocity;
```
$$ Tension=\frac{torque}{radius} $$
```
tension = torque/pulleyRadius;
```
[Insert free-body Diagram]
$$ 
a = (Tension – m*g*sin(slope\_angle)) / m
$$
```
disp('RESULT:')
acceleration = (tension-cartMass*gravity*sin(slopeAngle))/cartMass
```

RESULT:
acceleration = 9.8260

## Maximum Velocity
```
velocity=[0:0.5:5]*1000/3600;
```
Repeat above for vectors:
```
angularVelocity = velocity/pulleyRadius;
torque = torqueMax - (torqueMax/speedMax)*angularVelocity;
tension = torque/pulleyRadius;
acceleration = (tension-cartMass*gravity*sin(slopeAngle))/cartMass;
```
Plot:
```
figure(1)
plot(acceleration,velocity)
xlabel('acceleration [m/s^2]')
ylabel('velocity  [m/s]')
grid on
```
Acceleration is zero when:
$$ Tension=m*g*\sin(slope\_angle)\\ $$
```
tension = cartMass*gravity*sin(slopeAngle);
torque = tension*pulleyRadius;
velocityMax = pulleyRadius*(torqueMax-torque)*speedMax/torqueMax;
```
Plot max velocity:
```
figure(1)
hold on
plot(0, velocityMax,'r.')
hold off
```

![](file:///C:\Users\harry\AppData\Local\Temp\ConnectorClipboard1041403214567764340/image16907721124500.png)

## Was I right?!
```
omega=0:0.1:speedMax;
torque=torqueMax-(torqueMax/speedMax)*omega;
power=torque.*omega;
```
Plot
```
figure(2)
plot(omega,power)
hold on
plot([0 speedMax], [powerMax powerMax], 'g--')
grid on
xlabel('angular velocity')
ylabel('power')
hold off
```
![](file:///C:\Users\harry\AppData\Local\Temp\ConnectorClipboard1041403214567764340/image16907721928730.png)
