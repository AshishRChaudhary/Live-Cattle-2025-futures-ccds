Live Cattle futures = a bet on the future price of cows.
Imagine you're a farmer raising cows. You're worried that by the time you're ready to sell them in 6 months, prices might drop. So today you lock in a price — "I'll sell my cows at $200 in June." That agreement is a futures contract.
On the other side, a beef company might worry prices will rise, so they lock in buying at $200. Both sides get certainty.
Your data is basically: "what was the agreed price for cattle on each day, and how many people were trading it?"

Open/High/Low/Close — like a stock price, just for that agreement
Volume — how many contracts traded that day
Open Interest — how many contracts are still open (not settled yet)

The 6 files are just 6 different expiry dates — like 6 different "deadlines" spread across 2025. Feb, Apr, Jun, Aug, Oct, Dec.
What the price rise means in plain terms: cattle got significantly more expensive through 2024–2025 — roughly from $170 to $248 per hundredweight — mainly because there are fewer cows in the US right now than in decades.
That's it. Our ML project is trying to predict whether that price will go up, down, or stay flat over the next 5 days.

Target column?

The raw data only tells you what the price was each day. It doesn't tell you whether that day was a good time to buy or sell — that label doesn't exist anywhere, we have to create it ourselves.
The way we're doing it is simple: for each day, we look 5 days into the future and ask — did the price go up, down, or stay roughly the same?

If it went up more than 0.5% → Buy
If it fell more than 0.5% → Sell
If it barely moved → Hold
