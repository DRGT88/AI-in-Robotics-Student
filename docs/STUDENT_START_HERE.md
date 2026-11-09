# Student quick start — Adeept arena escape

> Instructor-supervised physical robot practical. Check the assigned robot and arena with staff before enabling its motor supply.

## 1. Connect to your assigned car

Connect to its named Wi-Fi hotspot (`adeept1`–`adeept6`), then in PowerShell / Terminal:

```bash
ssh adeept@10.42.0.1
hostname
```

The hostname must show your assigned car. Ask the teaching team for the credentials. Each car uses the same hotspot-local IP address; **connect to only your assigned robot**.

## 2. Activate the project

```bash
cd ~/rl_robot/adeept_rl_escape
source ~/rl_robot/venv/bin/activate
python pi_rl_escape_v42a.py --mode selftest
```

The self-test verifies software action and state logic; it does **not** move the motors.

## 3. Prepare a fresh experiment

With no robot controller running, follow [the clean-start procedure](EXPERIMENT_DATA_GUIDE.md). Check `escape_qtable_v42a.json` displays `{}` and archive prior logs.

## 4. Run a supervised first trial

Place the robot in the approved arena, verify initial clearance (including behind the robot), check the battery switch can be reached, and await your instructor.

```bash
python pi_rl_escape_v42a.py --mode train --episodes 1 --steps 10
```

Follow the on-screen prompts and record the **physical outcome** when asked.

For additional trials, your instructor may specify different parameters:

```bash
python pi_rl_escape_v42a.py --help
```

Actions 7 and 8 require `--enable-extended-turns`; **do not enable them unless the teaching team has explicitly commissioned and approved these moves on your assigned car**.

## 5. Analyse your results

Check the generated `escape_steps_v42a.csv`, `escape_training_v42a.csv` (if produced) and `escape_qtable_v42a.json`. A new training command normally **continues the current Q-table**, rather than resetting it. Compare outcomes, total reward, individual actions and repeated trials.

A positive software exit candidate is not necessarily a human-confirmed escape.

## Safe use and troubleshooting

- Keep hands clear of moving wheels, steering and pinch points.
- If motion is unexpected, switch off the **car motor battery power**. Ctrl+C and serial stop commands are not guaranteed emergency stops.
- Never run the car unattended or outside the approved arena.
- Stop and notify staff about USB disconnections, overcurrent warnings, loss of sensor validity or runaway movement.
- Robot clocks may be incorrect after boot when offline; confirm timestamp accuracy with staff before collecting experimental data.
- Do not update Pico firmware, motor wiring or the teaching software without instructor approval.
