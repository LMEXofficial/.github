# LMEX — More than just a Cryptocurrency Exchange
![LMEXLogo](https://github.com/user-attachments/assets/227c21b7-00f6-4911-8ca1-cf3a2dc357b6)


**24/7 perpetual futures and spot trading across crypto, US equities, and commodities.**

LMEX is a centralized exchange offering perpetual futures on three asset classes alongside spot trading on 17 fiat and stablecoin pairs, with a full-featured public testnet for development and strategy testing.

---

## Products

### Perpetual Futures
Trade perpetuals 24/7 on assets across three classes:

- 🪙 **Crypto** — BTC, ETH, and more
- 📈 **US Equities** — major US stocks as perpetual contracts
- 🛢️ **Commodities** — energy, metals, and more

No expiry. Funding settled every 8 hours.

### Spot
17 fiat and stablecoin trading pairs — direct buy/sell at market or limit.

### Testnet
Full production replica at `test-api.lmex.io` — connect real bots, test strategies, no funds at risk.

---

## API

### Base URLs

| Environment | Spot | Futures |
|-------------|------|---------|
| Live | `https://api.lmex.io/spot` | `https://api.lmex.io/futures` |
| Testnet | `https://test-api.lmex.io/spot` | `https://test-api.lmex.io/futures` |

### WebSocket

| Feed | URL |
|------|-----|
| Spot | `wss://ws.lmex.io/ws/spot` |
| Futures | `wss://ws.lmex.io/ws/futures` |

Subscribe to a trade stream:
```json
{ "op": "subscribe", "args": ["tradeHistoryApi:BTC-USD"] }
```

### REST Reference

**Spot** — `/spot/api/v3.2/`

| `GET` `market_summary` | All markets and ticker data |
|---|---|
| `GET` `orderbook/L2` | Level-2 order book |
| `GET` `trades` | Recent trades |
| `POST` `order` | Place order *(auth)* |
| `DELETE` `order` | Cancel order *(auth)* |
| `GET` `user/wallet` | Balances *(auth)* |

**Futures** — `/futures/api/v2.3/`

| `GET` `market_summary` | All markets, funding rate, mark price |
|---|---|
| `GET` `orderbook/L2` | Level-2 order book |
| `GET` `funding_history` | Historical funding rates |
| `GET` `user/positions` | Open positions *(auth)* |
| `POST` `leverage` | Set leverage *(auth)* |
| `POST` `order/close_position` | Close position *(auth)* |

### Rate Limits

| Bucket | Limit |
|--------|-------|
| Public / query | 15 req/s |
| Order management | 75 req/s |

---

## Fees

| Side | Rate |
|------|------|
| Maker | 0.10% |
| Taker | 0.10% |

---

## Open-Source Integrations

| Framework | Connector | Notes |
|-----------|-----------|-------|
| [**cryptofeed**](https://github.com/bmoscon/cryptofeed) | `LMEX`, `LMEX_FUTURES` | Trades via WebSocket; order book via REST polling |
| [**Hummingbot**](https://github.com/hummingbot/hummingbot) | `lmex`, `lmex_perpetual` | Full order lifecycle, spot and perpetual |
| [**CCXT**](https://github.com/ccxt/ccxt/pull/28684) | `lmex`, `lmex_perpetual` | Full ccxt-pro for spot and perpetual |


---

- 🌐 [lmex.io](https://lmex.io)
- 📖 [API Docs](https://docs.lmex.io)


