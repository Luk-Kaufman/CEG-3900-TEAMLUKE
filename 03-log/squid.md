# Squid Log Analysis

## Why This Matters
Squid logs help analysts:
- Track web traffic
- Detect suspicious activity
- Measure request speed
- Investigate compromised hosts

---

## Log Structure
View logs:
```bash
head squid_access.log

Common fields:

$1 → Timestamp (Epoch)

$2 → Response time (ms)

$3 → Client IP

$6 → HTTP method (GET/POST)

Epoch Time

Convert to readable format:

date -d @<timestamp>
Useful Commands
Fastest / Slowest Request
awk '{print $2}' squid_access.log | sort -n
Unique IPs
awk '{print $3}' squid_access.log | sort | uniq | wc -l
Count GET / POST
awk '{print $6}' squid_access.log | sort | uniq -c
Search Specific IP
grep "192.168.0.224" squid_access.log
Key Idea

Use awk for columns

Use sort + uniq for counts

Use grep for filtering

Know field positions


Questions:

1.
run the following command
head squid_access.log
find the epoch (something like 1286536308) and use https://www.epochconverter.com/ to get the year
Answer: 2010

2.
run the following command
cat squid_access.log | awk '{print $2}' | sort -n
find the shortest
Answer:5

3.
run the following command
cat squid_access.log | awk '{print $2}' | sort -n
find the longest
Answer:41762

4.
run the following command
cat squid_access.log | awk '{print $3}' | sort | uniq | wc -l
Answer: 4

5.
run the following command
cat squid_access.log | grep "GET" | sort | uniq | wc -l
Answer: 35

6.
run the following command
cat squid_access.log | grep "POST" | sort | uniq | wc -l
Answer:78

7.
run the following command
cat squid_access.log | grep "192.168.0.224"
Answer:liveupdate.symantecliveupdate.com

8.
run the following command
cat squid_access.log | grep "virus"
find the address with both virus and definitions
Answer: http://liveupdate.symantecliveupdate.com/streaming/norton$202009$20streaming$20virus$20definitions_1.0_symalllanguages_livetri.zip

