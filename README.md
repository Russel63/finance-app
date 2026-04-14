# Finance App

A stock trading simulator built with Flask. Users can register, look up real-time stock quotes, buy/sell shares, and track their portfolio and transaction history.

## Features

- Register / Login / Logout
- Look up stock quotes by symbol
- Buy and sell shares
- Portfolio overview with current prices and total value
- Full transaction history
- Password change in settings
- Reset progress (discard all holdings)

## Stack

- **Backend:** Python, Flask, CS50 SQL (SQLite)
- **Auth:** Werkzeug password hashing, Flask-Session
- **Data:** `lookup()` helper for real-time stock prices

## Database Schema

| Table          | Key Columns                                      |
|----------------|--------------------------------------------------|
| `users`        | `id`, `username`, `hash`, `cash`                 |
| `owners`       | `user_id`, `sign`, `value`                       |
| `transactions` | `user_id`, `sign`, `value`, `price`, `time`      |

## Setup

```bash
pip install flask flask-session cs50 werkzeug
flask run
```

Make sure `finance.db` exists with the schema above before running.

## Routes

| Route        | Methods    | Description              |
|--------------|------------|--------------------------|
| `/`          | GET        | Portfolio overview        |
| `/register`  | GET, POST  | Create account            |
| `/login`     | GET, POST  | Log in                    |
| `/logout`    | GET        | Log out                   |
| `/quote`     | GET, POST  | Look up a stock quote     |
| `/buy`       | GET, POST  | Buy shares                |
| `/sell`      | GET, POST  | Sell shares               |
| `/history`   | GET        | Transaction history       |
| `/settings`  | GET, POST  | Change password           |
| `/discard`   | POST       | Reset portfolio to $10,000|
