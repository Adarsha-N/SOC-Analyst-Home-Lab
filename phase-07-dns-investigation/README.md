# Phase 7 — DNS Investigation

## Objective

Investigate DNS traffic and identify anomalous DNS query behavior using
TShark packet capture and analysis.

## Environment

- Ubuntu Server: 10.10.20.10
- Ubuntu Internet interface: ens33
- Ubuntu Internet IP: 10.16.9.138
- SOC interface: ens37
- DNS resolver: 127.0.0.53
- Packet analysis tool: TShark 4.6.4

## 1. DNS Baseline

Normal DNS queries were generated for:

- example.com
- example.org

The baseline capture demonstrated normal A and AAAA DNS queries
and successful DNS responses.

Baseline capture:

`captures/phase7-dns-baseline.pcap`

## 2. Controlled Suspicious DNS Simulation

A controlled DNS anomaly was generated using the reserved `.invalid`
domain.

Ten unique random-looking subdomains were queried:

- x02f871a50184.test.invalid
- x0ae891533ae9.test.invalid
- x0f2325f15fff.test.invalid
- x39bbc2f67881.test.invalid
- x455eba599915.test.invalid
- x816a33d49dec.test.invalid
- x94bb0f1ab5ab.test.invalid
- xae49840e245f.test.invalid
- xd458eb7cce54.test.invalid
- xe07e1c820ad3.test.invalid

The queries were intentionally generated inside the lab and did not
use a real malicious domain.

Suspicious capture:

`captures/phase7-dns-suspicious.pcap`

## 3. Detection

The suspicious DNS traffic was identified by filtering:

`dns && dns.qry.name contains test.invalid`

Unique query count:

10

The queries showed random-looking subdomain labels and repeated
unique DNS requests over a short period.

## 4. SOC Analysis

### Indicators

- Multiple unique DNS queries
- Random/high-entropy-looking subdomain labels
- Repeated queries within a short period
- Non-existent `.invalid` domain
- Significant deviation from the established baseline

### Assessment

The activity is classified as:

**Suspicious DNS behavior — Controlled Lab Simulation**

This activity alone is not sufficient to confirm malware or DNS
tunneling.

In a real SOC investigation, additional correlation would be required,
including:

- Endpoint/process information
- User identity
- DNS history
- Query frequency
- Destination reputation
- Network flow information
- Endpoint security alerts

## 5. Evidence

### Baseline

`captures/phase7-dns-baseline.pcap`

### Suspicious Activity

`captures/phase7-dns-suspicious.pcap`

### Screenshots

- `screenshots/dns-baseline-analysis.png`
- `screenshots/dns-suspicious-analysis.png`

## 6. Conclusion

The investigation established a normal DNS baseline and demonstrated
how repeated unique and random-looking DNS queries can be identified
as anomalous using packet capture analysis.

The suspicious traffic was safely simulated using `.invalid` domains
within the isolated lab environment.