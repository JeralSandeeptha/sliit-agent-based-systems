# Makrov Models

## Markov Processes

At the heart of these models is the `Markov Property`, often summarized as `the future is independent of the past but only with the present`.

$$P(X_{t+1} = s_j \mid X_t = s_i, X_{t-1} = s_{k}, \dots) = P(X_{t+1} = s_j \mid X_t = s_i)$$

<br/>

## Makrov Models Types

1. [Markov Chains (Visible Markov Models)](./vmms.md)

2. [Hidden Markov Models (HMMs)](./hmms.md)
