# Blogs


## Introducing Google Research Football: A Novel Reinforcement Learning Environment

_Source: https://ai.googleblog.com/2019/06/introducing-google-research-football.html_

The Football Environment provides several crucial components:
1. A highly-optimized game engine.
2. A demanding set of research problems called Football Benchmarks.
3. Football Academy, a set of progressively harder RL scenarios.

Football Engine
- Written in highly optimized C++ code. Runs on off-the-shelf machines with/without GPU. `25 million steps per day` on a single hexa-core machine.
- Learning from both different state representations as well as learning from raw pixels.
- Can be run in both a stochastic mode in which there is randomness and in a deterministic mode, where there is no randomness.
- Compatible with the widely used OpenAI Gym API.

Football Benchmarks
- A fixed rule-based opponent that was hand-engineered for this purpose. Easy, Medium and Hard Benchmark.
- Benchmark results for two state-of-the-art reinforcement learning algorithms: `DQN` and `IMPALA`.
- Rewards provided to the algorithm are the goals scored and provide additional rewards for moving the ball closer to the goal.

Football Academy
- A diverse set of scenarios of varying difficulty.
- Using a simple API, researchers can further define their own scenarios and train agents to solve them.
