# Steps to Setup and run Seaker App

## Install WMI exporter in windows.
WMI exporter is used for collecting metrics from Windows.
WMI exporter Integrates with Prometheus to query data.  

To Install WMI exporter visit official site and download .msi file which can be easily Installed by following the prompts.
## Clone github repository
Clone the github repository. Open terminal and move to the cloned folder.
## Build docker image for Prometheus
To build Prometheus image, in terminal type
``` cd prometheus ```

``` docker build -t seeker-prometheus ```
## Build docker image for Grafana
For setting up Alerts Manager first we need to setup a host email. 

- Open grafana.ini file present in the grafana folder of the repository.
- Edit smtp section(first section) remove ';'. Add host mail and details.
- To build Grafana image, in terminal type
``` docker build -t seeker-grafana ```
## Run Prometheus and Grafana
In terminal move to repository folder and type
``` docker compose up -d ```.
To ensure prometheus and Grafana are running properly visit localhost:9090 for prometheus and localhost:3000 for grafana.
To login to grafana type username as admin and password as admin in the login page.
## Integrate Grafana with Prometheus
- To Integrate Prometheus with Grafana open Connections and cllick on Data sources. 
- In the Data sources tab click on the button Add new datasource. Fill the form.
## Setup dashboard
Open Dashboards section. 
- click on import in the dropdown New.
- Upload Dashbord.json file present in the grafana folder of the repository.
## Setup Alerts Manager
First select Contact points tab present under the Alerting section of Grafana website. 
- Add details of mails to send to. 
- To Add Alerts select Alert rules tab present under the Alerting section.
- Click on New Alert Button.
- Add queries and alert conditions.
# Block Diagram 
<figure>
<img src="/seeker-app.png">
</figure>
