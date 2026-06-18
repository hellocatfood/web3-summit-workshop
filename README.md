# Make music through code using Strudel

**[https://strudel.cc/](https://strudel.cc/)**  
Strudel is a free and open source website where you can use live coding to make music

## Playing sounds

**$: sound("bd")  

This function will play the bass drum sound once per cycle.

**$: sound("bd bd \[bd bd\] bd")**  

On the third step the bass drum sound (**bd**) will be played twice.

**$: sound("bd bd bd\*2 bd")**

Another way to write this is with the multiplication symbol.

**bank()**  

Strudel has a collection of sounds representing a basic drum kit and percussion sounds. These are crash/ride cymbal (**cr**/**rd**), low tom (**lt**), mid tom (**mt**), hi tom (**ht**), hi-hat (**hh**), open hi-hat (**oh**), snare drum (**sd**/**sn**), rimshot (**rim**), bass drum (**bd**), and clap (**cp**).

Strudel has samples from many different drum machines. Instead of typing the full name of the sample from each drum machine you can use the bank command to load a different sound bank. For example:

**$: sound("bd\*2").bank("9000 casiorz1")**

This will play a bass drum sound from the Linn9000 and CasioRZ1 drum machines. Please note that not all drum machines contain all drum sounds.

## Modifying patterns

**$: sound("bd bd \[cp bd\] bd").fast(2)**
 
The **fast** function plays a pattern faster by a factor of x, in this instance twice as fast.

**$: sound("bd bd \[cp bd\] bd").slow(2)**

The slow function plays a pattern slower by a factor of x, in this instance twice as slow.

**x=\>x**

This function should be used before any function that modifies a pattern.

**every()**

This function will apply a function every x cycles. For example **$: sound("bd bd hh bd").every(4, x=\>x.fast(2))** will play the pattern twice as fast every fourth cycle.

**jux()**

This will apply a function to your pattern but only in the right-hand speaker. For example, running **$: sound("bd cp bd hh").jux(fast(2))** will play the pattern twice as fast only in the right-hand speaker. This is more noticeable if you are wearing headphones.

**rev**

This function will play a pattern in reverse. When combined jux you can have a pattern play in reverse but only in the right-hand speaker. Run this as an example $: sound("bd \[cp,hh\*2\] bd hh ~ hh \[bd bd\] cp").jux(rev).

## Sound effects

**speed**

This function will raise or lower the pitch and speed of a sound. For example **$: sound("bd").speed(0.5)** will make the bass drum sound lower pitched.

**note()**

note is similar to speed but it adjusts the pitch as though they were notes on a keyboard or other pitched instrument. For example, you can run $: note("c e").sound("sine") and it will play the sine sound in the note c and e.

**chord() / voicing()**

You can also play chords. For example **$: chord("\<Cm DM\>").voicing().sound("sine")** will play the c minor chord followed by d major chord using sine as the sound. The voicing() function is needed to convert the chord name into notes that Strudel can interpret. A list of all chords is available here [https://f328my.csb.app/](https://f328my.csb.app/).

**degradeBy**

This function will randomly remove events from your pattern. For example, in **$: sound("bd bd hh bd").degradeBy(0.5)** there will be a 50% chance a sound will not play.

**sometimesBy**

This function randomly applies a function to a pattern. For example, in $: sound("bd cp bd hh").sometimesBy(0.5, x=\>x.speed(0.5)) there is 50% chance that the speed function will be applied to a sound.

## Other sounds to try

| belltree | gm\_pad\_sweep | fingercymbal |
| :-: | :-: | :-: |
| piano1 | glockenspiel | tubularbells |
| gm\_xylophone | woodblock | balafon |
| cajon | bassdrum1 | gm\_fx\_echoes |
| gm\_electric\_guitar\_muted | handchimes | gm\_helicopter |
| gm\_pad\_sweep | shaker\_large | metal |



## Learn more

**learn more Strudel functions and explore patterns made by others at these links:**

* [https://strudel.cc/workshop/getting-started/](https://strudel.cc/workshop/getting-started/)
* [https://www.youtube.com/@Eulerroom](https://www.youtube.com/@Eulerroom)


## My work and music

* [https://hellocatfood.com](https://hellocatfood.com/)
* [https://www.instagram.com/hellocatfood](https://www.instagram.com/hellocatfood)
* [https://soundcloud.com/hellocatfood](https://soundcloud.com/hellocatfood)


## Some of my Studel patterns

**Feel free to deconstruct these and remix them for your own patterns:**

* [Untitled](https://strudel.cc/?PQ46Favth6hc#Ly8gQGJ5IGhlbGxvY2F0Zm9vZAoKLy8gc2V0Y3BtKDEyMC80KQoKLy8ga2lja3MgYW5kIHBlcmN1c3Npb24KJDogc291bmQoIntiZCB%2BIGNwIGJkIH4gYmQvMiB%2BfSU4IikKICAubig3KQogIC5zb21ldGltZXNCeSgwLjIsIHg9Pnguc291bmQoImNwIikpCiAgLnNoYXBlKDAuNSkKICAuZXZlcnkoNCwgZWFybHkoMC4yNSkpCiAgLmV2ZXJ5KDcsIGxhdGUoMC4yNSkpCiAgLmZhc3QoMikKICAuYmFuaygiUm9sYW5kVFI5MDkiKQogIC8vIC5odXNoKCkKICAuY29sb3IoIiNhMGZmZjMiKQogIC5fc2NvcGUoKQovLyBoaSBoYXRzCiQ6IHNvdW5kKCJoaCoxNiIpCiAgLmJhbmsoIlJvbGFuZFRSOTA5IikKICAuc29tZXRpbWVzQnkoMC40LCB4PT54LnNvdW5kKCJoaDoyIikpCiAgLnNvbWV0aW1lc0J5KDAuMiwgeD0%2BeC5zcGVlZCgiMiIpLnBseSgyKS5wYW4oIjAgMSIuZmFzdCg4KSkpCiAgLmxlZ2F0bygwLjYpCiAgLy8gLmh1c2goKQogIC5jb2xvcigiIzAwRkZGRiAjRkYwMEZGIikKICAuX3BpYW5vcm9sbCgpCi8vIHN5bnRoIGtleXMgd2l0aCBvY2Nhc2lvbmFsIGFjaWQgc3F1ZWxjaAokOiBjaG9yZCgiQXN1cyBBbTciKQogIC52b2ljaW5nKCkKICAuc3ViKG5vdGUoIjEyIikpCiAgLmFkZChub3RlKCI8MCA3ICBbOSAyMSA5XSAxMj4iKSkKICAuc291bmQoInN1cGVyc2F3IikKICAuc3RydWN0KCJ0KDMsOCwyKSIuZmFzdCgyKSkKICAuZGVsYXkoIjAuMiIpCiAgLmRlbGF5dGltZSgiMC4yNSIpCiAgLmRlbGF5ZmVlZGJhY2soIjAuNSIpCiAgLmxwZihzaW5lLnJhbmdlKDUwMCwyMDAwKS5zbG93KDcpKQogIC5scHEoIjwxNSAwIDI1PiIpCiAgLmxwZShzaW5lLnJhbmdlKDEsMTApLnNsb3coNikpCiAgLy8gLmh1c2goKQogIC5jb2xvcigiI2ZBMDhBRCIpCiAgLnBpYW5vcm9sbCgpCi8vIGFtYmllbnQgcGFkcwokOiBjaG9yZCgiQXN1cyBBbTciKQogIC52b2ljaW5nKCkKICAuc3ViKG5vdGUoIjEyIikpCiAgLmFkZChub3RlKCI8MCA3IFs5IDIxIDldIDEyPiIpKQogIC5hdHRhY2soIjAuMyIpCiAgLnJlbGVhc2UoIjIiKQogIC5zb3VuZCgiZ21fYmFzc29vbiIpCiAgLmNob3AoNCkKICAucGFuKHNpbmUucmFuZ2UoMC4zLDAuNykuc2xvdyg0KSkKICAuaHBmKDE0MDApCiAgLy8gLmh1c2goKQogIC5jb2xvcigiI2ZmMDAwMCIpCiAgLl9zcGlyYWwoKQ%3D%3D) – includes examples of chords, panning, euclidian rhythms, and visualising patterns.
* [we love we love we love we love](https://strudel.cc/?upyCfJHvgFVo#Ly8gQHRpdGxlIHdlIGxvdmUgd2UgbG92ZSB3ZSBsb3ZlIHdlIGxvdmUKLy8gQGJ5IGhlbGxvY2F0Zm9vZAoKc2V0Y3BtKDE2MC80KQoKYXdhaXQgc2FtcGxlcygnZ2l0aHViOnRpZGFsY3ljbGVzL0RpcnQtU2FtcGxlcy9tYXN0ZXInKQphd2FpdCBzYW1wbGVzKCdnaXRodWI6eWF4dS9zcGljdWxlL21hc3Rlci8nKQoKJDogc291bmQoImtpY2s6NSIpCiAgLnN0cnVjdCgidCg3LDE2KSIpCiAgLnNoYXBlKDAuMykKICAuZ2FpbigwLjQpCiAgLmNvbG9yKCIjZmYwMDAwIikKICAuc3BpcmFsKHtzaXplOiA0MDAsIHBsYXloZWFkQ29sb3I6ICIjMDBGRjAwIiwgaW5hY3RpdmVDb2xvcjogIiMwRjA0NDQifSkKICAvLyAuaHVzaCgpCgokOiBzb3VuZCgiYW1lbmN1dHVwKjE2IikKICAubihpcmFuZCgiMzIiKSkKICAuc3BlZWQoIlsyfDEuMXwwLjc1fDAuOXwxLjZdIikKICAuZXZlcnkoNCwgeD0%2BeC5wbHkoNCkubGVnYXRvKDEpKQogIC5wYW4ocGVybGluLmZhc3QoMTIpKQogIC5jb2xvcigiIzAwZmYwMCIpCiAgLl9waXRjaHdoZWVsKCkKICAvLyAuaHVzaCgpCgokOiBzb3VuZCgiW2NwLHNkXSIpCiAgLnN0cnVjdCgidCg1LDE2KSIpCiAgLmV2ZXJ5KDQsIGVhcmx5KDAuMjUpKQogIC5ldmVyeSgzLCBsYXRlKDAuMjUpKQogIC5jb2xvcigiI2YwNDJmMCIpCiAgLy8gLmh1c2goKQoKJDogc291bmQoIltiZCw4MDhiZF0qMTYiKQogIC5zaGFwZSgwLjQpCiAgLmNydXNoKDMpCiAgLmxlZ2F0bygwLjQpCiAgLm1hc2soIjwwQDE0IDFAMj4iKQogIC5jb2xvcigiIzcyMGVhNCIpCiAgLy8gLmh1c2goKQoKJDogc291bmQoImJhbGFmb246MSg0LDgpIikKICAuZmFzdCgyKQogIC5wYW4oc2luZSkKICAuc29tZUN5Y2xlc0J5KDAuNCwgeD0%2BeC5zcGVlZCgiLTIiKSkKICAuc2hhcGUoMC4wMykKICAuY29sb3IoIiNhYmNkZWYiKQogIC8vIC5odXNoKCkKCiQ6IHNvdW5kKCJsdCg8MyA2IDg%2BLCA4KSIpCiAgLmNodW5rKDQsIGZhc3QoMikpCiAgLml0ZXIoNCkKICAuanV4KHJldikKICAuc3BlZWQoNCkKICAuY29sb3IoIiMwZjA0ZTEiKQogIC8vIC5odXNoKCkKCiQ6IHNvdW5kKCJyZXBldGl0aW9uIikKICAubigiPDAgLi4gOD4iLml0ZXIoNCkuZmFzdCgiPDQgMiAzPiIpKQogIC5zbGljZSg0LCAiMCAxIDIgMyA0Ii5zbG93KDIpKQogIC5tYXNrKCI8MEA2IDFAMj4iKQogIC5kZWxheSgiMC44OjAuNzU6MC42IikKICAuc3BlZWQoIlsxfDEuMXwwLjZ8MC45fDAuN10iLmZhc3QoOCkpCiAgLnJvb20oMC44KQogIC5wYW4oc2luZSkKICAuZWFybHkoMC4xMjUpCiAgLy8gLmh1c2goKQoKLy8gQHZlcnNpb24gMS4y) – includes examples of loading external sample libraries, using drum breaks, euclidian rhythms and visualising patterns. Warning: contains flashing images.
* [Two Chords](https://strudel.cc/?pLgTJk2m_egr#Ly8gQHRpdGxlIHR3byBjaG9yZHMKLy8gQGJ5IGhlbGxvY2F0Zm9vZAoKc2FtcGxlcygnZ2l0aHViOnRpZGFsY3ljbGVzL0RpcnQtU2FtcGxlcy9tYXN0ZXIvJykKc2FtcGxlcygnZ2l0aHViOnlheHUvc3BpY3VsZS9tYXN0ZXIvJykKCnNldGNwbSgxMjUvNCkKCiAgLy8gcGVyY3Vzc2lvbgokOiBzdGFjaygKICAgIHNvdW5kKCJraWNrOjEyKjQiKS5scGYoIjEwMDAiKS5zb21lQ3ljbGVzQnkoIjAuMyIsIHBseSgyKSksCiAgICBzb3VuZCgifiBjcCIpLmZhc3QoMiksCiAgICBzb3VuZCgifiBobyIpLmZhc3QoNCkKICAgICkKICAvLyAuaHVzaCgpCgogIC8vIGxvdyB0b21zCiQ6IHNvdW5kKCJsdCgzLDgpIikKICAuZmFzdCgyKQogIC5zcGVlZCgyKQogIC5zb21ldGltZXNCeSgwLjIsIHg9PnguZGVsYXkoMC41KSkKICAuZ2FpbigiMC43IDEiLmZhc3QoMykpCiAgLy8gLmh1c2goKQoKICAvLyBndWl0YXIKJDogY2hvcmQoIjxHbTcgQW03PiIuc2xvdygyKSkKICAudm9pY2luZygpCiAgLnNvdW5kKCJnbV9waWFubyIpCiAgLm9mZigwLjc1LCBhZGQobm90ZSgyNCkucGFuKHJhbmQucmFuZ2UoMCwxKSkpKQogIC5kZWxheSgwLjQpCiAgLmRlbGF5dGltZSgwLjM1KQogIC5kZWxheWZlZWRiYWNrKDAuNykKICAucm9vbSgwLjUpCiAgLnJvb21zaXplKDcpCiAgLnBvc3RnYWluKDEpCiAgLy8gLmh1c2goKQogIAovLyBhcnBlZ2dpbwokOiBjaG9yZCgiPEdtNyBBbTc%2BIi5zbG93KDIpKQogIC52b2ljaW5nKCkKICAuYWRkKG5vdGUoMjQpKQogIC5hcnAoIjAgMSAyIDMgNCA1IDUgNiA3Ii5pdGVyKDQpLnNvbWV0aW1lc0J5KDAuNCwgZmFzdCgiPFs0IDggMl0gOD4iKSkpCiAgLnNvdW5kKCJiYXNzMTo4IikKICAuYXR0YWNrKDAuMDUpCiAgLnJlbGVhc2UoMSkKICAubGVnYXRvKDEpCiAgLnBhbihzaW5lKQogIC5yb29tKCIwLjk6MC45IikKICAuZ2FpbihyYW5kLnJhbmdlKDAsMC42KSkKICAvLyAuaHVzaCgpCgovLyBiYXNzbGluZQokOiBuKCIxIDwxMSA4PiIpCiAgLnNjYWxlKCJjMjptaW5vciIpCiAgLnNvdW5kKCJiYXNzMToxNSIpCiAgLnN0cnVjdCgidCg8NSBbWzcgM10gNV0%2BLDgpIgogIC5mYXN0KCIyIikpCiAgLy8gLmh1c2goKQoKJDogc291bmQoIn4gcmF2ZTo0IH4gcmF2ZTo0IikKICAuc3BlZWQoIlsxLjQsMC45XSIpCiAgLmhwZigxMDAwKQogIC5uKDcpCiAgLnNsb3coMSkKICAuZ2FpbigiMC41IikKICAuaHVzaCgp) – a simple house track built from who minor chords.
