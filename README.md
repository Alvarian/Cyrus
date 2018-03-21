# Cyrus
Cyrus is an intelligent personal assistant that assists in the learning of SQL. Cyrus has flexible support for English converted to valid SQLite expressions and returns results in natural, spoken language.

<a href="http://ejosue.com/wp-content/uploads/ITiCSE-2018-NatQL-v7.pdf" target="_blank">ITiCSE 2018 paper discussing algorithms developed for Cyrus</a> 

<img src="https://i.imgur.com/yJMLaPQ.png" alt="Screenshot" width="250px">

# Features:
**Wildcard Queries**
> `SELECT * FROM tracks` can be generated in multiple different ways in Cyrus, including
the following widely different forms

(1) “Hey Cyrus, could you please show me all of the tracks I’ve got
in my database?”
(2) “What are the songs in the database?”
(3) “List all of my tracks for me.”
(4) “Tracks, please.”

**Projection Queries**

>The following expressions all map to the query `SELECT TrackId, Name FROM tracks`

(5) “Show track id and name from the tracks table.”
(6) “Output the track ids and names in tracks.”
(7) “List the number and title of the songs.”
(8) “Track id, name, tracks.”

**Selection Queries**
> Queries satisfying constraints are also supported in Cyrus. `SELECT * FROM
tracks WHERE TrackId=1479 AND Composer=’Jimi Hendrix’` can be asked in any of the following forms, among many others

(9) “Get tracks composer Jimi Hendrix where the track id is 1479.”
(10) “Print Jimi Hendrix composed songs with the number 1479.”
(11) “Show me the tracks composed by Jimi Hendrix if the track id
is 1479.”
(12) “Tracks composer Jimi Hendrix 1479 track id.”

>You can map any combination of these voice commands to an amalgamation of all three currently supported query types. For example, `SELECT Name, MediaTypeId, GenereId FROM
tracks WHERE TrackId=1479 AND Composer=’Jimi Hendrix’` would be generated by the following query:

(13) “Print track name, media type and genere of Jimi Hendrix
composed songs whenever the number is 1479.”

However, in the event Cyrus is presented with a query that doesn’t fall under one of the three supported query classes (or a combination of them), Cyrus will respond by saying `“I’m not sure I understand. I am unable to determine your intent. Perhaps you want to try rephrasing or simplifying your query?”`

### Tech

Cyrus has no external dependencies but uses the following technologies to work properly:
* **SFSpeechRecognizer**: Convert spoken query to text
* **NSLinguisticTagger**: Generate parts of speech to use during the SQLite conversion process
* **AVSpeechSynthesizer**: Speak results in natural language form

### Development

Want to contribute? Great! Submit a pull request with well-documented commits and a summary of your additions.

#### Building for source
Simply compile and run in Xcode 9+ with an iOS Device or simulator running iOS 11+

### Todos
 - Improve algorithm for choosing tables/columns when a token partially/completely matches several tables/columns using contextually-generated confidence scores
 - Support for join queries
 - Support for aggregate queries with having clauses
 - Support for division queries with nested sub-queries

License
----

MIT
