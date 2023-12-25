# ActiveMQ Helm Chart

## Overview
This Helm chart deploys an ActiveMQ container. ActiveMQ is a powerful open-source messaging server, and this deployment is tailored for Kubernetes environments.

## Services
The JMX ActiveMQ broker listens on port 61616 and the Web Console on port 8161 served by 2 separate services.

## ConfigMap
ConfigMap used for configuring the ActiveMQ Broker within a Kubernetes deployment. The ConfigMap contains essential configuration settings for ActiveMQ, encapsulated in an XML format.

#### The ConfigMap contains the activemq.xml configuration file. Key configuration elements include:
-   Spring Framework beans for property configuration and logging.
-   ActiveMQ broker definition, including JMX settings and data directory.
-   Policy entries for message handling and limits.
-   Plugins, such as the DiscardingDLQBrokerPlugin.
-   Management context for creating JMX connectors.
-   Persistence adapter settings (using KahaDB).
-   System usage settings for memory, store, and temporary space.
-   Transport connector configurations.
-   Shutdown hooks for the Spring context and Jetty server integration.


## Prerequisites
-   Kubernetes cluster
-   Helm 3
-   kubectl installed and configured

## Installation
helm repo add activemq https://ger-is-registry.caas.intel.com/chartrepo/pda
helm upgrade --install activemq -f values.yaml --namespace <namespace-name>

## Parameters
