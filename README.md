# Detection Engineering MCP Server

A Model Context Protocol (MCP) server that gives Claude integrated detection 
engineering capabilities — log analysis, threat intelligence processing, and 
detection rule management — built as the capstone project for the AI Cyber 
Defense Ops program (WiCyS / Just Hacking Training). Certificate issued July 2026.

![Purple Team Pipeline](./image/pipeline-diagram.png)

## What It Does

The platform turns threat intelligence into testable, measurable detection 
coverage. It combines:

- **MCP server architecture** — FastMCP-based server exposing 6+ tools and 5+ 
  resource types to Claude
- **Detection knowledge base** — 20+ production Sigma rules mapped to 50+ 
  MITRE ATT&CK techniques
- **Threat intelligence pipeline** — automated extraction of TTPs, IOCs, and 
  simulation plans from threat reports (`/ingest-ti`)
- **Multi-source investigation** — correlates Sysmon and Windows Security logs 
  with Splunk (`/query`, `/hunt`)
- **Coverage analysis** — quantifies detection gaps and validates rule coverage 
  against real attack scenarios
- **Purple team integration** — runs and analyzes Atomic Red Team tests against 
  the detection rules

## Purple Team Validation (July 2026)

Ran a full end-to-end purple team loop against a real threat campaign 
(Huntress report — ClickFix + Matanbuchus 3.0 + AstarionRAT):

1. **Ingested threat intel** — extracted 10+ techniques across Discovery, 
   Execution, Persistence, and C2 tactics
2. **Executed atomic tests** for T1082 (System Information Discovery) and 
   T1069.002 (Domain Groups Discovery)
3. **Scanned with Hayabusa** — 46,900+ EVTX detections across Security and
