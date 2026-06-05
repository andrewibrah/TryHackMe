SOC L1 Alert Triage

**Knowing how to handle ALERTS properly ultimately decides if breaches are "detected and prevented" or "missed and devastating"**

SOC = Security Operations Center 

# From EVENTS to ALERTS 
- First, an event must occur
- Then, your OS, a firewall, or a cloud provider must log the event
- Next, System logs are shipped to a security solution like SIEM or EDR. 
- Alerts save SOC analysts from manual log review by highlighting only suspicious, anomalous events.

Alert Management Platforms

|Solution------------------			Examples------------------	                                 Description------------------|
|SIEM----------------------			Splunk ES, Elastic----------	 SIEM has solid alert management capabilities and is a perfect choice for most SOC teams|
| EDR or NDR---------------- 			MS Defender, CrowdStrike	 While EDR and NDR provide their own alert dashboards, it is preferred to use SIEM or SOAR|
| SOAR----------------------			Splunk SOAR, Cortex SOAR-----	 Bigger SOC teams can use SOAR to aggregate and centralize alerts from multiple solutions|
| ITSM----------------------			Jira, TheHive---	Some teams may have a custom ticket management (ITSM) setup using a dedicated solution|

# **SIEM = Security Information and Event Management system**
# **EDR = Endpoint detection and response**
# **NDR = Network detection and response**
# **SOAR = Security orchestration, automation,a couple of minutes after the and response**
# **ITSM = IT service management** 

## SOC L1 analysts:  Review the alerts, distinguish bad from good, and notify L2 analysts in case of a real threat
## SOC L2 analysts:  Receive the alerts escalated by L1 analysts and perform deeper analysis and remediation
## SOC engineers:  Ensure the alerts contain enough information required for efficient alert triage
## SOC manager:  Track speed and quality of alert triage to ensure that real attacks won't be missed


# Alert Properties

1. Alert Time - Usually couple mins after event. (format: MM-DD 24h hh:mm)
2. Alert Name - summary of what happened, based on the detection rule's name (e.g.,  Unusual Login Locations, Email marked as phishing, Windows RDP bruteforce)
3. Alert Severity - urgency of the alert, initially set by detection engineers, but can be altered by analysts if needed (Low/Informational, Medium/Moderate, High/Severe, Critical/Urgent)
4. Alert Status - Informs if somebody is working on the alert or if the triage is done.(New / Unassigned, In Progress / Pending, Closed / Resolved)
5. Alert Verdict (Classification) - if the alert is a real threat or noise (True Positive, False Positive)
6. Alert Assignee - who is working on the alert, takes responsibility for their alerts
7. Alert Description - Explains what the alert is about, usually in three sections on the right 
    >Logic of the alert-generating rule
    >Why this activity cancan this activity indicate an attack
    >how to triage this alert
8. Alert Fields- Provides SOC analysts' comments and values on which the alert was triggered
    >Affected Hostname
    >Entered Commandline

# Alert Prioritization - process of deciding which task to handle
>crucial to ensure timely detection of a threat, especially with many alerts in the queue.

## SOC teams decide on their own prioritization rules and usually automate them by setting the appropriate alert sorting logic in SIEM or EDR.
Common approaches:
1. Filter the alerts: Don't take alerts that others have reviewed. Only take new, unseen, or unrevolved alerts.  
2. Sort by severity: Start with Critical, then High, Medium, and finally Low.
3. Sort by Time: oldest to newest. 

# Alert Triage
- Alert review by SOC analysts can also be called alert triage, alert handling, alert processing, alert investigation, or alert analysis.

## Initial Actions
Assign the alert to yourself, move alert to in progress then familiarize yourself with the alert details.

## Investigation 
Workbooks - instructions on how to investigate the specific category of alerts. 
If workbooks arent avaible:
1. Understand who is under threat
2. Note the action described in the alert
3. Review surrounding events
4. Use threat intelligence platforms or other available resources to verify your thoughts

## Final Actions
Decisions here determine whether you found or missed the potential cyberattack.
1. Decide if the alert you investigated is malicious (True Positive) or not (False Positive).
2. Prepare your detailed comment explaining your analysis steps and verdict reasoning.
3. Return to the dashboard and move it to the Closed status.
