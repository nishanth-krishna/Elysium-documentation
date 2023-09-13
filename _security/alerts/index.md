---
layout: default
title: Alerts
nav_order: 50
has_children: false
redirect_from: /security/alerts/
has_toc: false
---

# Security Alerts

This section describes the Elysium Security Alerts and its components. Any event or a group of events that is an anomaly (or a red flag) can be called an alert (or trigger or alarm). What makes this an anomaly is generally decided and defined by the client itself. For example, let us say if we have a threshold for some measure, say execution time. If the value of that measure crosses a certain threshold value, then we can call it an anomaly, or in other words, an alert. Ideally, alerts are supposed to be as minimal as possible.

The software from which we receive logs is called source software, or simply sources. Examples of sources include - Windows Security, Dell Boomi, Microsoft Azure, Watchguard Firewall etc. The sources differ from client to client.



## Alerts Interface

Click on “Alerts” under Security Menu to access the Security Alerts.

![image1.png]({{site.baseurl}}/images/security-alerts/image1.png)


![image2.png]({{site.baseurl}}/images/security-alerts/image2.png)


We have three alert tabs 

- Alert Rules
- Alerts
- Alerts Dashboard


## Alert Rules

Shows all the alert rules have been defined for various sources, along with their status, properties etc. It also allows users to create new alert rules and configure their properties.

![image3.png]({{site.baseurl}}/images/security-alerts/image3.png)

- The alert rules we define appear here with -
- ID: Auto-increment sequence number
- Category: Type of the alert. Rule-based and Behaviour Alerts are the two alert types. Refer to the below image for more detail.
- Rule - Shows the source name and a semi SQL
- -like condition describing the configured rule
- Properties - Shows other properties of the alert rule such as severity, rollup window, message, additional comments & email recipients. The severity of the alert can be low/medium/high. Rollup window tells us the time window for clubbing the alerts as alert count in the email notifications. Message and additional comments contain any additional description of the alert. Email recipients shows the email IDs to which the alert notification has to be sent.
- Created At - Shows the timestamp when the alert rule is created
- Created By - Shows the user who created the alert rule
- Immediate Notifications - Shows whether an immediate notification has to
-  be sent or not, when the alert is triggered. Whenever an alert is triggered, it has to be notified or shown to the client. This is currently being done in a couple of ways - email notifications, Looker dashboards and the 'Alerts Table' page. The user can either enable or disable it. Alert notifications are of three types - immediate, scheduled and manual. In immediate notification, mail is sent immediately after an alert is triggered. In scheduled notification (report scheduler), a consolidated list of all alerts that have occurred within a user-defined time period is mailed (say every hour or day or week or month). This time period can be defined once by the user, and a mail notification will be sent periodically at that fixed time. In manual notification, a consolidated report of all the alerts that have occurred for a particular day is mailed, upon the user’s request.
- Status - Shows whether the alert rule is in active or inactive state
- Action - Has options to Edit, Delete, Activate & Deactivate the alert rule
- At the top are the ‘Report Scheduler’ and ‘Add New Rule’ options. The ‘Report Scheduler’ gives a report of all the alerts that have occurred within the specified frequency mentioned by the user. All high-priority alerts will be sent to the user everyday by default. The ‘Add New Rule’ option can be used to create a new alert rule. Let us see that below.


### 1)Add New Rule

The ‘Add New Rule’ link is at the top right corner of the ‘Manage Alert Rules’ page, where you can define a new alert rule step-by-step. There are currently two categories of alerts. Select either of the two options.


- Behavior-Based: Alerts based on the behavior of a user or system. 
- Rule-Based: Alerts based on a pre-defined rule. We can define multiple combinations of rules using AND, OR operators corresponding to the sources (Boomi, Azure)

![image4.png]({{site.baseurl}}/images/security-alerts/image4.png)

After clicking on create new alert rule you will navigate to create alert page where you can different steps and forms like this:

![image5.png]({{site.baseurl}}/images/security-alerts/image5.png)

We have three steps for creating alert rule

