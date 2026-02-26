<!--
Copyright (C) 2019 NETSCOUT SYSTEMS, INC. All Rights Reserved.

Technology Add-on for NETSCOUT(R) Arbor Edge Defense (AED) devices and NETSCOUT(R) Arbor APS (APS) devices.  In this document, AED refers to both types of devices.
-->

## CHANGELOG
   0.2.0 - Added CIM Compliance with additional Fieldextractions, Aliases, Evals
   0.1.1 - Extended with additional field extractions
   0.1.0 - Initial Release

## INSTALLATION

   Install this Splunk technology add-on on your indexers, heavy forwarders, and search heads. The add-on provides configurations for search-time field extractions.

### Prerequisites

   + Splunk(R) Enterprise v7.x or later
   + Arbor Edge Defense or Arbor APS v6.2 or later

### Installation Summary

   1. Configure Splunk Enterprise to accept network monitoring input as described in the [Splunk documentation](https://help.splunk.com/en/data-management/get-data-in/get-data-into-splunk-enterprise/10.2/get-data-from-network-sources/get-data-from-tcp-and-udp-ports#configure-a-udp-network-input-0)

      Splunk recommends using a [Splunk forwarder](https://help.splunk.com/en/splunk-enterprise/get-started/get-data-in/10.2/introduction/use-forwarders-to-get-data-into-splunk-enterprise) to avoid possible disruptions (Splunk restarts) with the syslog stream. The NETSCOUT AED/APS add-on relies on sourcetype being set to `netscout:aed`. 

      You can set up the network input in the Splunk UI or by using an [inputs.conf](https://help.splunk.com/en/data-management/splunk-enterprise-admin-manual/10.2/configuration-file-reference/10.2.0-configuration-file-reference/inputs.conf) file. For example:

      ```
      [udp://514]
      connection_host = ip
      index = main
      sourcetype = netscout:aed
      no_appending_timestamp = true
      ```

   2. Configure AED to send syslog notifications to Splunk. In AED/APS, select **Administration > Notifications > Notifications Destinations tab**, and then add a syslog destination with the following settings:

      Host: The Splunk hostname or Splunk forwarder  
      Protocol: UDP  
      Syslog Format: CEF or LEEF. The Legacy format is not supported.  
      Alert Type: Blocked Host  

## License

   For license details, see [LICENSE](LICENSE.md).

## Support

   To contact NETSCOUT for help, to request features, or submit bug reports, email threat-community@netscout.com.
   This application is not subject to MasterCare or any other NETSCOUT support offering. We will respond to your email as resources are available.
