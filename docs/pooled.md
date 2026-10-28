# Pooled staking

Running an Ethereum validator needs exactly 32 ETH and operating infrastructure. Pooled staking lets users stake any amount: deposits are pooled in a **StakeWise** vault, the same infrastructure behind MetaMask's pooled staking, and professional node operators run the validators.

## How it works

```mermaid
flowchart LR
    U1["User A · 0.5 ETH"] --> V["StakeWise vault"]
    U2["User B · 3 ETH"] --> V
    U3["User C · 40 ETH"] --> V
    V -- each 32 ETH --> VAL["Ethereum validators<br/>run by node operators"]
    VAL -- consensus + execution rewards --> V
    V -- rewards net of vault fee --> U1 & U2 & U3
```

## Unstaking

```mermaid
stateDiagram-v2
    [*] --> Staked: Deposit ETH
    Staked --> Unstaking: Request unstake (all or part)
    Unstaking --> ReadyToClaim: Exit queue processed, usually a few days
    ReadyToClaim --> [*]: Claim ETH + rewards earned while waiting
```

ETH keeps earning rewards while it waits in the exit queue.

## Pooled or liquid

| | Pooled | Liquid (osETH) |
| --- | --- | --- |
| Holds | Staked balance in the vault | osETH tokens |
| Exit | Exit queue only | Exit queue, or sell instantly |
| DeFi use | No | Yes |
| Simplicity | Highest | Requires handling a token |

The vault takes a fee from rewards. The APY shown is after it. DYXY adds no fee.
