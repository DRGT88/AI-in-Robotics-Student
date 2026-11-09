# Experiment data and starting from an empty Q-table

The RL controller stores its results under `~/rl_robot/adeept_rl_escape`:

- `escape_qtable_v42a.json` — persistent learned Q-values, reused across runs
- `escape_steps_v42a.csv` — per-step readings, actions, states and rewards
- `escape_training_v42a.csv` — episode-level summary, if generated

## Before your group's first episode

**Ask your instructor before resetting:** another group's data may be on the robot. With the robot controller stopped, execute:

```bash
cd ~/rl_robot/adeept_rl_escape
mkdir -p commissioning_backup
```

Archive existing files using your instructor's group/session naming procedure. The following example stores copies in a time-stamped local folder, rather than deleting them:

```bash
backup="commissioning_backup/previous_$(date +%Y%m%d_%H%M%S)"
mkdir -p "$backup"
for file in escape_qtable_v42a.json escape_steps_v42a.csv escape_training_v42a.csv; do
    if [ -f "$file" ]; then mv "$file" "$backup/"; fi
done
printf '{}\n' > escape_qtable_v42a.json
cat escape_qtable_v42a.json
```

The final output must be `{}`. This starts Q-learning with an empty table; the controller will generate fresh CSV files when training. Confirm the Pi clock has been corrected before starting, otherwise the backup folder and CSV timestamps may be wrong.

**Do not reset between training episodes** if your intention is to test continuing learning. Save a labelled copy of the Q-table and logs before changing experimental conditions or running an independent trial.

## Comparisons and evidence

Record robot hostname, code version, trial settings, starting position, arena geometry, action availability, episodes, epsilon, reward and physically verified outcome. Distinguish complete escapes, partial exits, unconfirmed tape candidates, timeouts and communication/sensor errors. A few short episodes show the workflow, but do not establish a robust learned policy.

Do not upload student results, Q-tables, identifying data or camera images to this repository.
