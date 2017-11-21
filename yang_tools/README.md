# YANG (Using YANG tools):

## Introduction:
- YANG is ...
- Some links:
  - https://github.com/mbj4668/pyang/wiki/Tutorial
  - https://www.ietf.org/edu/tutorials/90-YANG-Tutorial.pdf

## Content of this repo:
- [NETCONF via SSH]()
- [Validate yang modules]()
- [Convert yang into yin]()
- [Generate a tree representation of YANG models]()
- [Generates Python classes from a YANG module]()


## NETCONF via SSH:
- You can connect to a device with the ```-s netconf``` option .This allows to:
  - Discover the netconf capabilities exchanged as part of the Hello process.
  - Pass NETCONF RPCs directly in XML.
- If you need to specify the port number add it this way: ```-p 830```.
```
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools$ ssh vyatta@vyatta1 -s netconf
Welcome to Brocade Vyatta Network OS

vyatta@vyatta1's password: 
<?xml version="1.0" encoding="UTF-8"?>
<hello xmlns="urn:ietf:params:xml:ns:netconf:base:1.0">
  <capabilities>
    <capability>urn:ietf:params:netconf:base:1.0</capability>
    <capability>urn:ietf:params:netconf:base:1.1</capability>
    <capability>urn:ietf:params:netconf:capability:with-defaults:1.0?basic-mode=explicit&amp;also-supported=report-all,explicit</capability>
    <capability>urn:ietf:params:netconf:capability:candidate:1.0</capability>
    <capability>urn:ietf:params:netconf:capability:startup:1.0</capability>
    <capability>urn:ietf:params:netconf:capability:rollback-on-error:1.0</capability>
    <capability>urn:ietf:params:netconf:capability:validate:1.1</capability>
    <capability>urn:ietf:params:netconf:capability:validate:1.0</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-pim6:1?module=vyatta-protocols-pim6-v1&amp;revision=2016-08-16</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-dhcpv6-server-routing-instance:1?module=vyatta-service-dhcpv6-server-routing-instance-v1&amp;revision=2016-06-12</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-policy:1?module=vyatta-interfaces-policy-v1&amp;revision=2015-10-05</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-connsync:1?module=vyatta-service-connsync-v1&amp;revision=2015-10-22</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-l2tpeth:1?module=vyatta-interfaces-l2tpeth-v1&amp;revision=2016-05-04</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-sflow-routing-instance:1?module=vyatta-service-sflow-routing-instance-v1&amp;revision=2016-01-13</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-dataplane:1?module=vyatta-interfaces-dataplane-v1&amp;revision=2016-10-04</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-bgp-routing-instance:1?module=vyatta-protocols-bgp-routing-instance-v1&amp;revision=2016-06-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-nhrp:1?module=vyatta-nhrp-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-alg:1?module=vyatta-system-alg-v1&amp;revision=2016-08-05</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-dhcpv6-client:1?module=vyatta-dhcpv6-client-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-pim6-routing-instance:1?module=vyatta-protocols-pim6-routing-instance-v1&amp;revision=2016-04-26</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-dhcpv6-relay-routing-instance:1?module=vyatta-service-dhcpv6-relay-routing-instance-v1&amp;revision=2016-07-12</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-misc:1?module=vyatta-system-misc-v1&amp;revision=2016-03-02</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-security-ssh-known-hosts-routing-instance:1?module=vyatta-security-ssh-known-hosts-routing-instance-v1&amp;revision=2016-04-13</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-dhcpv6-server:1?module=vyatta-service-dhcpv6-server-v1&amp;revision=2016-04-20</capability>
    <capability>urn:ietf:params:xml:ns:yang:ietf-netconf-with-defaults?module=ietf-netconf-with-defaults&amp;revision=2011-06-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-syslog-routing-instance:1?module=vyatta-system-syslog-routing-instance-v1&amp;revision=2016-04-22</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-telnet:1?module=vyatta-service-telnet-v1&amp;revision=2016-03-21</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-interface-validation:1?module=vyatta-protocols-interface-validation-v1&amp;revision=2016-07-21</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-dpi:1?module=vyatta-dpi-v1&amp;revision=2016-07-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-dhcp-relay-routing-instance:1?module=vyatta-service-dhcp-relay-routing-instance-v1&amp;revision=2016-06-12</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-dns-routing-instance:1?module=vyatta-service-dns-routing-instance-v1&amp;revision=2016-04-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-ssl-vpn-bundler:1?module=vyatta-ssl-vpn-bundler-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-alg-routing-instance:1?module=vyatta-system-alg-routing-instance-v1&amp;revision=2016-04-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-twamp:1?module=vyatta-service-twamp-v1&amp;revision=2016-04-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-acm-opd:1?module=vyatta-system-acm-opd-v1&amp;revision=2016-03-25</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-flow-monitoring:1?module=vyatta-service-flow-monitoring-v1&amp;revision=2016-09-28</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-ospfv3-routing-instance:1?module=vyatta-protocols-ospfv3-routing-instance-v1&amp;revision=2016-10-24</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-tacplus:1?module=vyatta-system-tacplus-v1&amp;revision=2016-02-19</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-policy-qos:1?module=vyatta-policy-qos-v1&amp;revision=2016-05-16</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-mgmt-routing-instance:1?module=vyatta-system-mgmt-routing-instance-v1&amp;revision=2016-04-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-security:1?module=vyatta-security-v1&amp;revision=2015-08-05</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-network:1?module=vyatta-system-network-v1&amp;revision=2016-05-31</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-op-routing-instance:1?module=vyatta-op-routing-instance-v1&amp;revision=2016-04-12</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-opd:1?module=vyatta-opd-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-resources-service-users:1?module=vyatta-resources-service-users-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-dataplane:1?module=vyatta-system-dataplane-v1&amp;revision=2015-10-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-bgp:1?module=vyatta-protocols-bgp-v1&amp;revision=2016-10-26</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-login:1?module=vyatta-system-login-v1&amp;revision=2016-06-28</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-ipv6-rtradv-groups:1?module=vyatta-ipv6-rtradv-groups-v1&amp;revision=2016-10-17</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-static:1?module=vyatta-protocols-static-v1&amp;revision=2016-07-13</capability>
    <capability>urn:ietf:params:xml:ns:yang:ietf-yang-types?module=ietf-yang-types&amp;revision=2013-07-15</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-static-routing-instance-inter-vrf:1?module=vyatta-protocols-static-routing-instance-inter-vrf-v1&amp;revision=2016-07-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-resources:1?module=vyatta-resources-v1&amp;revision=2015-08-05</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-flow-monitoring-dataplane-vif:1?module=vyatta-service-flow-monitoring-dataplane-vif-v1&amp;revision=2016-04-26</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-routing-v1:1?module=vyatta-routing-v1&amp;revision=2016-06-28</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-fips:1?module=vyatta-system-fips-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-time:1?module=vyatta-system-time-v1&amp;revision=2016-10-27</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-acm:1?module=vyatta-system-acm-v1&amp;revision=2016-03-25</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-sync:1?module=vyatta-system-sync-v1&amp;revision=2016-04-19</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-pim-interface:1?module=vyatta-protocols-pim-interface-v1&amp;revision=2017-02-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-dhcp-relay:1?module=vyatta-service-dhcp-relay-v1&amp;revision=2016-06-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-rib-routing-instance:1?module=vyatta-protocols-rib-routing-instance-v1&amp;revision=2016-05-02</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-bridge-spanning-tree:1?module=vyatta-interfaces-bridge-spanning-tree-v1&amp;revision=2015-11-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-security-vpn-l2tp:1?module=vyatta-security-vpn-l2tp-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-ipv6-rtradv:1?module=vyatta-ipv6-rtradv-v1&amp;revision=2016-09-08</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-fw-types:1?module=vyatta-fw-types-v1&amp;revision=2016-08-24</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-policy-pbr-routing-instance:1?module=vyatta-policy-pbr-routing-instance-v1&amp;revision=2016-04-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-bridge-rstp:1?module=vyatta-interfaces-bridge-rstp-v1&amp;revision=2015-10-13</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-dhcpv6-relay:1?module=vyatta-service-dhcpv6-relay-v1&amp;revision=2016-07-19</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-security-vpn-ipsec:1?module=vyatta-security-vpn-ipsec-v1&amp;revision=2017-01-27</capability>
    <capability>urn:ietf:params:xml:ns:yang:ietf-inet-types?module=ietf-inet-types&amp;revision=2013-07-15</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-ripng-routing-instance:1?module=vyatta-protocols-ripng-routing-instance-v1&amp;revision=2016-05-04</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-pim:1?module=vyatta-protocols-pim-v1&amp;revision=2016-08-02</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-syslog:1?module=vyatta-system-syslog-v1&amp;revision=2016-11-16</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-sflow-bonding:1?module=vyatta-service-sflow-bonding-v1&amp;revision=2016-04-15</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-mpls-ldp:1?module=vyatta-protocols-mpls-ldp-v1&amp;revision=2015-03-05</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-lldp:1?module=vyatta-service-lldp-v1&amp;revision=2015-08-06</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-ospf-routing-instance:1?module=vyatta-protocols-ospf-routing-instance-v1&amp;revision=2016-10-10</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-rib:1?module=vyatta-protocols-rib-v1&amp;revision=2016-06-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-mld:1?module=vyatta-protocols-mld-v1&amp;revision=2016-07-27</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-snmp-routing-instance:1?module=vyatta-service-snmp-routing-instance-v1&amp;revision=2016-03-07</capability>
    <capability>urn:vyatta.com:mgmt:yangd:1?module=yangd-v1&amp;revision=2016-11-09</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-loopback:1?module=vyatta-interfaces-loopback-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-ecmp:1?module=vyatta-protocols-ecmp-v1&amp;revision=2016-06-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-netconf:1?module=vyatta-service-netconf-v1&amp;revision=2015-08-10</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-snmp:1?module=vyatta-service-snmp-v1&amp;revision=2015-08-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-dscp:1?module=vyatta-dscp-v1&amp;revision=2015-08-05</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-bfd-routing-instance:1?module=vyatta-protocols-bfd-routing-instance-v1&amp;revision=2016-05-10</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-openvpn:1?module=vyatta-interfaces-openvpn-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-bridge-static-fdb:1?module=vyatta-bridge-static-fdb-v1&amp;revision=2015-07-29</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-vrrp:1?module=vyatta-vrrp-v1&amp;revision=2016-10-31</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-bonding-qos:1?module=vyatta-interfaces-bonding-qos-v1&amp;revision=2016-04-27</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-mpls-rsvp:1?module=vyatta-protocols-mpls-rsvp-v1&amp;revision=2015-06-05</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-multicast-routing-instance:1?module=vyatta-multicast-routing-instance-v1&amp;revision=2016-04-21</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-dhcp-server:1?module=vyatta-service-dhcp-server-v1&amp;revision=2016-04-20</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-telnet-routing-instance:1?module=vyatta-service-telnet-routing-instance-v1&amp;revision=2016-04-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-multicast:1?module=vyatta-multicast-v1&amp;revision=2016-06-20</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-services:1?module=vyatta-services-v1&amp;revision=2015-08-05</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-igmp:1?module=vyatta-protocols-igmp-v1&amp;revision=2016-11-17</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-msdp-routing-instance:1?module=vyatta-protocols-msdp-routing-instance-v1&amp;revision=2016-04-25</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-ssh-routing-instance:1?module=vyatta-service-ssh-routing-instance-v1&amp;revision=2016-04-13</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-policy:1?module=vyatta-policy-v1&amp;revision=2015-08-05</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-unnumbered:1?module=vyatta-interfaces-dataplane-unnumbered-v1&amp;revision=2016-07-13</capability>
    <capability>urn:vyatta.com:mgmt:configd:1?module=configd-v1&amp;revision=2016-01-25</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-bonding:1?module=vyatta-interfaces-bonding-v1&amp;revision=2016-07-19</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-ssh:1?module=vyatta-service-ssh-v1&amp;revision=2017-01-09</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-rip-routing-instance:1?module=vyatta-protocols-rip-routing-instance-v1&amp;revision=2016-05-12</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-tunnel:1?module=vyatta-interfaces-tunnel-v1&amp;revision=2017-01-13</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-igmp-routing-instance:1?module=vyatta-protocols-igmp-routing-instance-v1&amp;revision=2016-04-22</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-mgmt:1?module=vyatta-system-mgmt-v1&amp;revision=2016-03-17</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-time-routing-instance:1?module=vyatta-system-time-routing-instance-v1&amp;revision=2017-01-31</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-nsm-routing-instance:1?module=vyatta-protocols-nsm-routing-instance-v1&amp;revision=2016-05-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-login-sssd:1?module=vyatta-system-login-sssd-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-openvpn-access-server:1?module=vyatta-openvpn-access-server-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-login-radius-routing-instance:1?module=vyatta-system-login-radius-routing-instance-v1&amp;revision=2016-03-04</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-vif:2?module=vyatta-interfaces-vif-v2&amp;revision=2016-05-19</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-msdp:1?module=vyatta-protocols-msdp-v1&amp;revision=2016-07-27</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-bfd:1?module=vyatta-protocols-bfd-v1&amp;revision=2016-06-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system:1?module=vyatta-system-v1&amp;revision=2016-01-28</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-twamp-routing-instance:1?module=vyatta-service-twamp-routing-instance-v1&amp;revision=2016-04-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-policy-route:1?module=vyatta-policy-route-v1&amp;revision=2016-09-22</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces:1?module=vyatta-interfaces-v1&amp;revision=2016-08-24</capability>
    <capability>urn:ietf:params:xml:ns:yang:ietf-netconf-monitoring?module=ietf-netconf-monitoring&amp;revision=2010-10-04</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-https:1?module=vyatta-service-https-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-nsm:1?module=vyatta-protocols-nsm-v1&amp;revision=2016-05-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-ripng:1?module=vyatta-protocols-ripng-v1&amp;revision=2016-07-19</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-mld-routing-instance:1?module=vyatta-protocols-mld-routing-instance-v1&amp;revision=2016-04-22</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-dhcp-client:1?module=vyatta-dhcp-client-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-session-routing-instance:1?module=vyatta-system-session-routing-instance-v1&amp;revision=2016-06-17</capability>
    <capability>urn:ietf:params:xml:ns:netconf:base:1.0?module=ietf-netconf&amp;revision=2011-06-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-types:1?module=vyatta-types-v1&amp;revision=2016-11-16</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-session:1?module=vyatta-system-session-v1&amp;revision=2016-08-09</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-npf:1?module=vyatta-npf-v1&amp;revision=2016-11-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-resources-group:1?module=vyatta-resources-group-v1&amp;revision=2016-10-25</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-flow-monitoring-bonding:1?module=vyatta-service-flow-monitoring-bonding-v1&amp;revision=2015-09-09</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-static-routing-instance:1?module=vyatta-protocols-static-routing-instance-v1&amp;revision=2016-05-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-mpls:1?module=vyatta-protocols-mpls-v1&amp;revision=2015-07-28</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-dns:1?module=vyatta-service-dns-v1&amp;revision=2016-08-24</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-policy-pbr:1?module=vyatta-policy-pbr-v1&amp;revision=2016-10-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-rip:1?module=vyatta-protocols-rip-v1&amp;revision=2016-06-17</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-ospfv3:1?module=vyatta-protocols-ospfv3-v1&amp;revision=2016-10-24</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-tacplus-routing-instance:1?module=vyatta-system-tacplus-routing-instance-v1&amp;revision=2016-02-19</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols:1?module=vyatta-protocols-v1&amp;revision=2015-08-05</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-security-firewall:1?module=vyatta-security-firewall-v1&amp;revision=2016-09-12</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-dhcp-server-routing-instance:1?module=vyatta-service-dhcp-server-routing-instance-v1&amp;revision=2016-06-12</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-pim-routing-instance:1?module=vyatta-protocols-pim-routing-instance-v1&amp;revision=2016-04-18</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-pim-common:1?module=vyatta-protocols-pim-common-v1&amp;revision=2016-06-02</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-routing-instance-interfaces-v1:1?module=vyatta-routing-instance-interfaces-v1&amp;revision=2016-08-12</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-interface-validation-routing-instance:1?module=vyatta-protocols-interface-validation-routing-instance-v1&amp;revision=2016-05-25</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-vti:1?module=vyatta-interfaces-vti-v1&amp;revision=2016-10-27</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-ssh-known-hosts:1?module=vyatta-security-ssh-known-hosts-v1&amp;revision=2016-02-24</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-flow-monitoring-routing-instance:1?module=vyatta-service-flow-monitoring-routing-instance-v1&amp;revision=2016-01-22</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-ecmp-routing-instance:1?module=vyatta-protocols-ecmp-routing-instance-v1&amp;revision=2016-06-01</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-network-routing-instance:1?module=vyatta-system-network-routing-instance-v1&amp;revision=2016-05-31</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-portmonitor:1?module=vyatta-service-portmonitor-v1&amp;revision=2016-08-08</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-op:1?module=vyatta-op-v1&amp;revision=2015-08-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-sflow:1?module=vyatta-service-sflow-v1&amp;revision=2016-04-15</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-package:1?module=vyatta-system-package-v1&amp;revision=2016-03-15</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-system-acm-configd:1?module=vyatta-system-acm-configd-v1&amp;revision=2014-08-26</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-xconnect:1?module=vyatta-xconnect-v1&amp;revision=2016-06-17</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-bridge:1?module=vyatta-interfaces-bridge-v1&amp;revision=2016-03-28</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-policy-pbr-dpi:1?module=vyatta-policy-pbr-dpi-v1&amp;revision=2016-07-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-ospf:1?module=vyatta-protocols-ospf-v1&amp;revision=2016-12-06</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-protocols-interface-validation-mpls:1?module=vyatta-protocols-interface-validation-mpls-v1&amp;revision=2016-06-14</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-nat:1?module=vyatta-service-nat-v1&amp;revision=2016-11-04</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-service-sflow-dataplane-vif:1?module=vyatta-service-sflow-dataplane-vif-v1&amp;revision=2016-04-28</capability>
    <capability>urn:vyatta.com:mgmt:vyatta-interfaces-erspan:1?module=vyatta-interfaces-erspan-v1&amp;revision=2016-11-16</capability>
  </capabilities>
  <session-id>1</session-id>
</hello>
]]>]]>
```


