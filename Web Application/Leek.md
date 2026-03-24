## Leek

- Right click on the leek shopping website and go to inspect.
- Go to the network tab 
- Add a new item to the grocery list, anything > Click add
- In the network you should see "add"
- Right click on "add" and copy the cURL 
- Open terminal
- Use this command into your terminal
```
curl 'https://[hostname]/add' \
  -H 'Accept: */*' \
  -H 'Content-Type: application/json' \
  -H 'sec-ch-ua: "Not_A Brand";v="8", "Chromium";v="120", "Google Chrome";v="120"' \
  -H 'sec-ch-ua-platform: "macOS"' \
  --data-raw '{"content":10}' \
  --compressed
```
- Paste the cURL we had copied into the [hostname]
- Click enter and refersh your leeks shopping page
- Flag should be there if done correctly.
    - SKY-WYEB-6094 > Might be different for everyone
