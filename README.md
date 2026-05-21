# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
## DFT USING DIRECT METHOD
```
clc;
clear;

N=input("Length of the sequence N:");
x=input("Input Sequence x(n):");

if length(x)<> N then
    error("Length of x(n) must be equal to N");
end

x_direct=zeros(1,N);

for k=0:N-1
    sum_val=0;
    for n=0:N-1
        sum_val=sum_val+x(n+1)*exp(-%i*2*%pi*k*n/N);
    end
    x_direct(k+1)=sum_val;
end

x_direct=clean(x_direct);

disp("DFT using Direct Method");
disp(x_direct);

mag=abs(x_direct);
phase=atan(imag(x_direct),real(x_direct));

disp("Magnitude Spectrum");
disp(mag);

disp("Phase Spectrum");
disp(phase);

n=0:N-1;
k=0:N-1;

clf;

subplot(3,1,1);
plot2d3(n,x);
title("Input Sequence x(n)");

subplot(3,1,2);
plot2d3(k,mag);
title("Magnitude Spectrum");

subplot(3,1,3);
plot2d3(k,phase);
title("Phase Spectrum");
```
## DFT USING FFT ALGORITHM
```
clc;
clear;

N=input("Length of the sequence N:");
x=input("Input Sequence x(n):");

if length(x)<> N then
    error("Length of x(n) must be equal to N");
end

x_fft=fft(x);

disp("DFT using FFT");
disp(x_fft);

mag=abs(x_fft);
phase=atan(imag(x_fft),real(x_fft));

disp("Magnitude Spectrum");
disp(mag);

disp("Phase Spectrum");
disp(phase);

n=0:N-1;
k=0:N-1;

clf;

subplot(3,1,1);
plot2d3(n,x);
title("Input Sequence x(n)");

subplot(3,1,2);
plot2d3(k,mag);
title("Magnitude Spectrum |X(k)|");

subplot(3,1,3);
plot2d3(k,phase);
title("Phase Spectrum Angle X(k)");
```


# OUTPUT: 
## DFT USING DIRECT METHOD
<img width="1918" height="1078" alt="Screenshot 2026-05-21 152649" src="https://github.com/user-attachments/assets/1b59eb91-9495-4e7e-8567-24b1edfd8314" />


## DFT USING FFT ALGORITHM
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/5985bbbc-edf5-47f9-a0c8-18104a7fe951" />




# RESULT: 
Thus, the Discrete Fourier Transform (DFT) of the given input sequence was successfully computed using both the Direct Method and the Fast Fourier Transform (FFT) algorithm in Scilab. The magnitude and phase spectra were obtained and plotted, and the results from both methods were found to be the same.