## Validate yang modules:
```
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$ pyang vyatta-protocols-bgp-v1.yang 
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$ 
```

## Convert yang into yin:
```
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$ pyang vyatta-protocols-bgp-v1.yang -f yin -o vyatta-protocols-bgp-v1.yin
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$ ls | grep yin
vyatta-protocols-bgp-v1.yin
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$ cat vyatta-protocols-bgp-v1.yin
<?xml version="1.0" encoding="UTF-8"?>
<module name="vyatta-protocols-bgp-v1"
        xmlns="urn:ietf:params:xml:ns:yang:yin:1"
        xmlns:vyatta-protocols-bgp-v1="urn:vyatta.com:mgmt:vyatta-protocols-bgp:1"
        xmlns:types="urn:vyatta.com:mgmt:vyatta-types:1"
        xmlns:protocols="urn:vyatta.com:mgmt:vyatta-protocols:1"
        xmlns:service="urn:vyatta.com:mgmt:vyatta-services:1"
        xmlns:service-snmp="urn:vyatta.com:mgmt:vyatta-service-snmp:1"
        xmlns:configd="urn:vyatta.com:mgmt:configd:1"
        xmlns:policy="urn:vyatta.com:mgmt:vyatta-policy:1"
        xmlns:policy-route="urn:vyatta.com:mgmt:vyatta-policy-route:1">
  <namespace uri="urn:vyatta.com:mgmt:vyatta-protocols-bgp:1"/>
  <prefix value="vyatta-protocols-bgp-v1"/>
  <import module="vyatta-types-v1">
    <prefix value="types"/>
  </import>
  <import module="vyatta-protocols-v1">
    <prefix value="protocols"/>
  </import>
  <import module="vyatta-services-v1">
    <prefix value="service"/>
  </import>
  <import module="vyatta-service-snmp-v1">
    <prefix value="service-snmp"/>
  </import>
  <import module="configd-v1">
    <prefix value="configd"/>
  </import>
  ...
  ...
  ...

mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$ 
```

