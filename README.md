<picture><source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg"><img alt="Kiran Girishkumar, physical design, RTL to GDSII" src="assets/banner-light.svg" width="100%"></picture>

<p>
<a href="https://kiran-kichu.github.io"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/btn-portfolio-dark.svg"><img alt="Portfolio" src="assets/btn-portfolio-light.svg"></picture></a>
<a href="https://linkedin.com/in/kiran-girishkumar-45157b189"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/btn-linkedin-dark.svg"><img alt="LinkedIn" src="assets/btn-linkedin-light.svg"></picture></a>
<a href="https://kiran-kichu.github.io/resume.pdf"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/btn-resume-dark.svg"><img alt="Resume" src="assets/btn-resume-light.svg"></picture></a>
<a href="mailto:kirangirishkumar543@gmail.com"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/btn-email-dark.svg"><img alt="Email me" src="assets/btn-email-light.svg"></picture></a>
</p>

RTL-to-GDSII physical design with the open-source flow (OpenROAD, OpenLane, OpenSTA) on Sky130, Nangate45 and ASAP7. I like finding out *why* a number comes out the way it does.

> 🔎 **Open to Werkstudent roles, internships and Master's thesis topics in physical design** · Erlangen, Germany

---

## ⚡ Featured: PhyFlow, a timing and IR-drop closure agent

An LLM picks the next fix, OpenSTA / OpenROAD measure it on a copy of the design, and plain Python decides whether it stays.

```text
LLM picks move ─▶ apply to copy ─▶ measure ─▶ hard limits? ─▶ real gain? ─▶ in budget? ─▶ ✅ keep
```

| PicoRV32 @ 3.8 ns | Area to close it | Sparse-PDN IR drop |
|:---:|:---:|:---:|
| **WNS −0.38 → 0 ns** | **+10 µm²** | **78.6 → 15.3 mV** |

<p>
<a href="https://sta-agent-docker.fly.dev/"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/btn-demo-dark.svg"><img alt="Live demo" src="assets/btn-demo-light.svg"></picture></a>
<a href="https://github.com/kiran-kichu/sta-timing-agent"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/btn-code-dark.svg"><img alt="Code" src="assets/btn-code-light.svg"></picture></a>
</p>

---

## 🧱 Projects

<p>
<a href="https://github.com/kiran-kichu/picorv32-physical-design"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/card-picorv32-dark.svg"><img alt="PicoRV32 RISC-V: 238 MHz on Sky130" src="assets/card-picorv32-light.svg" width="49%"></picture></a>
<a href="https://github.com/kiran-kichu/systolic-array-ai-accelerator"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/card-systolic-dark.svg"><img alt="8x8 systolic-array MAC: 625 MHz on Nangate45" src="assets/card-systolic-light.svg" width="49%"></picture></a>
<a href="https://github.com/kiran-kichu/soc-pdn-sky130"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/card-soc-dark.svg"><img alt="Hierarchical SoC and power grid: 11 µV worst IR drop" src="assets/card-soc-light.svg" width="49%"></picture></a>
<a href="https://github.com/kiran-kichu/ibex-mcmm-asap7"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/card-ibex-dark.svg"><img alt="Ibex multi-corner sign-off on ASAP7" src="assets/card-ibex-light.svg" width="49%"></picture></a>
</p>

<picture><source media="(prefers-color-scheme: dark)" srcset="assets/systolic-dark.svg"><img alt="Animated 8x8 systolic array" src="assets/systolic-light.svg" width="440"></picture>

---

## 🔬 One experiment, three power grids

<picture><source media="(prefers-color-scheme: dark)" srcset="assets/irdrop-dark.svg"><img alt="IR drop: sparse grid 78.6 mV, default 33.7 mV, wider straps 15.3 mV" src="assets/irdrop-light.svg" width="100%"></picture>

---

## 📝 Things I learned the hard way

<details>
<summary><b>Reported fmax is a guess</b></summary>
<br>
The critical path moves as the clock tightens. On PicoRV32 it shrank 29.5% once the constraint forced faster adders and upsizing. Sweep and see what closes.
</details>

<details>
<summary><b>Decap doesn't help static IR drop</b></summary>
<br>
A capacitor is invisible to DC analysis. The apparent gain came from removed filler cells; only wider or denser straps moved the worst case.
</details>

<details>
<summary><b>Put limits between the steps, not on them</b></summary>
<br>
A 6.0 µm² per-move cap sat just under Sky130's 6.26 µm² upsize step and silently blocked good fixes. 7.0 µm² fixed it.
</details>

---

## 🛠️ Tools

`OpenROAD` · `ORFS` · `OpenLane` · `OpenSTA` · `Yosys` · `Magic` · `KLayout` · `Verilog` · `Tcl` · `Python` · `Docker`

<sub>Currently: making PhyFlow's power agent work on any uploaded design · learning German (A1)</sub>
