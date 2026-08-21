# <img src="http://i.imgur.com/RSUlFRa.gif" width="150" alt="HEP">

# Awesome HEP  [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A curated list of [HEP/EEP](https://github.com/sipcapture/hep) enabled projects and products — the **Homer Encapsulation Protocol** (also called Extensible Encapsulation Protocol) used by [SIPCAPTURE](https://github.com/sipcapture) / [HOMER](https://github.com/sipcapture/homer) and [QXIP](https://qxip.net).


## Contribution Guidelines
* Add entries alphabetically, under the appropriate category.
* To add, remove, or change things on the list: Submit a pull request.
* Description should contain a link with the name of the package/project


### HEP Protocol Specs
* [HEP/EEP](https://github.com/sipcapture/hep) - Specification and technical documentation for HEPv3 (chunk-based encapsulation of SIP, RTCP, logs, JSON and vendor extensions). Vendor IDs include FreeSWITCH (`0x0001`), Kamailio (`0x0002`), OpenSIPS (`0x0003`), Asterisk (`0x0004`), HOMER (`0x0005`), sipXecs (`0x0006`), Yeti Switch (`0x0007`) and Genesys (`0x0008`).

### Full-Stack Applications
* [HEPIC](https://hepic.tel) - Commercial HEP/EEP-centric VoIP and RTC observability platform from QXIP, with real-time session tracking, media QoS, clustering, partitioning and 3rd-party integrations, fully compatible with the open-source HEP agent stack.
* [HOMER](https://github.com/sipcapture/homer) - 100% open-source SIP, VoIP and RTC capture system. Homer 11 is an all-in-one HEP ingest, DuckLake/Parquet storage, FlightSQL and REST API monolith, backwards compatible with HEPv3 agents on UDP/9060, TCP/9061 and HTTP.

### HEP Server Applications
* [HEPlify-server](https://github.com/sipcapture/heplify-server) - Stand-alone HOMER capture server in Go. Ingests TCP/TLS/UDP HEP from heplify and other agents, indexes H5/H7 tables, and emits SIP/RTCP metrics for Prometheus and Grafana.
* [HEPop](https://github.com/sipcapture/hepop) - High-performance HEP capture server (Bun + DuckDB + Apache Parquet) for mass-scale ingest, compaction and OLAP query over local disk or object storage.
* [Kamailio](https://www.kamailio.org/docs/modules/stable/modules/sipcapture.html) - `sipcapture` module turns Kamailio into a HEP capture node (HEPv1/v2/v3, IPIP and raw mirroring) for HOMER.
* [OpenSIPS](https://opensips.org) - `proto_hep` + `sipcapture` provide a HEP server, [HEP switch/proxy](https://blog.opensips.org/2017/10/12/opensips-as-hep-proxyswitch/) (`hep_relay`) and [client](https://www.opensips.org/Documentation/Modules-devel) to forge, inspect and load-balance HEP toward HOMER or HEPIC.
* [VoIPmonitor](https://www.voipmonitor.org/doc/Sniffing_modes) - Commercial sniffer that listens for Homer Encapsulation Protocol on UDP/TCP 9060 (`hep=yes`, `hep_bind_port=9060`) from Kamailio, OpenSIPS, FreeSWITCH and other HEP sources.

### Native Client Applications
Open-source platforms that emit HEP themselves (no extra probe required).

* [Asterisk](https://github.com/sipcapture/homer/wiki/Examples:-Asterisk) - `res_hep` / `res_hep_pjsip` / `res_hep_rtcp` (Asterisk 12+) mirror SIP and RTCP to a HEP collector such as HOMER (`hep.conf`, default `:9060`).
* [Drachtio](https://drachtio.org) - High-performance SIP server with native HOMER capture (`<capture-server port="9060" hep-version="3">` or `--homer host:9060`).
* [FreeSWITCH](https://github.com/sipcapture/homer/wiki/Examples:-FreeSwitch) - Sofia capture agent (`capture-server=udp:host:9060;hep=3;capture_id=…`) ships SIP to HOMER; ESL events can be added via hepipe.js.
* [Kamailio](https://www.kamailio.org/docs/modules/stable/modules/siptrace.html) - `siptrace` duplicates SIP as HEPv3 toward a capture server (`hep_mode_on`, `hep_version=3`).
* [OpenSIPS](https://github.com/sipcapture/homer/wiki/Examples:-OpenSIPS) - Tracer/`siptrace` HEP client plus HEP switching on the same stack.
* [reConServer](http://www.resiprocate.org/Recon_Overview) - reSIProcate SBC / B2BUA with integrated HEP support.
* [repro](http://www.resiprocate.org/About_Repro) - reSIProcate SIP proxy with integrated HEP support.
* [RTP:Engine](https://github.com/sipwise/rtpengine) - Sipwise media proxy; sends RTCP / RTP stats to HOMER via HEP. See also [speech-to-text spooler](https://github.com/sipcapture/homer/wiki/Examples:-RTPEngine-speech) with HEP output.
* [sipXecs](https://www.sipfoundry.org) - sipXecs / [sipXhomer](https://github.com/sipcapture/sipXhomer) integration (HEP vendor ID `0x0006`); sipXecs 4.6+ replaced Sipviewer with HOMER SIP Capture.
* [Yate](https://yate.ro) - Native HEP capture (listed by QXIP alongside Kamailio, OpenSIPS, FreeSWITCH, Asterisk, RTP:Engine and Drachtio).
* [Yeti Switch](https://yeti-switch.org/docs/web-interface/system/sensors.html) - Class 4 softswitch with native HEPv3 sensors (target IP/port and `HEP_CAPTURE_ID`) for signaling and media mirroring to a HOMER capture node (vendor ID `0x0007`).

### Commercial Platforms & SBCs
Native HEP unless noted. Syslog/IPFIX paths are adapters, not on-box HEP.

* [AudioCodes](https://www.audiocodes.com) - SBC syslog is reassembled and converted to HEP by [paStash](https://github.com/sipcapture/paStash/wiki/Example:-AUDIOCODES-Syslog) (`app_audiocodes` → UDP/9060) when TLS signaling cannot be tapped off the wire.
* [Cisco ISR / CUBE](https://www.cisco.com) - Cisco syslog (`ccsipDisplayMsg`) converted to HEP by [paStash](https://github.com/sipcapture/paStash/wiki/Example:-CISCO-Syslog) (`app_cisco` → UDP/9060).
* [Genesys](https://www.genesys.com) - HEP3 vendor ID `0x0008`. Genesys Cloud Edge emits HEP with vendor chunks (`conversationId`, `organizationId`, `siteId`, `trunkBaseId`, `edgeId`). Application logs can also be shipped via [paStash `app_genesys`](https://github.com/sipcapture/paStash/wiki/Example:-GENESYS-Logs).
* [Oracle Communications SBC (Acme Packet)](https://www.oracle.com/communications/signaling-security/session-border-controller/) - Built-in comm-monitor exports SIP/QoS as IPFIX (not HEP). Convert to HEP with [HEPFIX.js](https://github.com/sipcapture/hepfix.js) or [horaclifix](https://github.com/negbie/horaclifix); older `packet-trace` used IPIP toward HOMER. See also the [HOMER wiki](https://github.com/sipcapture/homer/wiki/Examples:-ACME-Packet).
* [Ribbon / Sonus](https://ribboncommunications.com) - TRC syslog and Monitoring Profile (Extended SIP) converted to HEP by [paStash](https://github.com/sipcapture/paStash/wiki/Example:-SONUS-Logs) (`app_sonus` / monitoring recipe → 9060/9063) for TLS-opaque SBC traffic.
* [Sangoma SBC](https://www.sangoma.com) - Native HEP v1/v2/v3 SIP capture toward Homer (`udp:host:9060;hep=3;capture_id=…`). [Configuration](https://sangomakb.atlassian.net/wiki/spaces/SBC/pages/49152248/Session+Border+Controller+-+Enable+HEP+Capture+server).
* [Sansay](https://www.sansay.com) - Native HEP on recent VSXi SBC software (`protocol=HEP`, `signalingPort=9060`). [Example](https://github.com/sipcapture/homer/wiki/Example:-SANSAY-HEP).

### Stand-Alone Client Applications
* [CaptAgent](https://github.com/sipcapture/captagent) - Modular HEP capture agent/probe for RTC protocols (SIP, RTCP, RTCP-XR, Diameter, TLS, JSON) targeting HOMER.
* [captagent-js](https://github.com/sipcapture/captagent-js) - Sample Node.js HEP agent using hep-js.
* [HEPagent.rs](https://github.com/sipcapture/hepagent.rs) - Next-generation HEP capture agent in Rust (pcap/interface → Lua capture plan → HEP UDP/9060).
* [HEPjack](https://github.com/sipcapture/HEPjack.js) - Frida-based agent that sniffs forward-secrecy TLS/SIP at the source and forwards HEP.
* [HEPlify](https://github.com/sipcapture/heplify) - Portable single-binary HEP agent (Linux/macOS/Windows) for SIP, RTCP, DNS, Diameter and logs; default collector `127.0.0.1:9060`; can also relay HEP as a collector.
* [RTCAgent](https://github.com/sipcapture/rtcagent) - eBPF HEP agent for HOMER/HEPIC; hooks Kamailio, OpenSIPS, FreeSWITCH and RTPEngine in-process (default HEP port 9060) without decrypting on the wire.
* [RTPAgent](https://hepic.tel) - Commercial HEP agent with in-line RTP analyzer and recorder (QXIP / HEPIC).
* [sipgrep](https://github.com/sipcapture/sipgrep) - Console SIP troubleshooting tool with native HEP-EEP client and relay.
* [sngrep](https://github.com/irontec/sngrep) - Terminal SIP call-flow viewer with native HEP-EEP client and relay (`-L udp:host:9060`).

### Gateway Applications
* [HEPFIX.js](https://github.com/sipcapture/hepfix.js) - Node.js IPFIX-to-HEP adapter for Oracle / Acme Packet Net-Net SBCs → HOMER/HEPIC.
* [HEPSwitch](https://github.com/lmangani/docker-hepswitch) - Dockerized OpenSIPS HEP/EEP router and switch.
* [HEPipe.js](https://github.com/sipcapture/hepipe.js) - Pipes logs, FreeSWITCH ESL and Meetecho Janus events into HEP for HOMER.
* [horaclifix](https://github.com/negbie/horaclifix) - Go IPFIX-to-HEP gateway for Oracle SBC comm-monitor → HOMER.
* [Janus Gateway](https://janus.conf.meetecho.com) - WebRTC events (SIP, ICE, JSEP, media) encapsulated as HEP via [hepipe.js](https://github.com/sipcapture/hepipe.js) (and experimental native HOMER logger).
* [paStash](https://github.com/sipcapture/pastash) - Node.js multi I/O pipeline with [HEP output](https://github.com/sipcapture/paStash/blob/master/docs/outputs/hep.md) and vendor filters (AudioCodes, Cisco, Genesys, Ribbon/Sonus, and more).

### Tools
* [gossipper](https://github.com/sipcapture/gossipper) - Open-source SIP & WebRTC load-testing platform with HEP observability.
* [hammerHEP](https://github.com/negbie/hammerHEP) - HEP server stress tool in Go.
* [HEP Fidelity Proxy (HFP)](https://github.com/sipcapture/HFP) - Buffered TCP HEP proxy that stores and replays HEP when the collector (HOMER/HEPIC) is unreachable; default listen `:9060`.
* [hep-lineproto](https://github.com/sipcapture/hep-lineproto) - HEP to GigAPI / Influx line-protocol converter.
* [hep-sidekick](https://github.com/sipcapture/hep-sidekick) - HEP sidecar/sidekick for Kubernetes.
* [HEP Wireshark](https://github.com/sipcapture/hep-wireshark) - Lua dissector for HEPv2/v3 over UDP/TCP 9060/9062/9063 and HTTP `application/hep`.
* [HEPgen.js](https://github.com/sipcapture/hepgen.js) - Node.js HEP packet generator for SIP-less devs and unit tests.
* [HEPgen-bash](https://github.com/sipcapture/hepgen-bash) - HEP generator written in bash.
* [HEPipe C](https://github.com/sipcapture/hepipe) - Pipe arbitrary data rows (logs, events, CDRs) to a HEP server (C).
* [hepsim](https://github.com/sipcapture/hepsim) - Simulates phone calls by sending HEP for demos and statistics.


### Network Applications
* [Corelatus](https://www.corelatus.com) - E1/T1 extractions using HEP/EEP. [Example code](https://github.com/matthiasl/Corelatus-GTH-example-code/tree/eep_hec).
* [Cubro](https://www.cubro.com) - Network packet broker (EXA8) packages including HEPlify, HEPAgent, CaptAgent and other HEP/EEP tools. [QXIP EXA8 notes](https://github.com/qxip/EXA8).
* [nDPI](https://github.com/ntop/nDPI) - ntop deep-packet inspection library with HEP/EEP protocol recognition and tagging.
* [nProbe](https://www.ntop.org/products/netflow/nprobe/) - ntop nProbe (VoIP plugin) can act as a HEP capture agent toward HOMER (`--hep host:port`). [Example](https://github.com/sipcapture/homer/wiki/Examples:-nProbe).

### HEPSub Integrations
On-demand session enrichment for HOMER 7+ (not packet encapsulators; they subscribe to the HEP/HOMER API).

* [hepsub](https://github.com/sipcapture/hepsub) - HEP Pub-Sub API example agent.
* [hepsub-apiban](https://github.com/sipcapture/hepsub-apiban) - HOMER/HEPSUB integration for APIban.org.
* [hepsub-cgrates](https://github.com/sipcapture/hepsub-cgrates) - Fetch CDRs from CGRateS.
* [hepsub-elastic](https://github.com/sipcapture/hepsub-elastic) - Fetch correlated logs from Elasticsearch.
* [hepsub-rtpengine](https://github.com/sipcapture/hepsub-rtpengine) - RTPEngine metadata and recordings.
* [hepsub-voipmonitor](https://github.com/sipcapture/hepsub-voipmonitor) - Fetch RTP/CDRs from VoIPmonitor.

### Libraries and Code Examples
* [C](https://github.com/sipcapture/hep-c) / [libhep](https://github.com/sipcapture/libhep)
* [Erlang](https://github.com/sipcapture/hep-erlang)
* [Go](https://github.com/sipcapture/hep-go) — also [go.voiplens.io/hep](https://pkg.go.dev/go.voiplens.io/hep/encoding/binary)
* [Java](https://github.com/sipcapture/hep-java) — also [eep-client](https://github.com/bitinventions/eep-client)
* [Javascript](https://github.com/sipcapture/hep-js)
* [Node-RED](https://github.com/qxip/node-red-contrib-hep)
* [Perl](https://github.com/sipcapture/hep-perl)
* [Python](https://github.com/sipcapture/hep-python)
* [Rust](https://github.com/thevoiceguy/hep-rs)
* [Swift](https://github.com/sipcapture/hep-swift)
