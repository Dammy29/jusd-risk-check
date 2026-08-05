# JUSD Risk Check

An unofficial, read-only tool to check whether a wallet still holds JUSD (JuiceDollar) that needs to be swapped for USDT before the protocol's stated deadline: **10 August 2026, 12:57 UTC**.

**Live:** https://jusd-risk-check.vercel.app

## What this is

JuiceDollar's official site ([juicedollar.com](https://juicedollar.com)) posted a notice that control over the protocol has been lost, and that JUSD can only be swapped for USDT via the official bridge until the deadline above. This page makes it easy to check whether a specific wallet is affected, using public holder data.

## What this is *not*

- It does **not** connect to your wallet.
- It does **not** execute any swap or transaction.
- It is **not affiliated** with JuiceDollar, JuiceSwap, or Citrea.
- It is a static page that reads public data and links out to the official swap page — nothing more.

## How it works

- Fetches the current JUSD holder list directly from the [Citrea Blockscout explorer API](https://explorer.mainnet.citrea.xyz/token/0x0987D3720D38847ac6dBB9D025B9dE892a3CA35C) in your browser (no backend, no data collection).
- Separates individual wallet addresses from protocol contracts (LP pools, savings vault, etc.), since those are handled differently.
- Lets you paste an address to check its balance and status.
- Links to the official swap page: `bapp.juicedollar.com/swap` — **always verify that URL yourself before using it.**

## Verify it yourself

Don't take this repo's word for it — the source is a single file, `index.html`, with no build step and no external dependencies beyond the Blockscout API. Read it before you trust it:
- [JUSD contract on Citrea Explorer](https://explorer.mainnet.citrea.xyz/token/0x0987D3720D38847ac6dBB9D025B9dE892a3CA35C)
- [JuiceDollar's official notice](https://juicedollar.com)

## Running locally

No build tools needed — it's a single HTML file.

```bash
git clone https://github.com/Dammy29/jusd-risk-check
cd jusd-risk-check
open index.html   # or just double-click it
```

## Disclaimer

This tool is provided for informational purposes only, with no guarantee of accuracy or availability. It is not financial or security advice. Always verify contract addresses and URLs independently before taking any on-chain action.
