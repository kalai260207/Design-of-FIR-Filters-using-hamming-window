# Design-of-FIR-Filters-using-hamming-window

# DESIGN OF HIGH PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of high pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
```clc;
clear;
close;

// Filter specifications
M = 50;            // Filter order
fc = 0.4;          // Normalized cutoff frequency (0 to 0.5)

// Sample points
n = 0:M;

// Ideal impulse response of High Pass Filter
hd = zeros(1, M+1);
for i = 1:M+1
    if i == (M/2 + 1) then
        hd(i) = 1 - 2*fc;
    else
        hd(i) = (-sin(2*%pi*fc*(i - (M/2 + 1)))) / (%pi*(i - (M/2 + 1)));
    end
end

// Hamming window
w = 0.54 - 0.46 * cos(2*%pi*n/M);

// Apply window
h = hd .* w;

// Plot Impulse Response
figure(1);
plot(n, h);
xlabel("n");
ylabel("h(n)");
title("Impulse Response of High Pass FIR Filter using Hamming Window");
xgrid();

// Frequency Response
[H, f] = frmag(h, 512);
figure(2);
plot(f, H);
xlabel("Normalized Frequency");
ylabel("|H(f)|");
title("Magnitude Response of High Pass FIR Filter using Hamming Window");
xgrid();
```


# OUTPUT
<img width="850" height="529" alt="image" src="https://github.com/user-attachments/assets/9212908e-0600-494c-8373-b8352b5addda" />
<img width="842" height="530" alt="image" src="https://github.com/user-attachments/assets/e0f166bf-4152-459f-90ed-5e80923b7087" />


# RESULT
The High Pass FIR digital filter was successfully designed and its waveform was plotted using the Hamming window method in Scilab.
