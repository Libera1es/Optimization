# 1. Direct Attack  

## Non-Linear Flow Eq  

Consider household consumes $c_t$ and produces $c$ w/ inputs $k_t - c_t$.  
And the production func is $f$ (strictly concave).  

$$k_{t+1} = f(k_t - c_t, \theta)$$  
where $\theta$ is time-invariant technology param.  

# 2. Dynamic Programming  

**The idea of DP:** Not solve a complex optimization problem that considers all $T$ periods all at once, but optimize one period at a time.  

Consider the cake-eating problem:  
we know the value of any capital becomes zero in the final period, so
$$V_{T+1}(k_{T+1})=0$$
This enables us to **backward induction**. In period $T$, solve
$$V_T(k_T) = \max_{c_T\in (0,k_{T}]}\{u(c_T)+\beta V_{T+1}(k_{T+1})\}$$
where $k_{T+1} = k_T - c_T$.  This can be solved for any $k_t$. This solution provides the total value when a household consumes an amount $k_T$ during period $T$.  
This allows us to consider the decision in period $T-1$:
$$V_{T-1}(k_{T-1}) = \max_{c_{T-1}\in (0,k_{T-1}]}\{u(c_{T-1})+\beta V_{T}(k_{T})\}$$  
Solve until reaching $V_1(k_1)$ is called Backward induction.  

# 3. Momoization  

The precision of optimization depends on the fineness of the search grid. The finer imposes more computation cost(**Curse of Dimensionality**).  

**Memoization** is 

# 4. Stochastic DP  

$$k_{t+1} = \theta(k_t-c_t)^\alpha + \epsilon_{t+1}$$  

The dicision maker know the distribution of $\epsilon$.  
Then, the value function is:  
$$V_t(k_t) = \max_{c_t\in(0,k_t]}\{u(c_t) + \beta \mathbb{E}[V_{t+1}(k_{t+1})]\}$$  

Here, we assume the simple distribution:  low($\epsilon=-2$) and high($\epsilon=2$) states, and each state occur w/ probability of 0.5.  