- Choose Method: Select the category to create rule or behaviour type of alert rule by clicking on the toggle buttons like this

![image6.png]({{site.baseurl}}/images/security-alerts/image6.png)


## Behaviour Alerts

Alerts based on the behavior of a user or system are call Behaviour Alerts. As can be seen in the picture below, we start defining the alert rule by choosing from different categories of alert rules: Real-Time and Schedule.

The first option gives the flexibility of tying each triggered to an event in the source table (“Real-time”) or triggering it independent of a particular event(“Schedule”)

Real-Time vs Schedule Triggers: The main difference is that Real-Time Triggers are generated after each event and compared with previous events within the specified rolling time window whereas Scheduled Triggers are generated as per the run frequency specified by the users for all the events that occur inside the specified rolling time window.



### A. Real-time Trigger Alerts

These are alert that searches for events continuously near Real-Time. They trigger alert actions when results meet user-defined conditions within a rolling time window. For example, a SOC Admin can set up an alert to get notified as soon a fifth failed login attempt is performed by a user within the last 24 hours.

Real-time alerts have two threshold types:- Absolute and Relative.

Absolute vs Relative Thresholds: Absolute Thresholds are specific numeric values that are entered by the user when defining the alerts which then compared with the Metric. Relative Thresholds are thresholds where an aggregate or a grouping function is applied on the Threshold and is then compared to the specific value for that event. 

An example of an alert condition with an Absolute Threshold is Avg(duration)>1000. Here 1000 is the threshold as defined by the user. An example of an alert condition with a Relative Threshold is Duration > (avg(duration) * 2). Here (avg(duration) * 2) is the threshold as defined by the user.



### A1. Absolute Threshold

These are alerts that have a threshold as an absolute value as defined by the user i.e the alert triggering criteria is a number value that is specified when creating the alerts. It can be set up in such a way that the alerts will be triggered when the encountered value is >=, <=, =, etc. than the threshold value defined.

Below is the text which will be shown in Condition preview when you create a Real-time alert with an Absolute threshold. 

WHEN sum(duration) FOR EACH Domain > 1000 IN LAST 10 Hours FOR EACH RESULT 

The below image shows us the different parameters which the user would need to input to set up a real-time - Absolute alert condition. All the fields are mandatory to set up an alert condition.

1.Source

Shows all the source systems from which we receive logs for a particular client. Examples of sources include - Windows Security, Dell Boomi, Microsoft Azure, Watchguard Firewall, etc. The sources differ from client to client.

2.Feature

Feature lists the different fields for each source over which metric can be formed. The fields in Feature can either be of type string or number and each type is associated with its own set of metrics ( specified below ).

3.Metrics

Metrics are the different mathematical aggregate or grouping functions that can be applied over a feature. The different Metrics currently available in Version 1.75 are sum, avg, min, max, count, P90, P10, Rate, and median. All the Metrics are applicable for Features with type number whereas only count and Rate are applicable for strings since not all mathematical groupings are suited for strings. 

The usage for all metrics except P90, P10, and Rate are self-explanatory and straightforward. The explanation for P90, P10, and Rate can be found in the appendix section.

4.Context

Context is the attribute/column from the source with which you group the Metrics. The results will be calculated/grouped by each value in the context field.

“GLOBAL” context is also given as an option that allows you to calculate the metric on all the new data rather than to split it up for each context. For example, you can choose “src_user_name” as context if you want the max(event_id) for each src_user_name, however, to choose the max(event_id) for the entire dataset, you can choose GLOBAL as the context. 

5.Operator

This is the comparison operator which has to be specified between the Metric and the Threshold.

 	 **Eg** : >, >=, =, etc.

6.Threshold

The threshold is the number value defined by the user which will be compared with the Metrics value.

7.Timeframe

The timeframe is the rolling time window entered by the user associated with the particular alert.

8.Timeunit

The time unit is the measure of timeframe entered. The current options are minutes and hours.

Now that we have gone through all the components that make an Absolute Threshold alert, the below representation highlights all the components that users would have entered on the alert condition that was built.



## Rule Based Alerts

