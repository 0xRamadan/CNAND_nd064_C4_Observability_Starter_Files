## Verify the monitoring installation

_Done:_ run `kubectl` command to show the running pods and services for all components. Take a screenshot of the output and include it here to verify the installation.
### All Pods
![verifyMonitoringInstallationPODs](./answer-img/verifyMonitoringInstallationPODs.png)

### All SVC
![verifyMonitoringInstallationSVC](./answer-img/verifyMonitoringInstallationSVC.png)

## Setup the Jaeger and Prometheus source

_Done:_ Expose Grafana to the internet and then setup Prometheus as a data source. Provide a screenshot of the home page after logging into Grafana.

### Welcome Grafana

![welcomeGrafana](./answer-img/welcomeGrafana.png)

## Create a Basic Dashboard

_Done:_ Create a dashboard in Grafana that shows Prometheus as a source. Take a screenshot and include it here.

![basicDashboard](./answer-img/basicDashboard.png)

## Describe SLO/SLI

_Done_:_ SLI is an indicator of how much we were able to achieve the SLO defined. For monthly uptime SLO, we can have SLI in terms of the duration for which the service remain unavailable, which we could then reduce as much as possible. For request response time SLO, we could average out the request response time, which would then give us the current SLI.

1. we should consider the response to the customer.
2. we should monitor the Traffic flow of the frontend and more specific to the Backend and Trial API serving the frontend.
3. Percentage of Success hits to Frontend, Backend & Trial should always be above 99.95% for the monthly duration.
4. we should consider utilization of th app such as CPU, Memory and Disk
5. we should monitor the Start Timings of the Pod along with the number of replicas.

## Creating SLI metrics.

_Done:_

1. Request time respond. 
    * Response time
2. How many failed requests .
    * Error rate
3. Hom many requests over a period of time.
    * Availability 
4. The utilization of the CPU and Memory by the service.
5. Uptime of the Fronted & Backend service.

## Create a Dashboard to measure our SLIs

_Done:_ 

![SLI-Dashboard](./answer-img/SLI-Dashboard.png)

## Tracing our Flask App

![backend-service](./answer-img/backendService.png)

## Report Error

_Done:_ Using the template below, write a trouble ticket for the developers, to explain the errors that you are seeing (400, 500, latency) and to let them know the file that is causing the issue also include a screenshot of the tracer span to demonstrate how we can user a tracer to locate errors easily.

![trialService](./answer-img/trialService.png)

![trialError](./answer-img/trialError.png)

TROUBLE TICKET

Name: Homepage can't be reach

Date: 9/24/2022

Subject: FrontEnd-service not reachable

Affected Area: FrontEnd-service & Ingress

Severity: ERROR

Description: It seems that FrontEnd-service has change it's port scheme and therefore Ingress is not able to reach service.

## Creating SLIs and SLOs

_Done:_ We want to create an SLO guaranteeing that our application has a 99.95% uptime per month. Name four SLIs that you would use to measure the success of this SLO.
* Uptime
* Latency
* Error rate
* Resource Usage

## Building KPIs for our plan

_Done:_ Now that we have our SLIs and SLOs, create a list of 2-3 KPIs to accurately measure these metrics as well as a description of why those KPIs were chosen. We will make a dashboard for this, but first write them down here.

1. Measure the availability of the systems/services (Uptime). The backend and frontend services can be measured.
    * BackEnd-service Up/Down
    * FrontEnd-service Up/Down
    * Kubernetes Uptime
2. Track the average of 2xx or 3xx responses of the app as a ratio of the overall number of requests.
    * Average time responses
    * Number of successful request second
3. Error rate
    * Rate of failed request per sec
    * Error codes for all services 500s & 400s
4. Network Bandwidth of Receive / Transmit: This metric indicates the saturation level of the network 
5. Memory Utilization: This metric will indicate how intensely the memory resources are consumed
6. CPU Utilization: This metric will indicate the saturation level in our compute power

## Final Dashboard

![Final Dashboard](./answer-img/finalDashboard.png)
