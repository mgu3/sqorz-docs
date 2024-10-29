There are two JSON APIs that can be accessed.

# Internet

Firstly, on the internet, via [https://our.sqorz.com](https://our.sqorz.com). You can easily 
examine the API by using your browser’s debugger while looking at [https://our.sqorz.com](https://our.sqorz.com).

To get information about an account, including a list of events:

GET [https://our.sqorz.com/json/org/ffc](https://our.sqorz.com/json/org/ffc)

To get detailed information about an event:

GET [https://our.sqorz.com/json/event/6453634f979fbdc2a0a63db8](https://our.sqorz.com/json/event/6453634f979fbdc2a0a63db8)

Pros: accessible via internet, all event data in a single JSON message.

Cons: not realtime, updates every 30s.

# Local Area Network

The Sqorz app has a built in server that powers our "local web services” feature. 
You can also access this API. This requires that you connect to the scoring computer on the LAN.

Easiest way to learn is to look at browser debugger while using our Local Web Services 
Commentary screen. Martin can help you with this.

Pros: Realtime.

Cons: More complex. Require LAN access.

This API consists of two parts:

# HTTP

Requests are like following:

POST http://<LOCAL_IP_ADDRESS>:4343/api?func=<FUNC>

Function arguments are passed in the request body as a JSON array.

Some useful FUNC for you:

```
getEventSummary

[]

``` 

```
getPhaseBlockSummaries (event schedule)

[]
```
 
```
getPhaseSummaries (in race order)

[]
```
 
```
getRaceDetails (race draw/results for a class/phase)

[
{"classCode":"7X_SP",
"phaseBlockCode":"M1",
"identifyBestTimes":true}
]
```
 
```
getPhaseRankDetail (class ranking)

[
{"classCode":"7X_SP",
"phaseBlockCode":"M1",
"includePhasesWith":"draws",
"includeTeamName":true}
]
```

# Socket.IO (v4)

Receive realtime updates as event unfolds.

Channel relevant to you: /event/raceSummary

This channel sends updates whenever a race changes. Can then call http functions to 
obtain details (getRaceDetails/getPhaseRankDetail).


