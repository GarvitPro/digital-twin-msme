UI Wireframes (ASCII) — Digital Twin Platform for MSMEs
Note: These are conceptual wireframes for presentation/demo only. They illustrate layout and user flow, not visual styling.

1) Dashboard (KPIs + Alerts + Live Feed)
+--------------------------------------------------------------------------------------+
| Digital Twin Platform — Dashboard |
+----------------------+------------------------+-----------------------+---------------+
| Uptime | OEE | Active Alerts | Energy Usage |
| 97.8% | 78.3% | 3 | 1,240 kWh |
+----------------------+------------------------+-----------------------+---------------+
| Production Overview |
| [ Line A ] [■■■■■■■■■■■■■■■■■----] 82% | Throughput: 540/hr | Defects: 1.2% |
| [ Line B ] [■■■■■■■■■■■----------] 55% | Throughput: 310/hr | Defects: 2.0% |
+--------------------------------------------------------------------------------------+
| Alerts |
| 1) Motor M-01 vibration above threshold (0.09g > 0.08g) — Prior: High — Ack: [ ] |
| 2) Temp spike on Dryer D-02 (88°C > 85°C) — Prior: Medium — Ack: [x] |
| 3) Sensor S-12 battery low (14%) — Prior: Low — Ack: [ ] |
+--------------------------------------------------------------------------------------+
| Live Sensor Feed (last 5 min) |
| Time Machine Temp(°C) Vib(g) Status |
| 10:01:05 M-01 72.4 0.07 OK |
| 10:01:10 M-01 72.6 0.09 WARN |
| 10:01:15 D-02 88.0 - WARN |
| 10:01:20 S-12 - - LOW BATT |
+--------------------------------------------------------------------------------------+
| [View Twins] [Predict Failures] [Optimize Schedule] [Export Report] |
+--------------------------------------------------------------------------------------+

Legend:

OEE: Overall Equipment Effectiveness

Bars are conceptual utilization indicators

“Ack” denotes alert acknowledgement

2) Digital Twin List (Inventory)
+---------------------------------------------------+
| Digital Twins |
+------+------------+------------+---------+---------+
| ID | Name | Asset Type | Health | Status |
+------+------------+------------+---------+---------+
| T01 | Line A | Assembly | Good | Active |
| T02 | Line B | Assembly | Fair | Active |
| T03 | M-01 | Motor | Warn | Active |
| T04 | D-02 | Dryer | Warn | Active |
| T05 | S-12 | Sensor | Good | Inact. |
+------+------------+------------+---------+---------+
| [Create Twin] [Edit] [Open] [Archive] |
+---------------------------------------------------+

3) Drag-and-Drop Twin Builder
+--------------------------------------------------------------------------------------+
| Digital Twin Builder |
+---------------------------+----------------------------------------------------------+
| Component Library | Canvas: Line A |
| | |
| [Motor] [Conveyor] | +-------------------+ +-----------------------+ |
| [Pump] [Dryer] | | MOTOR M-01 |---->| CONVEYOR C-02 | |
| [Sensor] [PLC] | +-------------------+ +-----------------------+ |
| [Gateway] [Node] | | | |
| | [Sensor S-12] [Sensor S-14] |
| | (Vib/Temp) (Speed) |
| | |
+---------------------------+----------------------------------------------------------+
| Properties Panel | Selected: MOTOR M-01 |
| Name: M-01 Thresholds: Vib 0.08g, Temp 85°C |
| Tags: motor, critical Maintenance: every 500 hours |
| Data Binding: sensor S-12 Predictive: model_v1 (RUL forecast) |
+--------------------------------------------------------------------------------------+
| [Add Component] [Connect] [Validate] [Save Twin] [Simulate] |
+--------------------------------------------------------------------------------------+

4) Predictive Simulation Setup
+--------------------------------------------------------------+
| Predictive Simulation |
+---------------------------+----------------------------------+
| Scenario Parameters | Output (Preview) |
| Horizon: 7 days | Failure Probability: 18% |
| Shift Plan: 3x8 | Predicted RUL (M-01): 220 hours |
| Load: High | Energy Cost: +6% |
| Maintenance: deferred | Throughput Impact: -3% |
+---------------------------+----------------------------------+
| [Run Simulation] [Compare Scenarios] [Export Results] |
+--------------------------------------------------------------+

5) Settings — Data Sources
+--------------------------------------------------------------+
| Data Sources |
+----------------------------+---------------------------------+
| Name Type Status | Details |
| mqtt-01 MQTT Active | broker: iot.local:1883 |
| edge-01 Gateway Active | site: Plant-1 |
| csv-01 Batch Idle | path: /uploads/sensors.csv |
+----------------------------+---------------------------------+
| [Add Source] [Test] [Edit] [Remove] |
+--------------------------------------------------------------+

End of wireframes.
3) How to design ASCII wireframes quickly
Use monospaced font: Ensure alignment in your editor (VS Code, GitHub renders Markdown monospaced in code blocks).

Keep it boxy: Use +, -, | to make containers; use [Label] for buttons; use tables for lists.

Use simple icons: [x]/[ ] for toggles, ■ bars for utilization, WARN/OK flags for status.

Limit width: Aim for ~100 characters per line so it fits well on GitHub.

Group by sections: Dashboard, Twin List, Builder, Simulation, Settings—each in its own code block.

4) Optional: Add Markdown code fences for clean rendering
Wrap each wireframe in triple backticks with no language for best alignment:

text
+------------------+
|   Example Box    |
+------------------+
5) Versioning tips
Start with v0.1 wireframes.

Add a “Changelog” at the end:

v0.2: Added Predictive Simulation panel

v0.3: Added Data Sources table
