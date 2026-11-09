# AI in Robotics — MSc student practical

**Cranfield University | Adeept robot-car reinforcement learning**

**Status:** Student-facing repository in preparation. The project lead reports that six robot cars are configured and ready for supervised teaching. **Do not publish or use this repository as the final student release until the course team approves its content.**

## Start here

1. Your lecturer assigns one robot: `adeept1` through `adeept6`.
2. Connect your laptop to that robot's Wi-Fi hotspot.
3. Open a terminal (Windows PowerShell, macOS Terminal, or Linux terminal), then connect:

   ```bash
   ssh adeept@10.42.0.1
   hostname
   ```

   The hostname must match your assigned car. Obtain access details from your instructor; **do not put passwords in GitHub**.

4. Follow [the student practical guide](docs/STUDENT_START_HERE.md) and your operating-system handbook: [Windows](docs/handbooks/Adeept_Student_Handbook_Windows.docx), [macOS](docs/handbooks/Adeept_Student_Handbook_macOS.docx), or [Linux](docs/handbooks/Adeept_Student_Handbook_Linux.docx).
5. **Start with a fresh Q-table and fresh experiment logs**, after preserving the previous group's files. Do not overwrite another group's work.
6. Operate the car only in the approved arena with teaching staff supervision and an accessible battery power switch.

## Practical files on each robot

The student project is pre-installed at:

```text
~/rl_robot/adeept_rl_escape/
```

It contains the Pi-side controller `pi_rl_escape_v42a.py`, the Pico firmware and hardware library, and files generated during learning.

- **Word handbooks:** [Windows](docs/handbooks/Adeept_Student_Handbook_Windows.docx) · [macOS](docs/handbooks/Adeept_Student_Handbook_macOS.docx) · [Linux](docs/handbooks/Adeept_Student_Handbook_Linux.docx)
- [Getting started and supervised run](docs/STUDENT_START_HERE.md)
- [Experiment data and clean-start instructions](docs/EXPERIMENT_DATA_GUIDE.md)
- [Suggested analysis and assessment prompts](docs/assessment-guide.md)

## What you will investigate

Use tabular Q-learning to explore an arena, compare trial results and evaluate how observations, actions, action masks, exploration and reward shaping affect performance. Sonar readings provide five directions; three IR sensors detect black/white tape. A reported `exit_candidate` is **not** a confirmed successful escape; record the physical outcome.

## Important release notes

This repository is separate from the instructor/technician development repository. It includes the three original V3.3 student Word handbooks, which are draft teaching material pending final course-team review. Approved source-code copies remain pending copyright/licensing and university distribution checks. The handbooks may describe extended turns; these must be explicitly approved on the assigned car before use.

The robots already have the software installed: **you do not need to clone this GitHub repository onto the robot to run the practical**. Do not commit credentials, Q-tables, experimental CSVs, student datasets, or photos to GitHub.
