
# Binance Data Streams

# Overview
This repository contains scripts for tracking various activities on the Binance exchange such as large orders, monitoring funding rates, and liquidations. These scripts utilize WebSockets to receive real-time data and process it accordingly.


##  Dependencies

These scripts require the following Python modules:

asyncio
json
datetime
websockets
termcolor
os
pytz



To run these scripts, ensure you have the following Python modules installed. You can install them using pip:
```sh
pip install asyncio json datetime websockets termcolor pytz
```
## Scripts

1. **funding.py**: Tracks the funding rates for specified symbols.
2. **large_liqs.py**: Monitors large liquidations.
3. **large_trades.py**: Tracks large trades.
4. **liquidations.py**: Monitors liquidations.
5. **stream.py**: General script for tracking trades for specified symbols.

## Script Details

### funding.py
- Tracks funding rates for specified symbols.
- Prints the yearly funding rate and highlights high or low rates with different colors.

### large_liqs.py
- Monitors large liquidations across the Binance exchange.
- Logs liquidation details to a CSV file and prints significant liquidations with color coding.

### large_trades.py
- Tracks large trades for specified symbols.
- Aggregates trades over time and prints significant trades with color coding.

### liquidations.py
- Similar to `large_liqs.py`, but monitors all liquidations.
- Logs liquidation details to a CSV file and prints significant liquidations.

### stream.py
- A general script to track trades for specified symbols.
- Logs trade details to a CSV file and prints significant trades with color coding.


## Editing Tracked Symbols

To edit the symbols (cryptocurrency pairs) that are being tracked by each script, modify the `symbols` list at the beginning of each file. Below are the specific lines to update in each script:

```python
symbols = ['btcusdt', 'ethusdt', 'solusdt', 'ondousdt', 'fetusdt']
```
## Changing Timezone
You can change the time the trade takes place by editing the timezone settings in the script. For example, in large_trades.py, you can change the timezone from US/Eastern to UTC+1 as follows:
```python
import pytz
```
### Replace this line:
```python
trade_time = datetime.fromtimestamp(data["T"] / 1000, pytz.timezone("US/Eastern"))
```
### With this line:
```python
trade_time = datetime.fromtimestamp(data["T"] / 1000, pytz.timezone("Etc/GMT-1"))
```
This will convert the trade timestamp to UTC+1 time.

You can find more info on this looking up the documentation for pytz.
## Usage

To run any of the scripts, use the following command in your terminal:
```sh
python <script_name>.py
```

For example, to run the `funding.py` script:
```sh
python funding.py
```


## Contributing

Contributions are always welcome!

Feel free to fork this repository and submit pull requests for any enhancements or bug fixes.

## License

This project is licensed under the MIT License. 

[MIT](https://choosealicense.com/licenses/mit/)

Happy tracking!
