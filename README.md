# mtf_adx

A TradingView indicator that shows how strong a trend is, and which way it
points, on seven timeframes at once.

It reads the ADX (average directional index) and the two directional lines
(+DI and −DI) on 5-minute, 15-minute, 30-minute, 1-hour, 4-hour, daily and
weekly bars, and lays them out in a table in the top-right corner of its pane:

| Column | Shows |
|---|---|
| TF | the timeframe — M5, M15, M30, H1, H4, D1, W1 |
| ADX | the ADX value on that timeframe |
| Direction | **up** when +DI is above −DI, **down** otherwise — labelled *Weak* at ADX 25 or below, *Uptrend* / *Downtrend* above 25, *Strong* above 40 |
| Strength % | the ADX value, positive when the trend is up and negative when it is down |

Below the table, the pane plots the ADX of the chart's own timeframe, with
reference lines at 25 and 50.

Both ADX settings are fixed at 14 bars: the DI length and the ADX smoothing.

## Adding it to a chart

1. Open a chart on TradingView and open the **Pine Editor**.
2. Create a new indicator, replace its contents with the contents of
   `mtf_adx.pine`, and save.
3. Click **Add to chart**.

The script is written in Pine Script version 6.

## Alerts

The indicator can raise an alert when one chosen timeframe shows a trend of the
kind you are looking for. Set these in the indicator's settings:

| Setting | Default | Meaning |
|---|---|---|
| Enable Alerts | on | Turns the alert condition on or off |
| Alert Timeframe | 60 (1 hour) | The timeframe the alert watches: 5, 15, 30, 60, 240, D or W |
| Minimum ADX | 25 | The alert needs at least this ADX (10 to 60) |
| Trend Direction | Both | Up, Down, or Both |
| Trend Strength | Trend | Weak needs ADX 15 or more, Trend 25 or more, Strong 40 or more |
| Alert Cooldown (bars) | 5 | The least number of bars between two alerts |

The alert fires when every condition holds on the chosen timeframe and the
cooldown has passed. To receive it, create an alert in TradingView on this
indicator and pick the condition **MTF ADX Alert**.

## Licence

MIT — see [LICENSE](LICENSE).

From [ChorBazaar](https://chorbazaar.co.in).
