## Quiz

* Which interface JDK tools use to connect to JVM locally?\
Answer: the JVM tool interface (JVM TI)
* What is difference between profiling and traceability?\
Answer: profiling focuses on metrics, summaries and statistics, while tracing focuses on workflow, paths and events  


## OutOfMemory (OOM) error troubleshooting
#### Get OOM error
#### Use jvisualvm to observe OOM
![img.png](img.png)

![img_1.png](img_1.png)

#### Get heap dump
##### Using -XX:+HeapDumpOnOutOfMemoryError option
![img_2.png](img_2.png)

##### [Optional] Using jcmd
##### [Optional] Using jmap
#### Get heap histogram
##### Using jcmd
##### Using jmap
![img_3.png](img_3.png)

Last jcmd histograms before OOM
![img_6.png](img_6.png)

jmap histograms before OOM
![img_8.png](img_8.png)

#### Analyze heap dump
##### Using Java Visual VM
###### -XX:+HeapDumpOnOutOfMemoryError
![img_4.png](img_4.png)

###### jcmd
![img_14.png](img_14.png)

###### jmap
![img_15.png](img_15.png)

##### OQL
Execute OQL in jvisualvm:
![img_5.png](img_5.png)
![img_7.png](img_7.png)
![img_9.png](img_9.png)

Startup `jhat` (note: `jhat` was decommissioned in JDK 9)
![img_10.png](img_10.png)

Execute OQL in jhat
![img_11.png](img_11.png)
![img_12.png](img_12.png)
![img_13.png](img_13.png)


## Deadlock troubleshooting
#### Get deadlock
- Execute java application that simulates deadlock:

![img_18.png](img_18.png)

#### Get thread dump
1} jstack
![img_17.png](img_17.png)

2} kill -3

3} jvisualvm
![img_16.png](img_16.png)

4} Windows (Ctrl + Break)

5} jcmd
![img_19.png](img_19.png)

## Remote JVM profiling
Using [JMX Technology](https://docs.oracle.com/javase/8/docs/technotes/guides/management/agent.html)

For insecure remote connection use parameters:
![img_20.png](img_20.png)

Connect to JVM using jconsole:
![img_21.png](img_21.png)

![img_22.png](img_22.png)

## Inspect a Flight Recording
### Execute JVM with two special parameters:
```
    -XX:+UnlockCommercialFeatures
    -XX:+FlightRecorder
```
![img_24.png](img_24.png)

### Enable Flight Recording on JVM without these parameters:
![img_26.png](img_26.png)

![img_27.png](img_27.png)


### Open Java Mission Control and connect to default HotSpot of our JVM:

#### With -XX options: JMC before OOM
![img_23.png](img_23.png)

#### With -XX options: JMC after OOM 
![img_29.png](img_29.png)

#### With jcmd: JMC before OOM
![img_25.png](img_25.png)

#### With jcmd: JMC after OOM
![img_28.png](img_28.png)


## jinfo
Print system properties and command-line flags that were used to start the JVM.
![img_30.png](img_30.png)

![img_31.png](img_31.png)