These are relatively simpler alert rules, where you can create simple to very complex nested rule conditions that are checked across each event in the source table. You can see the sample UI below whereby choosing “Add Group” option, you add a nested conditional branch whereas the “ADD Rule” option just adds another condition to the same branch.



## Notification Settings: 

The notification settings are very similar between the different kinds of alerts, so an in-depth explanation is not required for this section. However in Rule based alerts, the  **context** is provided in the notification settings since context does not affect the results in Rule based alert and can be used to just roll up the data.




- Define Rule: Enter the source, after selecting source there will one input where you can enter your condition type and condition for alert rule
- Define Alert Properties: Fill the required fields in this step to create a rule. The number of fieldsdiffer on selection category in the first step (rule/behaviour). 
 	Required Fields: Title, Severity

Optional Fields: Description, Email notifications, Email recepients

For Rule based - Email notifications – true, submit these fields

![image7.png]({{site.baseurl}}/images/security-alerts/image7.png)

For Behaviour based – Run Frequency

![image8.png]({{site.baseurl}}/images/security-alerts/image8.png)

If real time is scheduled submit the cron-expression too as shown below

![image9.png]({{site.baseurl}}/images/security-alerts/image9.png)

After submitting all the required fields, you can click on save to create the new alert rule. If the alert data, you submitted is valid it will create new alert rule and navigates you back to the alerts page where you can see your alert created in the table. To do any changes click on actions for that particular row and edit them update them

2)Search 

Type in this search box to search specific alert rules using keywords like alert title, id’s, status etc...

![image10.png]({{site.baseurl}}/images/security-alerts/image10.png)

These are the results for the keyword ‘title’ that from the search box

![image11.png]({{site.baseurl}}/images/security-alerts/image11.png)

3)Actions on table



- Click on arrow icon to view complete alert rule data 

![image12.png]({{site.baseurl}}/images/security-alerts/image12.png)

- Click on menu icon to view actions that can be performed on alert rules

![image13.png]({{site.baseurl}}/images/security-alerts/image13.png)

![image14.png]({{site.baseurl}}/images/security-alerts/image14.png)
    

Onclick on all actions icon as shown in first picture it will display three different actions as shown in second picture


- Delete Action – On Click on delete action you will get a confirm pop up like this.


![image15.png]({{site.baseurl}}/images/security-alerts/image15.png)


- Select Cancel option for not deleting the rule
- Select Confirm option for deleting the rule, after the rule gets deleted table gets refreshed and shows the updated data

![image16.png]({{site.baseurl}}/images/security-alerts/image16.png)


After clicking on confirm button table will loads and shows updated alert rules

2.  **Edit Action –** To Edit any specific rule click on the edit option which it will navigates you to the edit page 

![image17.png]({{site.baseurl}}/images/security-alerts/image17.png)

After clicking edit you will navigate to this page where you can edit alert rules data and update the rule successfully

 **3. Activate/ Deactivate Action –**  To Activate or Deactivate the rule select this option as shown in the below image

![image18.png]({{site.baseurl}}/images/security-alerts/image18.png)

After clicking on activate/ deactivate button table loads and shows updated status of alert rules





## Alerts

On selecting alerts tab, you can see the table like the below image:

Table Interface

![image19.png]({{site.baseurl}}/images/security-alerts/image19.png)



This page shows all the alerts that have been triggered so far, based on the alert rules defined by the client. Details about the alerts like - Source (source name), Parent ID (parent alert ID), Alert Name (alert name and condition) & Count (clone count, or count of similar alerts) are shown.

The alerts can also be filtered based on date, or can be searched with the parent ID, as shown in the below image.


![image20.png]({{site.baseurl}}/images/security-alerts/image20.png)


- Search Box: Search here for alerts with keywords like title
- Date Picker: You can select the specified dates to check the generated alerts in that time period.

## Alerts Dashboard

On selecting alerts dashboards tab, you can see the alerts dashboard iframe like the below image:

![image21.png]({{site.baseurl}}/images/security-alerts/image21.png)

Text

