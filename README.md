# Big Mac Index in JSON

I wanted to build an assignment for students learning how to use APIs in React that compared not only currency exchange rates but also purchasing power. It might not be perfect, but [The Economist's bi-annual Big Mac Index](http://www.economist.com/content/big-mac-index) certainly helps understand economic concepts.

The only problem is it's not in an easily digestible format for web development. Since I went to the trouble of converting it to JSON, I thought I would make my conversions available to others as well.

Check out [The Economist's Big Mac Index site](http://www.economist.com/content/big-mac-index) for more information on the project and the concepts of purchasing power and currency valuations.

## Data

The format of the data is:

```javascript
{
  "releateDate": "2017-01-01",
  "data": [{
    "Country": "Argentina",
    "local_price": 55,
    "dollar_ex": 15.9,
    "dollar_price": 3.47,
    "dollar_ppp": 10.9,
    "dollar_valuation": -31.5,
    "dollar_adj_valuation": 6.3,
    "euro_adj_valuation": 8.3,
    "sterling_adj_valuation": 29.6,
    "yen_adj_valuation": 32.7,
    "yuan_adj_valuation": 13.6
  }, {
    "Country": "Australia",
    "local_price": 5.8,
    "dollar_ex": 1.4,
    "dollar_price": 4.28,
    "dollar_ppp": 1.1,
    "dollar_valuation": -15.5,
    "dollar_adj_valuation": -11.9,
    "euro_adj_valuation": -10.3,
    "sterling_adj_valuation": 7.4,
    "yen_adj_valuation": 10,
    "yuan_adj_valuation": -5.8
  }, {
  // ...
```

### Date

Each file contains all of the data for one release date. The object contains a field for the release date in `YYYY-MM-DD` (ISO 8601) format. Note that the release dates provided are only month and year, so I added `01` for the day.

### Normalization

Later release dates used empty cells in places where earlier ones used "#N/A". To normalize the data, all "#N/A" and empty cells were changed to `null`.

Similarly, earlier releases used `id` for the `Country`. These were changed to all use `Country`.

## Contributing

Contributions are welcome. Simple follow the same pattern for the previous files by release date.

## Disclaimer

Floating point numbers are notoriously difficult to work with in JavaScript. Read [What Every JavaScript Developer Should Know About Floating Points](https://modernweb.com/what-every-javascript-developer-should-know-about-floating-points/) by Brian Rinaldi for more info.

**This data comes with no warranty.**

This program is free software. It comes without any warranty, to the extent permitted by applicable law. You can redistribute it and/or modify it under the terms of the Do What The Fuck You Want To Public License, Version 2, as published by Sam Hocevar. See [http://www.wtfpl.net/](http://www.wtfpl.net/) for more details.

## License

Copyright © 2017 Sia Karamalegos and contributors, [http://siakaramalegos.github.io/](http://siakaramalegos.github.io/)
This work is free. You can redistribute it and/or modify it under the terms of the Do What The Fuck You Want To Public License, Version 2, as published by Sam Hocevar. See [http://www.wtfpl.net/](http://www.wtfpl.net/) for more details.

