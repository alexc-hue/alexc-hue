## Hi, I'm Alex

Project controls and technical PM professional (PMP®-certified) working across
industrial and OT/IT delivery programmes. My core discipline is project controls,
EVM, CPM scheduling, risk management, and change control, and I build the software
that operationalizes it: methodologies that are usually run by hand in a
spreadsheet, turned into repeatable, automated tools.

These methods reflect real project-controls practice: recovered a programme
from four months behind schedule to three weeks late, an 85%+ recovery,
using the same EVM/CPM discipline this toolkit automates.

**Background:** project controls and technical PM roles across engineering,
industrial automation, and OT/IT delivery, including plant and
process scripting (VBScript, Structured Text, FBD).

### Project Controls Toolkit

Six practical tools that operationalize core project-controls disciplines
as software, each reading from CSVs and producing charts plus a saved
report. All six also share one fixed status color convention (good,
warning, serious, critical) and chart style, the same single RAG standard a
project controls function would enforce across a programme, not six
different ad-hoc looks:

**Integration**
- [project-controls-reporting-engine](https://github.com/alexc-hue/project-controls-reporting-engine):
  composes four of the tools below (schedule, EVM, risk, change) against
  one consistent programme into a single integrated status report, no new
  logic, just the four disciplines' findings shown side by side.

**Schedule Integrity**
- [schedule-health-analyzer](https://github.com/alexc-hue/schedule-health-analyzer):
  Critical Path Method, baseline vs current schedule, float erosion, and a
  Schedule Health Score.

**Decision Support**
- [recovery-scenario-planner](https://github.com/alexc-hue/recovery-scenario-planner):
  models and ranks recovery interventions (add resources, re-sequence,
  accept delay) against a programme's schedule/cost/risk status, the
  toolkit's decision layer: the other five tools report a status, this one
  recommends what to do about it.

**Portfolio Reporting**
- [project-controls-dashboard](https://github.com/alexc-hue/project-controls-dashboard):
  EVM (SPI/CPI/EAC/ETC/VAC), milestone tracking, risk register, and change
  register, in one status report.

**Risk & Change**
- [risk-trend-tracker](https://github.com/alexc-hue/risk-trend-tracker):
  risk register tracked over time: exposure trend, per-risk trajectory,
  and mitigation effectiveness.
- [change-control-register](https://github.com/alexc-hue/change-control-register):
  cumulative budget/schedule creep from approved changes, decision cycle
  time, stale pending changes flagged.

A note on the code itself: project-controls-reporting-engine and
recovery-scenario-planner don't import the other four tools' logic, they
vendor it, copies of the EVM, CPM, and risk-scoring modules. That's a
deliberate convention, not copy-paste sloppiness: every repo in this toolkit
needs to stand alone and be cloneable on its own. Each copy records the
source commit it came from, and CI checks both that nobody has edited the
copy and that the source hasn't moved on without it.

### Applied: data center practice models (synthetic data)

Two separate repos that apply the same methods to data center delivery.
Everything in them is made up; they are practice models, not a record of
real data center work.

- [commissioning-readiness-gate](https://github.com/alexc-hue/commissioning-readiness-gate):
  per data hall, a ready / conditional / not-ready verdict with reasons for
  starting the next commissioning level (L1 to L5, strict sequencing),
  from the punch list, a design-load vs provisioned power and cooling
  check, and assets read from NetBox.
- [facility-status-digital-twin](https://github.com/alexc-hue/facility-status-digital-twin):
  CPM schedule status placed on a facility layout, built on the toolkit's
  CPM and EVM engines: one OpenUSD block per activity, colored by status.
  The facility is a grid of placeholder blocks, not a real data hall.

### How the repos are kept honest

The sample output in each README is tested against what the code actually
prints, so the numbers can't drift out of date. Where code review found a
bug in the calculations or the report, there's a regression test for it,
checked to fail without the fix. Every repo is versioned, with a changelog
saying what changed in each release. Same thing I'd expect from a controls
function: a baseline, a change record, and numbers you can trace back to
where they came from.

### Tools I work with

Project controls methods (EVM, CPM, schedule and risk analysis),
operationalized in Python (pandas, matplotlib) and Excel. Also comfortable
in MATLAB.

### Beyond the toolkit

A few fixes outside this toolkit too, merged into other people's codebases:
documentation and example corrections in NVIDIA's OpenUSD learning
repository, one of which grew to cover every affected lesson after the
maintainer asked for the rest; a Huawei server spec correction in NetBox's
device-type library, checked against the manufacturer's datasheet; a crash
in LibreNMS, the network monitoring platform, when an APC UPS reported a
malformed date, fixed with a regression test; and a phpIPAM API endpoint
that returned an empty 500 error, traced to its root cause. Same habit as
the toolkit above: check the record against the source of truth, fix
what's wrong.

### Elsewhere

[LinkedIn](https://www.linkedin.com/in/alexandru-nicolau-pmp%C2%AE-b64274165/)
