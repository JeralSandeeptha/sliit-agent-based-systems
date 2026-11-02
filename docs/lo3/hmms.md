# Hidden Markov Models (HMMs)

Real-world problems are rarely so transparent. Often, the true underlying state of a system is hidden from us, but we can observe `outward signals or symptoms that depend on that hidden state`. This is a `Hidden Markov Model (HMM)`.

![Image](../../images/hmm-03.png)

<br/>

The Two Hierarchies of HMMs:

1. `The Hidden Process`: A Markov chain of unobserved (hidden) states $Z_1, Z_2, \dots, Z_T$.

2. `The Observation Process`: At each time step, the hidden state emits an observable output $O_t$ based on a probability distribution.

<br/>

**Core Parameters of an HMM**

$A$ `(Transition Probabilities)`: Probability of moving between hidden states $P(Z_t \mid Z_{t-1})$.

$B$ `(Emission Probabilities)`: Probability of observing output $v_k$ given that the system is in hidden state $s_j$: $B_{jk} = P(O_t = v_k \mid Z_t = s_j)$.

$\pi$ `(Initial State Distribution)`: Starting probabilities for the hidden states.

<br/>

## The Three Fundamental Problems of HMMs

When working with HMMs in machine learning, you typically solve three core algorithmic problems:

| Problem | Goal | Standard Algorithm |
| :--- | :--- | :--- |
| **1. Evaluation** | Compute the probability of a specific observation sequence given the model parameters. | **Forward-Backward Algorithm** |
| **2. Decoding** | Find the most likely sequence of *hidden* states that led to a given observation sequence. | **Viterbi Algorithm** |
| **3. Learning** | Adjust the model parameters ($A, B$) to best fit a set of observed training sequences. | **Baum-Welch Algorithm** (Expectation-Maximization) |

<br/>

**Example: The Doctor and the Patient**

Imagine trying to deduce whether a friend has a Fever or is Healthy (Hidden States), but you can only observe whether they feel Normal, Dizzy, or Cold (Observations) when they visit you. The underlying state drives the symptoms, but you only see the symptoms.

![Image](../../images/hmm-01.jpeg)

<br/>

**Initial State Distribution ($\pi$)**
The probability of how the friend's health starts on Day 0:$$\pi = \begin{bmatrix} P(H) & P(F) \end{bmatrix} = \begin{bmatrix} 0.6 & 0.4 \end{bmatrix}$$

**Transition Probability Matrix ($A$)**

The probability of moving between hidden states:$$A = \begin{pmatrix} P(H \to H) & P(H \to F) \\ P(F \to H) & P(F \to F) \end{pmatrix} = \begin{pmatrix} 0.8 & 0.2 \\ 0.1 & 0.9 \end{pmatrix}$$

**Emission Probability Matrix ($B$)**

The probability of observing a symptom given a hidden state (Rows = Hidden States, Columns = Observations $[N, D, C]$):$$B = \begin{pmatrix} P(N \mid H) & P(D \mid H) & P(C \mid H) \\ P(N \mid F) & P(D \mid F) & P(C \mid F) \end{pmatrix} = \begin{pmatrix} 0.9 & 0.1 & 0.0 \\ 0.2 & 0.5 & 0.3 \end{pmatrix}$$

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

**Example: Mood depends on Weather**

![Image](../../images/hmm-01.png)

```
HMM = Hidden Markov Chains + Observable Variables
```

![Image](../../images/hmm-02.png)
