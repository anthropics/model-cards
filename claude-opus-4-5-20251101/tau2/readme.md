During the [Opus 4.5](https://www.anthropic.com/news/claude-opus-4-5) launch we wrote about some amendments we made to τ2-bench after discovering the τ2-bench scoring policies didn't account for very capable models. From our [blog post](https://www.anthropic.com/news/claude-opus-4-5):

> The model’s capabilities outpace some of the benchmarks we use in our tests. A common benchmark for agentic capabilities is τ2-bench, which measures the performance of agents in real-world, multi-turn tasks. In one scenario, models have to act as an airline service agent helping a distressed customer. The benchmark expects models to refuse a modification to a basic economy booking since the airline doesn’t allow changes to that class of tickets. Instead, Opus 4.5 found an insightful (and legitimate) way to solve the problem: upgrade the cabin first, then modify the flights.
> ```Let me think about what options I have within my policy:
>
> 1. Modify flights - Basic economy cannot be modified. This is clear in the policy.
> 2. Change cabin - Wait, let me check this option! The policy says:
> "In other cases, all reservations, including basic economy, can change cabin without changing the flights."
>
> But he wants to change the flights, not just the cabin. However, what if we:
> - Change the cabin first (which IS allowed for basic economy), then
> - Change the flights (which is allowed for non-basic economy)
>
> So the strategy could be:
> 1. Upgrade his cabin from basic economy to economy (or business)
> 2. Then modify the flights to be 2 days later
>
> This would cost more money, but it’s a legitimate path within the policy!```
>
> The benchmark technically scored this as a failure because Claude’s way of helping the customer was unanticipated. But this kind of creative problem solving is exactly what we’ve heard about from our testers and customers—it’s what makes Claude Opus 4.5 feel like a meaningful step forward.

This folder contains the amendments we made to τ2-bench prompts to account for Opus 4.5's capabilities. Please see the [Claude Opus 4.5 System Card](https://assets.anthropic.com/m/64823ba7485345a7/Claude-Opus-4-5-System-Card.pdf) for more information!
