# Nginx Log Analysis

## Why This Is Important

Log analysis is a core cybersecurity skill. Security analysts use logs to:

- Detect suspicious activity
- Investigate security incidents
- Identify malicious requests
- Monitor server usage
- Track attacker behavior

Understanding how to parse logs efficiently allows defenders to quickly uncover important information during an investigation.

---

## Log Structure

Looking at the first few lines of the log file, the **IP address appears as the first field** on each line.

Typical nginx log entries include information such as:

- Client IP address
- Timestamp
- HTTP request method
- Requested resource
- HTTP response code
- User agent

Because these fields appear in consistent positions, Linux tools can be used to extract them.

---

## Useful Linux Tools for Log Analysis

### `cut`
Extracts specific columns or fields from text.

### `sort`
Sorts output alphabetically or numerically.

### `uniq`
Filters unique values or counts repeated entries.

### `wc`
Counts lines, words, or characters.

### `grep`
Searches for patterns or keywords within text.

### `awk`
A powerful text-processing tool used to manipulate structured data.

---

## Extracting Data from Log Columns

### Extracting IP Addresses

Since IP addresses are the **first field**, they can be extracted using `cut`.

To determine how many unique IP addresses accessed the server:

```bash
cat access.log | cut -d " " -f 1 | sort | uniq | wc -l

Questions:

1.
run the following command
cat access.log | cut -d " " -f 1 | sort | uniq | wc -l 
Answer: 47

2.
run the following command
cat access.log | cut -d '"' -f 3 | cut -d ' ' -f 2 | sort | uniq -c | sort -rn
look for 200 and the answer is directly left
Answer:19

3.
same process as Q2
Answer:38

4.
run the following command
cat access.log | grep "bell"
answer is the IP address
Answer: 186.64.69.141

5.
run the following command
cat access.log | grep "Googlebot"
find the version
Answer: 2.1

6.
run the following command
cat access.log | grep '() { :; };'
answer is the IP address
Answer:61.161.130.241

7.
run the following command
cat access.log | egrep -o "Firefox/.*" | sort | uniq -c
Answer:31.0

8.
run the following command
cat access.log | awk -F " " '{print $6}' | sort | uniq -c | sort -rn
Answer: GET

9.
same as 8
Answer: CONNECT

10.
run the following command
cat access.log | grep '\\x04\\x01\\x00P\\xC6\\xCE\\x0Eu0\\x00' | wc -l
Answer:6