## Generate a tree representation of YANG models:

- This is helpful for quick visualization:
- Let's look a sample data-model and display it all:

```
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$ pyang -f tree vyatta-protocols-bgp-v1.yang 
module: vyatta-protocols-bgp-v1
  augment /protocols:protocols:
    +--rw bgp* [tagnode]
       +--rw tagnode           uint32
       +--rw parameters!
       |  +--rw extended-asn-capability?          empty
       |  +--rw no-rtm?                           empty
       |  +--rw cluster-id?                       types:ipv4-address
       |  +--rw always-compare-med?               empty
       |  +--rw default!
       |  |  +--rw local-pref?   uint32
       |  +--rw confederation!
       |  |  +--rw identifier?   uint32
       |  |  +--rw peers*        uint32
       |  +--rw graceful-restart!
       |  |  +--rw graceful-reset?   empty
       |  |  +--rw restart-time?     uint32
       |  |  +--rw stalepath-time?   uint32
       |  +--rw bestpath!
       |  |  +--rw med!
       |  |  |  +--rw confed!
       |  |  |  |  +--rw missing-as-worst?   empty
       |  |  |  +--rw missing-as-worst?   empty
       |  |  +--rw as-path!
       |  |  |  +--rw ignore?   empty
       |  |  |  +--rw confed?   empty
       |  |  +--rw compare-routerid?    empty
       |  |  +--rw igp-metric-ignore?   empty
       |  +--rw log-neighbor-changes?             empty
       |  +--rw no-fast-external-failover?        empty
       |  +--rw enforce-first-as?                 empty
       |  +--rw scan-time?                        uint32
       |  +--rw maximum-as-limit?                 uint8
       |  +--rw med-out-delay?                    uint32
       |  +--rw no-client-to-client-reflection
       |  |  +--rw all?          empty
       |  |  +--rw cluster-id*   union
       |  +--rw deterministic-med?                empty
       |  +--rw maximum-paths
       |  |  +--rw ibgp?   uint32
       |  |  +--rw ebgp?   uint32
       |  +--rw router-id?                        types:ipv4-address
       +--rw timers!
       |  +--rw holdtime?    uint32
       |  +--rw keepalive?   uint32
       +--rw peer-group* [tagnode]
       |  +--rw tagnode                           string
       |  +--rw interface* [ifname]
       |  |  +--rw ifname           types:interface-ifname
       |  |  +--rw vrrp-failover!
       |  |     +--rw vrrp-group* [groupid]
       |  |        +--rw groupid       uint8
       |  |        +--rw prepend-as?   string
       |  |        +--rw med?          uint32
       |  |        +--rw route-map?    -> /policy:policy/policy-route:route/route-map/tagnode
       |  +--rw med-out
       |  |  +--rw igp!
       |  |  |  +--rw delay-updates?   empty
       |  |  +--rw minimum-igp?   empty
       |  +--rw cluster-id?                       union
       |  +--rw strict-capability-match?          empty
       |  +--rw password?                         string
       |  +--rw override-capability?              empty
       |  +--rw local-as* [tagnode]
       |  |  +--rw tagnode    uint32
       |  +--rw as-origination-interval?          uint32
       |  +--rw ttl-security!
       |  |  +--rw hops?   uint32
       |  +--rw capability!
       |  |  +--rw dynamic?         empty
       |  |  +--rw route-refresh?   empty
       |  +--rw disable-capability-negotiation?   empty
       |  +--rw enforce-multihop?                 empty
       |  +--rw description?                      string
       |  +--rw update-source?                    union
       |  +--rw advertisement-interval?           uint32
       |  +--rw passive?                          empty
       |  +--rw port?                             uint32
       |  +--rw shutdown?                         empty
       |  +--rw timers!
       |  |  +--rw connect?     uint32
       |  |  +--rw holdtime?    uint32
       |  |  +--rw keepalive?   uint32
       |  +--rw ebgp-multihop?                    uint32
       |  +--rw remote-as?                        uint32
       |  +--rw address-family!
       |     +--rw ipv4-unicast!
       |     |  +--rw route-map
       |     |  |  +--rw export?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  |  +--rw import?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  +--rw filter-list!
       |     |  |  +--rw export?   -> /policy:policy/policy-route:route/as-path-list/tagnode
       |     |  |  +--rw import?   -> /policy:policy/policy-route:route/as-path-list/tagnode
       |     |  +--rw attribute-unchanged
       |     |  |  +--rw next-hop?   empty
       |     |  |  +--rw med?        empty
       |     |  |  +--rw as-path?    empty
       |     |  +--rw remove-private-as?        empty
       |     |  +--rw route-reflector-client?   empty
       |     |  +--rw maximum-prefix* [tagnode]
       |     |  |  +--rw tagnode         uint32
       |     |  |  +--rw warning-only?   empty
       |     |  |  +--rw threshold* [tagnode]
       |     |  |     +--rw tagnode         uint32
       |     |  |     +--rw warning-only?   empty
       |     |  +--rw allowas-in!
       |     |  |  +--rw number?   uint32
       |     |  +--rw weight?                   uint32
       |     |  +--rw disable-send-community
       |     |  |  +--rw extended?   empty
       |     |  |  +--rw standard?   empty
       |     |  +--rw capability!
       |     |  |  +--rw graceful-restart!
       |     |  |  |  +--rw disable?   empty
       |     |  |  +--rw orf!
       |     |  |     +--rw prefix-list!
       |     |  |        +--rw receive?   empty
       |     |  |        +--rw send?      empty
       |     |  +--rw soft-reconfiguration
       |     |  |  +--rw inbound?   empty
       |     |  +--rw default-originate!
       |     |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  +--rw unsuppress-map?           -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  +--rw nexthop-self?             empty
       |     |  +--rw route-server-client?      empty
       |     |  +--rw prefix-list
       |     |  |  +--rw export?   -> /policy:policy/policy-route:route/prefix-list/tagnode
       |     |  |  +--rw import?   -> /policy:policy/policy-route:route/prefix-list/tagnode
       |     |  +--rw distribute-list
       |     |     +--rw export?   uint32
       |     |     +--rw import?   uint32
       |     +--rw ipv6-unicast!
       |        +--rw route-map
       |        |  +--rw export?   -> /policy:policy/policy-route:route/route-map/tagnode
       |        |  +--rw import?   -> /policy:policy/policy-route:route/route-map/tagnode
       |        +--rw filter-list!
       |        |  +--rw export?   -> /policy:policy/policy-route:route/as-path-list/tagnode
       |        |  +--rw import?   -> /policy:policy/policy-route:route/as-path-list/tagnode
       |        +--rw attribute-unchanged
       |        |  +--rw next-hop?   empty
       |        |  +--rw med?        empty
       |        |  +--rw as-path?    empty
       |        +--rw remove-private-as?        empty
       |        +--rw route-reflector-client?   empty
       |        +--rw maximum-prefix* [tagnode]
       |        |  +--rw tagnode         uint32
       |        |  +--rw warning-only?   empty
       |        |  +--rw threshold* [tagnode]
       |        |     +--rw tagnode         uint32
       |        |     +--rw warning-only?   empty
       |        +--rw allowas-in!
       |        |  +--rw number?   uint32
       |        +--rw weight?                   uint32
       |        +--rw disable-send-community
       |        |  +--rw extended?   empty
       |        |  +--rw standard?   empty
       |        +--rw capability!
       |        |  +--rw graceful-restart!
       |        |  |  +--rw disable?   empty
       |        |  +--rw orf!
       |        |     +--rw prefix-list!
       |        |        +--rw receive?   empty
       |        |        +--rw send?      empty
       |        +--rw soft-reconfiguration
       |        |  +--rw inbound?   empty
       |        +--rw default-originate!
       |        |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |        +--rw unsuppress-map?           -> /policy:policy/policy-route:route/route-map/tagnode
       |        +--rw nexthop-self?             empty
       |        +--rw route-server-client?      empty
       |        +--rw prefix-list!
       |        |  +--rw export?   -> /policy:policy/policy-route:route/prefix-list6/tagnode
       |        |  +--rw import?   -> /policy:policy/policy-route:route/prefix-list6/tagnode
       |        +--rw distribute-list!
       |           +--rw export?   uint32
       |           +--rw import?   uint32
       +--rw neighbor* [tagnode]
       |  +--rw tagnode                           union
       |  +--rw interface* [ifname]
       |  |  +--rw ifname           types:interface-ifname
       |  |  +--rw vrrp-failover!
       |  |     +--rw vrrp-group* [groupid]
       |  |        +--rw groupid       uint8
       |  |        +--rw prepend-as?   string
       |  |        +--rw med?          uint32
       |  |        +--rw route-map?    -> /policy:policy/policy-route:route/route-map/tagnode
       |  +--rw med-out
       |  |  +--rw igp!
       |  |  |  +--rw delay-updates?   empty
       |  |  +--rw minimum-igp?   empty
       |  +--rw cluster-id?                       union
       |  +--rw strict-capability-match?          empty
       |  +--rw password?                         string
       |  +--rw override-capability?              empty
       |  +--rw local-as* [tagnode]
       |  |  +--rw tagnode    uint32
       |  +--rw as-origination-interval?          uint32
       |  +--rw ttl-security!
       |  |  +--rw hops?   uint32
       |  +--rw capability!
       |  |  +--rw dynamic?         empty
       |  |  +--rw route-refresh?   empty
       |  +--rw disable-capability-negotiation?   empty
       |  +--rw enforce-multihop?                 empty
       |  +--rw description?                      string
       |  +--rw update-source?                    union
       |  +--rw advertisement-interval?           uint32
       |  +--rw passive?                          empty
       |  +--rw port?                             uint32
       |  +--rw shutdown?                         empty
       |  +--rw timers!
       |  |  +--rw connect?     uint32
       |  |  +--rw holdtime?    uint32
       |  |  +--rw keepalive?   uint32
       |  +--rw ebgp-multihop?                    uint32
       |  +--rw remote-as?                        uint32
       |  +--rw log
       |  |  +--rw all?         empty
       |  |  +--rw events?      empty
       |  |  +--rw filters?     empty
       |  |  +--rw fsm?         empty
       |  |  +--rw keepalive?   empty
       |  |  +--rw update
       |  |  |  +--rw in?    empty
       |  |  |  +--rw out?   empty
       |  |  |  +--rw all?   empty
       |  |  +--rw bfd?         empty
       |  |  +--rw dampening?   empty
       |  |  +--rw msdp?        empty
       |  +--rw route-map
       |  |  +--rw export?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  |  +--rw import?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  +--rw address-family!
       |     +--rw ipv4-unicast!
       |     |  +--rw route-map
       |     |  |  +--rw export?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  |  +--rw import?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  +--rw filter-list!
       |     |  |  +--rw export?   -> /policy:policy/policy-route:route/as-path-list/tagnode
       |     |  |  +--rw import?   -> /policy:policy/policy-route:route/as-path-list/tagnode
       |     |  +--rw attribute-unchanged
       |     |  |  +--rw next-hop?   empty
       |     |  |  +--rw med?        empty
       |     |  |  +--rw as-path?    empty
       |     |  +--rw remove-private-as?        empty
       |     |  +--rw route-reflector-client?   empty
       |     |  +--rw maximum-prefix* [tagnode]
       |     |  |  +--rw tagnode         uint32
       |     |  |  +--rw warning-only?   empty
       |     |  |  +--rw threshold* [tagnode]
       |     |  |     +--rw tagnode         uint32
       |     |  |     +--rw warning-only?   empty
       |     |  +--rw allowas-in!
       |     |  |  +--rw number?   uint32
       |     |  +--rw weight?                   uint32
       |     |  +--rw disable-send-community
       |     |  |  +--rw extended?   empty
       |     |  |  +--rw standard?   empty
       |     |  +--rw capability!
       |     |  |  +--rw graceful-restart!
       |     |  |  |  +--rw disable?   empty
       |     |  |  +--rw orf!
       |     |  |     +--rw prefix-list!
       |     |  |        +--rw receive?   empty
       |     |  |        +--rw send?      empty
       |     |  +--rw soft-reconfiguration
       |     |  |  +--rw inbound?   empty
       |     |  +--rw default-originate!
       |     |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  +--rw unsuppress-map?           -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  +--rw nexthop-self?             empty
       |     |  +--rw route-server-client?      empty
       |     |  +--rw prefix-list
       |     |  |  +--rw export?   -> /policy:policy/policy-route:route/prefix-list/tagnode
       |     |  |  +--rw import?   -> /policy:policy/policy-route:route/prefix-list/tagnode
       |     |  +--rw distribute-list
       |     |  |  +--rw export?   uint32
       |     |  |  +--rw import?   uint32
       |     |  +--rw peer-group?               -> ../../../../peer-group/tagnode
       |     +--rw ipv6-unicast!
       |        +--rw route-map
       |        |  +--rw export?   -> /policy:policy/policy-route:route/route-map/tagnode
       |        |  +--rw import?   -> /policy:policy/policy-route:route/route-map/tagnode
       |        +--rw filter-list!
       |        |  +--rw export?   -> /policy:policy/policy-route:route/as-path-list/tagnode
       |        |  +--rw import?   -> /policy:policy/policy-route:route/as-path-list/tagnode
       |        +--rw attribute-unchanged
       |        |  +--rw next-hop?   empty
       |        |  +--rw med?        empty
       |        |  +--rw as-path?    empty
       |        +--rw remove-private-as?        empty
       |        +--rw route-reflector-client?   empty
       |        +--rw maximum-prefix* [tagnode]
       |        |  +--rw tagnode         uint32
       |        |  +--rw warning-only?   empty
       |        |  +--rw threshold* [tagnode]
       |        |     +--rw tagnode         uint32
       |        |     +--rw warning-only?   empty
       |        +--rw allowas-in!
       |        |  +--rw number?   uint32
       |        +--rw weight?                   uint32
       |        +--rw disable-send-community
       |        |  +--rw extended?   empty
       |        |  +--rw standard?   empty
       |        +--rw capability!
       |        |  +--rw graceful-restart!
       |        |  |  +--rw disable?   empty
       |        |  +--rw orf!
       |        |     +--rw prefix-list!
       |        |        +--rw receive?   empty
       |        |        +--rw send?      empty
       |        +--rw soft-reconfiguration
       |        |  +--rw inbound?   empty
       |        +--rw default-originate!
       |        |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |        +--rw unsuppress-map?           -> /policy:policy/policy-route:route/route-map/tagnode
       |        +--rw nexthop-self?             empty
       |        +--rw route-server-client?      empty
       |        +--rw prefix-list!
       |        |  +--rw export?   -> /policy:policy/policy-route:route/prefix-list6/tagnode
       |        |  +--rw import?   -> /policy:policy/policy-route:route/prefix-list6/tagnode
       |        +--rw distribute-list!
       |        |  +--rw export?   uint32
       |        |  +--rw import?   uint32
       |        +--rw peer-group?               -> ../../../../peer-group/tagnode
       +--rw address-family!
       |  +--rw ipv4-unicast!
       |  |  +--rw parameters!
       |  |  |  +--rw synchronization?           empty
       |  |  |  +--rw network-synchronization?   empty
       |  |  |  +--rw distance!
       |  |  |  |  +--rw global!
       |  |  |  |     +--rw local?      uint32
       |  |  |  |     +--rw internal?   uint32
       |  |  |  |     +--rw external?   uint32
       |  |  |  +--rw dampening!
       |  |  |     +--rw re-use?                      uint32
       |  |  |     +--rw half-life?                   uint32
       |  |  |     +--rw start-suppress?              uint32
       |  |  |     +--rw max-suppress-time?           uint32
       |  |  |     +--rw un-reachability-half-life?   uint32
       |  |  +--rw aggregate-address* [tagnode]
       |  |  |  +--rw tagnode         types:ipv4-prefix
       |  |  |  +--rw as-set?         empty
       |  |  |  +--rw summary-only?   empty
       |  |  +--rw network* [tagnode]
       |  |  |  +--rw tagnode      types:ipv4-prefix
       |  |  |  +--rw backdoor?    empty
       |  |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  |  +--rw redistribute!
       |  |  |  +--rw kernel!
       |  |  |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  |  |  +--rw rip!
       |  |  |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  |  |  +--rw connected!
       |  |  |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  |  |  +--rw static!
       |  |  |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  |  |  +--rw ospf!
       |  |  |     +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  |  +--rw auto-summary?        empty
       |  |  +--rw nexthop!
       |  |     +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  +--rw ipv6-unicast!
       |     +--rw parameters!
       |     |  +--rw synchronization?           empty
       |     |  +--rw network-synchronization?   empty
       |     |  +--rw distance!
       |     |  |  +--rw global!
       |     |  |     +--rw local?      uint32
       |     |  |     +--rw internal?   uint32
       |     |  |     +--rw external?   uint32
       |     |  +--rw dampening!
       |     |     +--rw re-use?                      uint32
       |     |     +--rw half-life?                   uint32
       |     |     +--rw start-suppress?              uint32
       |     |     +--rw max-suppress-time?           uint32
       |     |     +--rw un-reachability-half-life?   uint32
       |     +--rw aggregate-address* [tagnode]
       |     |  +--rw tagnode         types:ipv6-prefix
       |     |  +--rw as-set?         empty
       |     |  +--rw summary-only?   empty
       |     +--rw network* [tagnode]
       |     |  +--rw tagnode      types:ipv6-prefix
       |     |  +--rw backdoor?    empty
       |     |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     +--rw redistribute!
       |     |  +--rw kernel!
       |     |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  +--rw ripng!
       |     |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  +--rw connected!
       |     |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  +--rw static!
       |     |  |  +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     |  +--rw ospfv3!
       |     |     +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       |     +--rw auto-summary?        empty
       |     +--rw nexthop!
       |        +--rw route-map?   -> /policy:policy/policy-route:route/route-map/tagnode
       +--rw log
          +--rw all?         empty
          +--rw events?      empty
          +--rw filters?     empty
          +--rw fsm?         empty
          +--rw nsm?         empty
          +--rw keepalive?   empty
          +--rw update
          |  +--rw in?    empty
          |  +--rw out?   empty
          |  +--rw all?   empty
          +--rw bfd?         empty
          +--rw dampening?   empty
          +--rw msdp?        empty
          +--rw rib?         empty
  augment /service:service/service-snmp:snmp/service-snmp:notification:
    +--rw bgp
       +--rw all?   empty
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$
```

