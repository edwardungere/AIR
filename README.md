# Automated Ingestion & Response (AIR) Lab 

## 1. Introduction
The Automated Ingestion Response lab demonstrates a full cloud security monitoring and automated incident response pipline using **AWS** and **Splunk**. 

Instead of relying on a single telemetry source to respond to threats, this lab demonstrates how logs across the control and data plane can be correlated to provide expanded visibility into internal adversary tactics and techniques to enable effective automated mitigation. 

## 2. Background
As organizations continue migrating operations to the cloud, these environments have become critical components of enterprise infrastructure. Monitoring these workloads and operations are essential for business continuity and maintaing an important security posture. Comprehensive logging and monitoring across both the control and data plane, paired with sevrless compute functions can provide active defense for these critical enviroments.

## 3. Scenario
This scenario models an internal machine launching MITRE-mapped attacks against an internal cloud workload operating within the same AWS account. The attacker will move laterally from its own instace to the private instance. 

Activity from the attacker will generate telemetry across AWS API logs, VPC network flow metadata, and host-based Linux logs. These sources are ingested into a Splunk instance, where they are normalized, correlated, and analyzed to detect malicious behavior and trigger automated response actions via Lambda Functions.

## 4. System Architecture

List of services used in this lab:

## 6. Threat Model
The threat model can be found [here](https://github.com/edwardungere/AIR/blob/main/architecture/threat-model.md)

<img src="aws-splunk.png" width="300" height="300" />
