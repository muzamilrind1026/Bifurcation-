# Bifurcation-
These codes are for bifurcation for Matlab Tool.
clc;
clear all;
m=1000;
lm=linspace(3.5,4,m);
x0=.3;
n=2000;
x=zeros(m,n);
for i=1:m
    for j=1:n
        if j==1
           x(i,j)=x0; 
        else
            x(i,j)=lm(i)*x(i,j-1)*(1-x(i,j-1));
        end
        
    end
    
end

A=x(:,(n-50):n);

figure
plot(lm,A,'m.','MarkerSize',3);
ylabel('x(n)')


# Code 

% Program 3d: Bifurcation diagram of the logistic map.
clear
itermax=100;
finalits=30;finits=itermax-(finalits-1);
for r=0:0.005:4
    
    x=0.4;
xo=x;
for n=2:itermax
xn=r*xo*(1-xo);
x=[x xn];
xo=xn;
end
plot(r*ones(finalits),x(finits:itermax),'','MarkerSize',1)
hold on
end
fsize=15;
set(gca,'XTick',0:1:4,'FontSize',fsize)
set(gca,'YTick',0:0.2:1)
xlabel('{\mu}','FontSize',fsize)
ylabel('\itx','FontSize',fsize)
hold off
function [y]=myf1(x)

if x<=-2
    
    y=x^2;
end

if -2<x && x<=0
    
    y=1-x;
    
end

if 0< x && x<2
    
    y=exp(x);
    
end

if x>= 2
    
    y=x^3-3*x+2;
end
end

This is MATLAB code for generating a sequence using the logistic map:

clc;
clear all;
syms x;
f=x^2+3;
;
lm=2;
x0=.6;
A=zeros(1,1000);
A(1)=x0;
for i=2:1000
    A(i)=lm*A(i-1)*(1-A(i-1)); 
end

This MATLAB code is generating a bifurcation diagram for the quadratic map
clc;
clear all;
m=2000;
C=linspace(-2,.24,m);
x0=0;
n=10000;
A=zeros(m,n);
for i=1:m
    
        f=@(x) x^2+C(i);
        
    for j=1:n
        
        if j==1
            
            A(i,j)=x0;
            
        else
            A(i,j)=f(A(i,j-1)); 
        end
        
        
    end
end
B=A(:,(n-40):n);

plot(C,B,'.','MarkerSize',3);






clear
fsize=15;
nmax=10;halfm=nmax/2;
t=zeros(1,nmax);t1=zeros(1,nmax);t2=zeros(1,nmax);
t(1)=.5;

c=3.8282;

f=@(x) x^2+c;


axis([0 1 0 1]);
for n=1:nmax
t(n+1)=f(t(n));
end
for n=1:halfm
t1(2*n-1)=t(n);
t1(2*n)=t(n);
end
t2(1)=0;t2(2)=t(2);
for n=2:halfm
t2(2*n-1)=t(n);
t2(2*n)=t(n+1);
end
hold on
plot(t1,t2,'r');
fplot('f(x)',[0 1]);
x=[-2 2];y=[-5 5];
plot(x,y,'g');
hold off
%title(�Graphical iteration for the tent map�)
set(gca,'xtick',[-2 2],'Fontsize',fsize)
set(gca,'ytick',[-5 5],'Fontsize',fsize)
xlabel('x','Fontsize',fsize)
ylabel('f_{\mu}','Fontsize',fsize)





