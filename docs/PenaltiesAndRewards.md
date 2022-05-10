# Penalties and Rewards

Razor network has carefully designed ensuring that all the honest stakers get rewarded and malicous nodes get penalised. In order to prevent 51% takeover attack, the stakers with 51% of infulence are deincetivised heavily.

## Influence, Reputation And Maturity {#influence-reputation-and-maturity}

Razor network measures the reputation of every staker based on different factors like Stake. Whenver any staker performs stake action, it gets its reputation increased and vice versa.

        Reputation = Minimum(Log(m+s),Rc);

        Here, m is the maturity and s is the smoothing factor(to prevent high rate of growth) And Rc is the upper limit of Reputation.

With Reputation and staker's stake, Infulence of Staker is calculated.

        Influence = Reputation * Stake

## Penalties {#penalties}

### Penalty for Wrong Block Proposed {#penalty-for-wrong-block-proposed}

If staker tries to propose an invalid block, then any staker can dispute on that by calculating the correct values. We assume that each staker uses the same client and data without any modifications. hence if there is any malicious activity done, staker's stake will be slashed. The part of staker's stake will be burnt and remaining will be sent to disputer.

### Voting Penalites {#voting-penalites}

If any staker, does not participate in epoch and do not provide the commit, then she will get its influence reduced by 1%. And if she commits and do not reveal then there will be signigicant amount of penality on influence.

### Inactivity Penalty {#inactivity-penalty}

Considering technical issues, we have kept a Grace Period for inactivity. If by any chance staker is not able to participate in the network for epochs less then Grace Period, we do not give any Inactivity Penalties.

## Rewards {#rewards}

For every participation in each epoch, staker will be incentivised with increase in the influence of its on network. It is also known as Voting Rewards

If there is malicious block being created, the disputer will get some percentage of the slashed stake of the staker as a reward.

### Block Reward {#block-reward}

A block Reward will be awarded to stakers if all the given conditions satisfy.

1. Staker proposes a valid block in Propose state
2. Staker has highest priority for becoming the block producer for epoch.
3. No one has proven block as malicious block.
4. Staker confirms the block and submits to client.

The block Reward will be given in the 5th State , Confirm State.
