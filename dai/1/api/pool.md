---
layout: dai/api
title: Dai 1.0
subtitle: API - Pool
---

### Collateral Pool

The `peth` token is a simple proportional claim on a collateral pool, with the
initial `gem`<->`peth` exchange ratio being 1:1.

The `gem`/`peth` exchange rate is called `per`, and is calculated as the
total number of deposited `gem` divided by the total supply of PETH.

The reference price of `gem` (in practice, ETHUSD) is provided by the `pip`,
an external oracle. The `pip` is completely trusted.

The reference price of `peth` is then given by the dynamic `tag`, e.g.  the
price of PETH in USD.

Anyone can deposit `GEM` to the pool via `join`, and withdraw  via `exit`.
Surpluses generated by the system are paid by burning `PETH` causing its value
to rise proportional to pooled collateral.

![Join-Exit](https://user-images.githubusercontent.com/5028/35772451-cba0bb78-09a3-11e8-8f8e-fc8d6ecbad3e.png)

If `PETH` has to be issued to cover forced liquidations the value of the claim
can also fall during times of volatility.
