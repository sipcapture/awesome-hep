# Awesome HEP  [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
A curated list of [HEP-EEP](https://github.com/sipcapture/hep) enabled projects and products.

## Contribution Guidelines
* Add entries alphabetically, under the appropriate category.
* To add, remove, or change things on the list: Submit a pull request.
* Description should contain a link with the name of the package/project/website.
* Do not exceed more than a paragraph.

### Full-Stack Applications
* [HOMER](http://github.com/sipcapture/homer) - HOMER is a robust, carrier-grade, scalable SIP Capture system and VoiP Monitoring Application based on HEP/EEP encapsulation, ready to process & store insane amounts of signaling, logs and statistics with instant indexing, search, end-to-end analysis and protocol drill-down capabilities, built on top of OpenSIPS or Kamailio as Capture Servers.
* [HEPIC](http://hepic.tel) - HEPIC is a stand-alone HEP/EEP centric real-time packet capture framework, with protocol agnostic indexing and highly-scalable correlation, media and customization capabilities for advanced usage and integrations with 3rd party VoIP/RTC platforms and services.

### Server Applications
* [OpenSIPS](https://opensips.org) - OpenSIPS is a GPL implementation of a multi-functionality SIP Server with deep HEP support providing Server, [Client](http://www.opensips.org/html/docs/modules/2.2.x/siptrace.html) and [Switch/Proxy](https://github.com/sipcapture/homer/wiki/Examples%3A-opensips-hepswitch) features to forge and manipulate HEP packets.
* [Kamailio](https://github.com/kamailio/kamailio) - The Kamailio SIP server is designed for scalability, targeting large deployments (e.g. for IP telephony operators or carriers, which have a large subscriber base or route a big volume of calls) providing [Server](https://www.kamailio.org/docs/modules/5.0.x/modules/sipcapture.html) and [Client](https://www.kamailio.org/docs/modules/5.0.x/modules/siptrace.html) features to mirror HEP packets.

### Client Applications
* [CaptAgent](https://github.com/sipcapture/captagent) - CaptAgent is a modular packet capture agent/probe for RT protocols with bleeding edge HEP support.
* [HEPlify](https://github.com/sipcapture/heplify) - heplify is captagents little brother. While it offers a compareable performance the design goal was simplicity. It's a single binary which you can run to capture packets and send them to Homer. Right now heplify is able to send SIP, correlated RTCP, RTCPXR and very basic DNS, LOG or TLS handshakes into HOMER.
* [sngrep](https://github.com/irontec/sngrep) - sngrep is a tool for displaying SIP calls message flows from terminal with native HEP-EEP client and relay capabilities.
* [sipgrep](https://github.com/sipcapture/sipgrep) - sipgrep is a tool for displaying and troubleshoot SIP signaling over IP networks in console, with native HEP-EEP client and relay capabilities.

### Gateway Applications
* [paStash](https://github.com/sipcapture/pastash) - PaStasH (pastaʃ'ʃ-utta) is a NodeJS multi I/O processor supporting ingestion, decoding, interpolation and correlation of data - be it logs, packets, events and beyond. PaStash supports the Logstash configuration format and delivers cross-functionality comparable to "Beats" with custom modules, providing a flexible and agnostig data pipelining tool, including [HEP-EEP](https://github.com/sipcapture/paStash/blob/master/docs/outputs/hep.md) output support.
* [horaclifix](https://github.com/negbie/horaclifix) - horaclifix sends IPFIX messages from Oracle SBC's into Homer as HEP-EEP
* [HEPfix.js](https://github.com/sipcapture/hepfix.js) - NodeJS IPFIX adaptor for HOMER/HEP and Oracle Acme Packet SBCs

### Tools
* [HEPgen.js](https://github.com/sipcapture/hepgen.js) - HEPgen is a NodeJS HEP Packet Generator for SIP-less Devs and Unit Testing
* [HEP Wireshark](https://github.com/sipcapture/hep-wireshark) - HEP-EEP Wireshark Dissector as a LUA plugin
* [HEPipe.js](https://github.com/sipcapture/hepipe.js) - Pipe arbitrary data rows (logs, events, cdrs, esl, etc) to HEP Server
* [hammerHEP](https://github.com/negbie/hammerHEP) - HEP Server stress-tool

### Cloud - PaaS
* [sipcapture.io](https://sipcapture.io) - Hosted and Maintained versions of HOMER and HEPIC straight from its makers.

### Libraries and Code Examples
  * [C](https://github.com/sipcapture/hep-c)
  * [Java](https://github.com/sipcapture/hep-java)
  * [Javascript](https://github.com/sipcapture/hep-js)
  * [GO](https://github.com/sipcapture/hep-go)
  * [Perl](https://github.com/sipcapture/hep-perl)
  * [Python](https://github.com/sipcapture/hep-python)
  * [Erlang](https://github.com/sipcapture/hep-erlang)
