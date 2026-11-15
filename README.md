# Penetration Testing Report --- Footprinting & Network Scanning

A Week 2 cybersecurity and ethical hacking internship project
documenting two practical activities:

1.  **Footprinting and reconnaissance** of `networkwalks.com` using Kali
    Linux tools.
2.  **Network discovery** on the author's own local LAN using Zenmap
    (Nmap GUI).

> **Important:** These activities were performed only on systems for
> which written permission had been secured or on systems owned by the
> author. This repository is for educational and research purposes only.
> Do not use these techniques against systems or networks without
> authorization.

## Project Information

  -----------------------------------------------------------------------
  Field                               Details
  ----------------------------------- -----------------------------------
  Program                             Cybersecurity Program ---
                                      Networkwalks

  Week                                02

  Batch                               B084-Networkwalks

  Report date                         13 November 2026

  Pentester                           Emmanuel John

  Author                              Rudraksh Kaushik

  Modules completed                   W2-PM1 (Multiple Kali Tools),
                                      W2-PM5 (Zenmap Scanning)

  Scope                               `networkwalks.com` (written
                                      permission secured) and the
                                      author's own local LAN

  Activities covered                  Phase 1: Reconnaissance &
                                      Footprinting; Phase 2: Scanning &
                                      Network Discovery

  Further phases                      Phases 3--5 were in progress at the
                                      time of the report
  -----------------------------------------------------------------------

## Objectives

-   Gather publicly available information about the authorized target
    domain.
-   Identify web technologies and inspect DNS and HTTP information.
-   Discover active devices on the author's local network.
-   Record observations, potential risks, and security recommendations.
-   Document the work and its evidence.

## Tools Used

  -----------------------------------------------------------------------
  Tool                                Purpose
  ----------------------------------- -----------------------------------
  Kali Linux                          Operating system used for
                                      footprinting activities

  WHOIS                               Retrieve publicly available domain
                                      registration details and
                                      name-server information

  WhatWeb                             Identify web technologies and
                                      components

  `nslookup`                          Resolve a domain name to an IP
                                      address

  `curl -I`                           Inspect HTTP response headers

  Wafw00f                             Identify the presence and type of a
                                      Web Application Firewall

  DNSRecon                            Enumerate DNS records and related
                                      infrastructure information

  Zenmap (Nmap GUI)                   Discover live hosts and view
                                      network topology

  Windows CMD (`ipconfig`)            Identify local IP and network
                                      configuration
  -----------------------------------------------------------------------

## Activities and Observations

### 1. Footprinting & Reconnaissance

The `networkwalks.com` domain was examined using six Kali Linux tools.

  -----------------------------------------------------------------------
  Tool                                Observation recorded in the report
  ----------------------------------- -----------------------------------
  WHOIS                               Retrieved publicly available domain
                                      registration and name-server
                                      information

  WhatWeb                             Identified WordPress 7.0.4 and WP
                                      Download Manager 3.3.58

  `nslookup`                          Resolved the domain to
                                      `192.232.216.135`

  `curl -I`                           Returned HTTP response headers and
                                      exposed the `/wp-json/` endpoint

  Wafw00f                             Identified ModSecurity (SpiderLabs)

  DNSRecon                            Returned information about name
                                      servers, mail servers, SPF/TXT
                                      records, service records, and DNS
                                      software
  -----------------------------------------------------------------------

### 2. Network Scanning with Zenmap

The local network configuration was first checked using Windows
`ipconfig`. The subnet was then entered in Zenmap and a **Ping Scan**
was used to identify active hosts.

The report's example results list these live hosts:

-   `192.168.31.1`
-   `192.168.31.2`
-   `192.168.31.3`
-   `192.168.31.4`
-   Additional hosts may also have been present.

The practical also recorded MAC-address information and used Zenmap's
**Topology** view to create a network topology, which was saved as a
PDF.

> **Note:** The report explicitly states that the example subnet, host
> count, and addresses should be replaced with results from the author's
> own network before submission. Treat the addresses above as example
> results, not verified details of every network.

## Risk Analysis

The report identifies the following potential risks. These are
observations from information gathering and host discovery, **not
confirmed vulnerabilities**.

  -----------------------------------------------------------------------
  Finding                 Potential impact        Risk level
  ----------------------- ----------------------- -----------------------
  Web technology          Technology and version  Medium
  information exposed     details may help an     
                          attacker identify       
                          software for further    
                          review                  

  Server IP address       Reveals information     Low
  identifiable            about the web service's 
                          network location        

  HTTP technical          May assist technology   Low
  information exposed     fingerprinting and      
                          further enumeration     

  WAF technology          Reveals information     Low
  identifiable            about the web           
                          application's security  
                          architecture            

  DNS infrastructure      Can help build a        Medium
  information exposed     broader infrastructure  
                          profile                 

  Multiple live hosts     Unknown or unauthorized Medium
  visible on the local    devices may potentially 
  network                 be present              
  -----------------------------------------------------------------------

No exploitation or vulnerability validation was performed as part of
these two modules. A software version, IP address, or DNS record alone
does not establish that a system is vulnerable.

## Recommendations

1.  Review publicly exposed information about web technologies, CMS
    platforms, and plugins.
2.  Keep CMS platforms, plugins, and other web technologies updated.
3.  Review HTTP response headers and reduce unnecessary technical
    disclosures.
4.  Periodically review DNS records and confirm that only required
    information and services are exposed.
5.  Keep the ModSecurity WAF enabled, properly configured, and
    monitored.
6.  Perform regular discovery scans on networks that the organization
    owns or is authorized to assess.
7.  Investigate and verify unexpected devices found during network
    scans.
8.  Maintain current network topology and device documentation.
9.  Perform reconnaissance and scanning only with appropriate
    authorization.

## Evidence

The original report includes evidence screenshots on its evidence pages.
Include the corresponding screenshots and the exported Zenmap topology
PDF in this repository if they are available.

Suggested organization:

``` text
.
├── README.md
├── Pentest report.docx
└── evidence/
    ├── footprinting/
    ├── zenmap/
    └── network-topology.pdf
```

The folder and filenames above are suggestions; add only evidence files
that you actually have.

## Conclusion

The project provided practical experience with domain footprinting, web
technology identification, DNS enumeration, HTTP header inspection, WAF
detection, and local network discovery using Zenmap. It also
demonstrated the importance of recording findings, assessing potential
impact carefully, and staying within an explicitly authorized testing
scope.

## Author

**Rudraksh Kaushik**

-   LinkedIn:
    [rudraksh-kaushik](https://www.linkedin.com/in/rudraksh-kaushik-48465b43b)

## Disclaimer

This project is intended for educational and research purposes only.
Testing was limited to systems with written permission or systems owned
by the author. Unauthorized access or scanning may be illegal. The
author, instructors, and Networkwalks are not responsible for misuse of
the information in this repository. Anyone using these techniques is
responsible for ensuring that they have the necessary authorization and
comply with applicable laws.
