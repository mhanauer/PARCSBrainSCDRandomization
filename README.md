---
title: "Test"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
Need to figure out how randomly select for each person from baseline and intervention (not first for baseline) 7 values that do not include the three leading up to the change.

Let's try person one.  So want the first intervention start point plus at least 4 data points forward, so we can have the first three intervention data points no matter what.

Checklist
Make sure you are grabbing the right starting and ending values, make sure 4 makes sense, make sure you updating the names (e.g. personOneProbe is for person one not person two).

These are just for the intervention probes for person 2:5 we need to also randomly select when to get the CBMS for the baseline.
```{r}
personOne = c((6+4):35)
ProbeFunction = function(x){
 set.seed(12345)
x = as.data.frame(sample(x, 7))
colnames(x) = c("x")
x = x[order(x),]
x
}
personOneProbe = ProbeFunction(personOne); personOneProbe
```
Now person two.  
```{r}
personTwo = c((9+4):38)
ProbeFunction = function(x){
 set.seed(12345)
x = as.data.frame(sample(x, 7))
colnames(x) = c("x")
x = x[order(x),]
x
}
personTwoProbe = ProbeFunction(personTwo); personTwoProbe
```
Now person three 
```{r}
personThree = c((11+4):40)
ProbeFunction = function(x){
 set.seed(12345)
x = as.data.frame(sample(x, 7))
colnames(x) = c("x")
x = x[order(x),]
x
}
personThreeProbe = ProbeFunction(personThree); personThreeProbe
```
Now person four
```{r}
personFour = c((13+4):42)
ProbeFunction = function(x){
 set.seed(12345)
x = as.data.frame(sample(x, 7))
colnames(x) = c("x")
x = x[order(x),]
x
}
personFourProbe = ProbeFunction(personFour); personFourProbe
```
Now person five
```{r}
personFive = c((15+4):44)
ProbeFunction = function(x){
  set.seed(12345)
  x = as.data.frame(sample(x, 7))
  colnames(x) = c("x")
  x = x[order(x),]
  x
}
personFiveProbe = ProbeFunction(personFive); personFiveProbe
```
Now combine them so it is easier to view them
```{r}
probes = cbind(personOneProbe, personTwoProbe, personThreeProbe, personFourProbe, personFiveProbe); probes

```
Now I need to select 7 from the baselines for person's 2 through 5
Person 2 Baseline
```{r}
personTwoBase = c(1:8)
ProbeFunction = function(x){
  set.seed(12345)
  x = as.data.frame(sample(x, 7))
  colnames(x) = c("x")
  x = x[order(x),]
  x
}


personTwoProbeBase = ProbeFunction(personTwoBase); personTwoProbeBase
```
Person 3 Baseline
```{r}
personThreeBase = c(1:10)
ProbeFunction = function(x){
  set.seed(12345)
  x = as.data.frame(sample(x, 7))
  colnames(x) = c("x")
  x = x[order(x),]
  x
}
personThreeProbeBase = ProbeFunction(personThreeBase); personThreeProbeBase
```
Person 4 Baseline
```{r}
personFourBase = c(1:12)
ProbeFunction = function(x){
  set.seed(12345)
  x = as.data.frame(sample(x, 7))
  colnames(x) = c("x")
  x = x[order(x),]
  x
}
personFourProbeBase = ProbeFunction(personFourBase); personFourProbeBase
```
Person 5 Baseline
```{r}
personFiveBase = c(1:14)
ProbeFunction = function(x){
  set.seed(12345)
  x = as.data.frame(sample(x, 7))
  colnames(x) = c("x")
  x = x[order(x),]
  x
}
personFiveProbeBase = ProbeFunction(personFiveBase); personFiveProbeBase
```
Now combine them all make the changes
```{r}
personBaselineProbes = cbind(personTwoProbeBase, personThreeProbeBase, personFourProbeBase, personFiveProbeBase); personBaselineProbes

```

