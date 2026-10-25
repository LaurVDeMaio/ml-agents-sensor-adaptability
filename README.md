# Unity ML-Agents Sensor Adaptability

Unity project for comparing how four ML-Agents sensor types (raycast, camera, grid, and buffer) handle environment changes after training.

An agent is trained with PPO to catch a scripted player before it reaches a goal, in an arena with one obstacle. Each trained agent is then tested with 1 to 5 obstacles to see how well it adapts to layouts it never saw during training. In our tests, the raycast agent held up best as obstacles were added, and the buffer agent degraded the most.

This work was presented at EXAG 2026 (AIIDE Workshop on Experimental AI in Games).

## What's included

- `Assets/Scenes/`: one scene per sensor
- `Assets/Scripts/`: agent, scripted player, and stats scripts
- `Assets/*.onnx`: the trained model for each sensor
- `config/`: PPO training configs
- `data/`: evaluation results and inference timing logs

## Running it

Built with Unity 6000.0.62f1 and ML-Agents 4.0.2.

To test a trained model, open a scene, set **Obs Count** on the agent to the number of obstacles you want, and press Play.

To retrain, run `mlagents-learn config/<sensor>.yaml --run-id=<name>` and press Play in Unity when prompted.
