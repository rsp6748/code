clc
clear all
close all
xk=input('Enter the DFT sequence:  ');
N=input('Enter number of points in IDFT:  ');
k=0:N-1;
subplot(3,2,1);
stem(k,xk);
xlabel('frequency resolution');
ylabel('amplitude');
title('DFT Sequence'); 
N1=length(xk);
xk=[xk zeros(1,(N-N1))];
n=0:N-1;
k=0:N-1;
nk=n'*k;
wn=exp((i*2*pi)/N);
wnnk=wn.^nk;
xn=(xk*wnnk)*(1/N);
 
% IDFT x(n)
disp('IDFT');
disp(xn);
% plot IDFT
subplot(3,2,2);
stem(n,real(xn));
xlabel('time');
ylabel('amplitude');
title('signal REAL PART');
subplot(3,2,3);
stem(n,imag(xn));
xlabel('time');
ylabel('amplitude');
title('signal IMAGINARY PART ');
subplot(3,2,4);
stem(n,abs(xn));
xlabel('time');
ylabel('amplitude');
title('signal AMPLITUDE SPECTRA '); 
z=atan2(real(xn),imag(xn));
subplot(3,2,5);	
stem(z);
xlabel('time');
ylabel('THETA');
title('signal PHASE SPECTRA ');
