# ggplot2-examples
Some graphics examples for ggplot2 using GLM.

`library(ggplot2)`

`varY<-c(0,10,20,30,40,50,20,30,43,28)`

`varX1<-c(0,11,22,31,44,50,24,34,12,45)`

`varX2<-c("A","B","A","B","C","C","A","B","C","A")`

`data<-data.frame(varY,varX1,varX2)`

`theme_set(theme_bw())`

### Base Plot
`gg <- ggplot(data, aes(x = varX1, y = varY, color = factor(varX2))) + geom_point() + geom_smooth(method=glm, se=FALSE) + labs(subtitle="Unknow data", title="Example plot", y="Categorical Y-Var", x="Categorical X-Var1") + scale_x_continuous(limits=c(0,55))`

### Modify theme components
`gg2 <- gg + theme(axis.title.x=element_text(size=12), axis.title.y=element_text(size=12), axis.text.x=element_text(size=10), axis.text.y=element_text(size=10))`

### Modify legend
`gg3 <- gg2 + scale_color_discrete(name="Treatment", labels = c("TA","TB","TC"))`

### Plot
`gg3`

![plot](https://s10.postimg.org/y56gh5crd/Rplot.png)

#### For poisson data
`ggplot(data, aes(x = varX1, y = varY, color = factor(varX2))) + geom_point() + geom_smooth(method=glm,method.args=list(family=poisson), se=TRUE)`
