clc;
clear all;
close all;
x1 = input('Enter the first sequence x1(n) = ');
t1 = input('Enter Origin location Of Sequence x1(n) : ');
x2 = input('Enter the second sequence x2(n) = ');
t2 = input('Enter Origin location Of Sequence x2(n) : ');
l1 = length(x1);
l2 = length(x2);
ln = l1+l2-1;
X1 = [x1,zeros(1,l2)];
X2 = [x2,zeros(1,l1)];
for i = 1:l2+l1-1
y(i) = 0;
for j = 1:l1
if(i-j+1>0)
y(i) = y(i)+X1(j)*X2(i-j+1);
else
end
end
end
a = t1+l1-1;
t = t1:a;
subplot(4,1,1);
stem(t,x1);
disp(x1);
xlabel('Time--->');
ylabel('Amplitude--->');
title('First Sequence');
a = t2+l2-1;
t = t2:a;
subplot(4,1,2);
stem(t,x2);
disp(x2);
xlabel('Time--->');
ylabel('Amplitude--->');
title('Second Sequence');
tn = t1+t2;
a = tn+ln-1;
t = tn:a;
subplot(4,1,3);
disp('Convolved Sequence = ');
disp(y);
stem(t,y);
xlabel('Time--->');
ylabel('Amplitude--->');
title('Convolved Output');
% using inbuilt function
y1=conv(x1,x2);
subplot(4,1,4);
disp('Convolved Sequence using inbuilt fun= ');
disp(y1);
stem(y1);
xlabel('Time--->');
ylabel('Amplitude--->');
title('Convolved Output using inbuilt function');
