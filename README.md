# Lasso typeoptimization

## Univariate

Example: (beta-5)^2+7\*|beta|

Algorithm:

l'=2(beta-5)+7\*beta/|beta|

l''=2+7/|beta|

beta=beta-l'/l''

```
x<-5
beta<-10

for(ii in 1:1000){
  l1<-2*(beta-x)+7*sign(beta)
  l2<-2+7/abs(beta)
  beta<-beta-l1/l2
  if(abs(beta)<0.01)break
  abline(h=beta)
  show(beta)
}

## check result

optimize(f=function(b)(b-x)^2+7*abs(b),c(-10,10))

b<-seq(-10,10,0.01)
y<-(b-x)^2+7*abs(b)

plot(b,y)
b[which.min(y)]
```

## Multivariate
