This contains a set of configurations to rank candidates when building a
recommended feed. For illustrative purposes we have chosen a video recommendation system.
The approach here should work for otehr domains where the user action labels of 
consumption, skipping and exit are available.

- [reward_maximizing.json](./reward_maximizing.json) ranks, i.e. sorts, items by the reward which is the probability of watching the video.
- [nonskip_conditional.json](./nonskip_conditional.json) changes this to P(watch) * (1 - P(skip))
- [inverse_skip](./inverse_skip_conditional.json) illustrates the the reward/risk advice of [this blog](https://recsysml.substack.com/p/how-to-account-for-risk-in-recommended) and ranks by ~ P(watch)/P(skip)
- [inverse_exit](./inverse_exit_conditional.json) is similar to inverse skip but uses P(exit) instead of P(skip)
- [separate_top_position](./separate_top_position_inverse_exit_conditional.json) assumes that the recommender system has two ranking calls, one that explicitly chooses the top position and another call used for all other positions. This sort of a separation can be useful to your system when there is a high drop off of users from top position to the next.