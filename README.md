# radar_range
Aim

To evaluate and plot the maximum radar range (Rmax) as a function of transmitted power(Pt),Antenna Gain(G),Wavelength(λ) using the Radar Range Equation in Scilab.

Equipments Needed

1.Computer with i3 Processor

2.SCI LAB


Algorithm


1.Start the program.

2.Initialize constants: radar cross-section (σ), minimum detectable signal (Smin), and fixed values for Pt and G.

3.Vary one parameter (Pt, G, or λ) at a time while keeping others constant.

4.Apply the radar range equation:

5.Compute Rmax for each case:

Rmax vs Pt

Rmax vs G

Rmax vs λ

6.Plot all three graphs in a single window using subplots.

7.End the program.



Procedure

1.Open Scilab software.

2.Create a new script and enter the provided code.

3.Define all the required parameters:

sigma = 1

Smin = 1e-10

Pt_fixed = 5000

G_fixed = 1000

4.Define varying ranges:

Pt = 100:100:10000

G_array = 100:100:2000

lambda_array = 0.01:0.01:0.1

5.Compute the maximum range for each parameter using the radar range equation.

6.Use subplot() and plot() commands to display three graphs:

First graph: Rmax vs Pt

Second graph: Rmax vs G

Third graph: Rmax vs λ

7.Run the program and observe the output plots.


Program
````
sigma = 1;
Smin = 1e-10;
Pt_fixed = 5000;
G_fixed = 1000;
Pt = 100:100:10000;
Rmax_Pt = ((Pt .* (G_fixed^2) .* (0.03^2) .* sigma) ./ ((4*%pi)^3 * Smin)).^(1/4);
G_array = 100:100:2000;
Rmax_G = ((Pt_fixed .* (G_array.^2) .* (0.03^2) .* sigma) ./ ((4*%pi)^3 * Smin)).^(1/4);
lambda_array = 0.01:0.01:0.1;
Rmax_lambda = ((Pt_fixed .* (G_fixed^2) .* (lambda_array.^2) .* sigma) ./ ((4*%pi)^3 * Smin)).^(1/4);
clf(); 
subplot(3,1,1);
plot(Pt, Rmax_Pt);
subplot(3,1,2);
plot(G_array, Rmax_G);
subplot(3,1,3);
plot(lambda_array, Rmax_lambda);
````


Output Waveform

![WhatsApp Image 2025-10-22 at 10 11 26_7d8e9ddf](https://github.com/user-attachments/assets/a4777739-87de-4277-84e9-033a56157e94)



Result

Three plots are obtained in a single figure window:

1.Rmax vs Pt: The maximum radar range increases as transmitted power increases.

2.Rmax vs G: The radar range increases with antenna gain.

3.Rmax vs λ: The radar range increases with wavelength.

Hence, it is concluded that the radar range depends directly on transmitted power, antenna gain, and wavelength, and is limited by the minimum detectable signal.






