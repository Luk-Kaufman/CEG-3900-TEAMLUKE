# Payments Log Analysis

## Why This Matters
Payment logs may expose:
- Credit card activity
- Purchase amounts
- Customer data
- Transaction IDs

---

## Log Structure
Relevant lines:
- `PPAPIService: Request:` → payment details
- `PPAPIService: Response:` → transaction results

Data is stored in **XML (SOAP format)**.

---

## Extracting XML

### Linux
```bash
sed -nr 's/PPAPIService: Request: (.*)/\1/p' payments.log > requests.xml
sed -nr 's/PPAPIService: Response: <\?.*\?>(.*)/\1/p' payments.log > responses.xml

Add root tags:

<xml>
...
</xml>
Convert XML → CSV

Use tools like:

convertcsv.com

Excel import

Key Analysis Tasks
Count Transactions

Count rows in CSV

Largest Purchase + Transaction ID

Sort OrderTotal column

Find largest value

Note row number

Match same row in responses

Extract TransactionID

Most Purchases by State

Use ShipTo State column

Count unique values

Highest count = answer

Key Idea

Requests = purchase data

Responses = transaction IDs

Match them by order/position

Questions:

1.
run the following command
cat payments.log | grep "PPAPIService: Request:" | wc -l
Answer: 192

2.
run the following command
grep -oP '(?<=OrderTotal currencyID="USD">)[0-9.]+' payments.log | sort -n
run this command
grep -A20 "988.6" payments.log | grep -oP '(?<=TransactionID>)[^<]+'
answer is the top one
Answer:3a4da8c8-6934-4655-9ec5-335ab4540a2b

3.
run the following command
grep -oP '(?<=<ebl:StateOrProvince>)[^<]+' payments.log | sort | uniq -c | sort -nr
Answer:MA

