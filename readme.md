# Recall (POC)
Portable, rapid, inline, cmd syntax note collection and search applicatin.
> I've never learned that before!

The below represent ways in which the tool may or may not function as I build it out.  This **readme.md** currenbtly exists more of a brain dump of ideas than anything else.

It should be able to handle complex regex and multi-line cmds.

### Examples
Note Taking
```python
recall.py -l dig -s "dig $domain ANY +noall +answer +additional" -p "view all dns record types available"
```

Note Recall
```python
recall.py -r "dns records"
```
The desired output would be all entries that included "dns" **or** "records"

```bash
dig @$nameSrv $domain #Bash #query a specific name server # dns
dig $domain ANY +noall +answer #Bash #View all record types available #dns records
dig $domain +trace #Bash #trace path taken to answer #dns answer trace
dig -x $ip  #Bash #Reverse Lookup, Outputs domain name #dns reverse lookup
```

## Intended usage
```python
recall.py -l language -c cmd -s syntax -p purpose -t notes
```
**Language** The source language or tool of the cmd ex: `PowerShell`

**Cmd** The actual command being stored ex: `stop-process`

**Syntax** syntax needed to properly executed cmd to get intended result ex: `stop-process -id 2798`

**Purpose** reason for using this cmd this particular way ex: `kill a single process using powershell`

**Tags** any additional information about the cmd that I may want to recall or use to categorize and search

## Functions
**collection** store note.  This function can be utilized as described above.

**search** recall note.  Usage: `recall.py search "search term"` 

## Features
Store notes as JSON

Export JSON as CSV

## Usage requirements
Language, Syntax, Purpose

Example:
```Python
recall.py -l amass -s "amass -enum $domain" -p "enumerate subdomains"
```
## Internal Checks
- Check if syntax already exists (or something similar already exists)

## Other

When a note is stored an ID is associated to it for internal reference
