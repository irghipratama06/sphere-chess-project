# Sphere Chess

English mobile-friendly chess game for Sphere Wallet + Unicity Testnet 2.

## Current build

- 1 player vs computer
- Easy / Medium / Hard difficulty
- Fixed square chessboard on mobile and desktop
- Sphere Wallet Connect on Testnet 2
- Every UCT deposit requires a separate wallet approval
- 1 UCT = 20 move credits
- 5 UCT = 100 moves
- 10 UCT = 200 moves
- 15 UCT = 300 moves
- UCT Testnet 2 coin ID is pinned to the official testnet2 registry

## Vercel

- Application Preset: Vite
- Root Directory: `./`

Required Environment Variable:

```text
VITE_GAME_TREASURY=<your game's Sphere receiving address>
```

Do not put a private key or recovery phrase in Vercel environment variables.

## Deposit flow

1. Connect Sphere Wallet.
2. Approve the requested `transfer:request` permission.
3. Choose the UCT deposit amount.
4. Tap **Deposit & Verify in Wallet**.
5. Sphere Wallet opens the transfer approval UI.
6. Move credits are added only after the wallet returns a successful send result.

A `deliveryPending` result is not treated as a reason to resend the transfer.

## Important

The game UI does not custody private keys. The connected Sphere Wallet signs and authorizes transfers. Prize-pool accounting and payouts should be handled by a secure backend before production use.
