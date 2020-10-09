# Discussions

- Building a competitive full self-play RL is probably not realistic even with free Kaggle notebooks and the `$1000` Google cloud compute credits. It might be possible to use RL in a smarter way. For example, first training a policy to reproduce the behavior of a top player before improving that policy with self-play RL.
- Anything you print to stdout or stderr will appear in the logs.
- You are given a list of the opponent positions, as well as their velocities from the last step. You can add each velocity to the corresponding player to estimate that if they continued on course then you could find where they end up.
- There are a few ways that you can return actions. You can just plainly return an integer from `0` to `18` which results in the corresponding action, or you could do it in an even easier way. If you add the `@human_readable_agent` decorator over you `def agent(obs):` line, that will transfer data in a way that can be readable by humans. Actions will then be transferred to `Action` objects, so you can do things like return `Action.Top`, `Action.Shot`, `Action.Sprint`, etc.