- Looking for a bigger data model and diplay only the 4 levels:

```
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$ pyang -f tree vyatta-protocols-bgp-v1.yang --tree-depth=4
module: vyatta-protocols-bgp-v1
  augment /protocols:protocols:
    +--rw bgp* [tagnode]
       +--rw tagnode           uint32
       +--rw parameters!
       |  +--rw extended-asn-capability?          empty
       |  +--rw no-rtm?                           empty
       |  +--rw cluster-id?                       types:ipv4-address
       |  +--rw always-compare-med?               empty
       |  +--rw default!
       |  |  +--rw local-pref?   uint32
       |  +--rw confederation!
       |  |  +--rw identifier?   uint32
       |  |  +--rw peers*        uint32
       |  +--rw graceful-restart!
       |  |  +--rw graceful-reset?   empty
       |  |  +--rw restart-time?     uint32
       |  |  +--rw stalepath-time?   uint32
       |  +--rw bestpath!
       |  |  +--rw med!
       |  |  |     ...
       |  |  +--rw as-path!
       |  |  |     ...
       |  |  +--rw compare-routerid?    empty
       |  |  +--rw igp-metric-ignore?   empty
       |  +--rw log-neighbor-changes?             empty
       |  +--rw no-fast-external-failover?        empty
       |  +--rw enforce-first-as?                 empty
       |  +--rw scan-time?                        uint32
       |  +--rw maximum-as-limit?                 uint8
       |  +--rw med-out-delay?                    uint32
       |  +--rw no-client-to-client-reflection
       |  |  +--rw all?          empty
       |  |  +--rw cluster-id*   union
       |  +--rw deterministic-med?                empty
       |  +--rw maximum-paths
       |  |  +--rw ibgp?   uint32
       |  |  +--rw ebgp?   uint32
       |  +--rw router-id?                        types:ipv4-address
       +--rw timers!
       |  +--rw holdtime?    uint32
       |  +--rw keepalive?   uint32
       +--rw peer-group* [tagnode]
       |  +--rw tagnode                           string
       |  +--rw interface* [ifname]
       |  |  +--rw ifname           types:interface-ifname
       |  |  +--rw vrrp-failover!
       |  |        ...
       |  +--rw med-out
       |  |  +--rw igp!
       |  |  |     ...
       |  |  +--rw minimum-igp?   empty
       |  +--rw cluster-id?                       union
       |  +--rw strict-capability-match?          empty
       |  +--rw password?                         string
       |  +--rw override-capability?              empty
       |  +--rw local-as* [tagnode]
       |  |  +--rw tagnode    uint32
       |  +--rw as-origination-interval?          uint32
       |  +--rw ttl-security!
       |  |  +--rw hops?   uint32
       |  +--rw capability!
       |  |  +--rw dynamic?         empty
       |  |  +--rw route-refresh?   empty
       |  +--rw disable-capability-negotiation?   empty
       |  +--rw enforce-multihop?                 empty
       |  +--rw description?                      string
       |  +--rw update-source?                    union
       |  +--rw advertisement-interval?           uint32
       |  +--rw passive?                          empty
       |  +--rw port?                             uint32
       |  +--rw shutdown?                         empty
       |  +--rw timers!
       |  |  +--rw connect?     uint32
       |  |  +--rw holdtime?    uint32
       |  |  +--rw keepalive?   uint32
       |  +--rw ebgp-multihop?                    uint32
       |  +--rw remote-as?                        uint32
       |  +--rw address-family!
       |     +--rw ipv4-unicast!
       |     |     ...
       |     +--rw ipv6-unicast!
       |           ...
       +--rw neighbor* [tagnode]
       |  +--rw tagnode                           union
       |  +--rw interface* [ifname]
       |  |  +--rw ifname           types:interface-ifname
       |  |  +--rw vrrp-failover!
       |  |        ...
       |  +--rw med-out
       |  |  +--rw igp!
       |  |  |     ...
       |  |  +--rw minimum-igp?   empty
       |  +--rw cluster-id?                       union
       |  +--rw strict-capability-match?          empty
       |  +--rw password?                         string
       |  +--rw override-capability?              empty
       |  +--rw local-as* [tagnode]
       |  |  +--rw tagnode    uint32
       |  +--rw as-origination-interval?          uint32
       |  +--rw ttl-security!
       |  |  +--rw hops?   uint32
       |  +--rw capability!
       |  |  +--rw dynamic?         empty
       |  |  +--rw route-refresh?   empty
       |  +--rw disable-capability-negotiation?   empty
       |  +--rw enforce-multihop?                 empty
       |  +--rw description?                      string
       |  +--rw update-source?                    union
       |  +--rw advertisement-interval?           uint32
       |  +--rw passive?                          empty
       |  +--rw port?                             uint32
       |  +--rw shutdown?                         empty
       |  +--rw timers!
       |  |  +--rw connect?     uint32
       |  |  +--rw holdtime?    uint32
       |  |  +--rw keepalive?   uint32
       |  +--rw ebgp-multihop?                    uint32
       |  +--rw remote-as?                        uint32
       |  +--rw log
       |  |  +--rw all?         empty
       |  |  +--rw events?      empty
       |  |  +--rw filters?     empty
       |  |  +--rw fsm?         empty
       |  |  +--rw keepalive?   empty
       |  |  +--rw update
       |  |  |     ...
       |  |  +--rw bfd?         empty
       |  |  +--rw dampening?   empty
       |  |  +--rw msdp?        empty
       |  +--rw route-map
       |  |  +--rw export?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  |  +--rw import?   -> /policy:policy/policy-route:route/route-map/tagnode
       |  +--rw address-family!
       |     +--rw ipv4-unicast!
       |     |     ...
       |     +--rw ipv6-unicast!
       |           ...
       +--rw address-family!
       |  +--rw ipv4-unicast!
       |  |  +--rw parameters!
       |  |  |     ...
       |  |  +--rw aggregate-address* [tagnode]
       |  |  |     ...
       |  |  +--rw network* [tagnode]
       |  |  |     ...
       |  |  +--rw redistribute!
       |  |  |     ...
       |  |  +--rw auto-summary?        empty
       |  |  +--rw nexthop!
       |  |        ...
       |  +--rw ipv6-unicast!
       |     +--rw parameters!
       |     |     ...
       |     +--rw aggregate-address* [tagnode]
       |     |     ...
       |     +--rw network* [tagnode]
       |     |     ...
       |     +--rw redistribute!
       |     |     ...
       |     +--rw auto-summary?        empty
       |     +--rw nexthop!
       |           ...
       +--rw log
          +--rw all?         empty
          +--rw events?      empty
          +--rw filters?     empty
          +--rw fsm?         empty
          +--rw nsm?         empty
          +--rw keepalive?   empty
          +--rw update
          |  +--rw in?    empty
          |  +--rw out?   empty
          |  +--rw all?   empty
          +--rw bfd?         empty
          +--rw dampening?   empty
          +--rw msdp?        empty
          +--rw rib?         empty
  augment /service:service/service-snmp:snmp/service-snmp:notification:
    +--rw bgp
       +--rw all?   empty
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$
```

- Looking for a bigger data model and diplay a specific section:
```

```

## Generates Python classes from a YANG module:

### Introduction to pyangbind (a pyang plugin)

WORK IN PROGRESS !!!

- https://github.com/robshakir/pyangbind

- Pyang uses a pointer to identify where pyang-bind plugin is installed: 
```
mab@mab-infra:~$ export PYBINDPLUGIN=`/usr/bin/env python -c \
> 'import pyangbind; import os; print "%s/plugin" % os.path.dirname(pyangbind.__file__)'`
mab@mab-infra:~$ echo $PYBINDPLUGIN
/home/mab/.local/lib/python2.7/site-packages/pyangbind/plugin
mab@mab-infra:~$ 
mab@mab-infra:~$ 
```
- That will allows you to use ```--plugindir $PYBINDPLUGIN ``` when calling pyang.

```
mab@mab-infra:~/mab_automate/nw_automation_with_odl/yang_tools/yang_modules/vyatta$ pyang --plugindir $PYBINDPLUGIN -f pybind -o vyatta-protocols-bgp-v1.py vyatta-protocols-bgp-v1.yang
```

