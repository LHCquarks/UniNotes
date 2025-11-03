## Extended ASCII
We use the extra 8th bit in ASCII to implement other characters.

Unfortunately there was no standard so we get a lot of **Mojibake** disasters. 
This is where we decode data with a different system than it was encoded in resulting in a mess!

## UNICODE
Unicode has space for 1.1 million code points. We separate these charters into 14 planes:

| Plane | Use                        |
| ----- | -------------------------- |
| 0     | Traditional language chars |
| 1     |                            |
| 2     | Ancent languages           |
| 3     |                            |
| 4-13  |                            |
| 14    |                            |
### UTF-32
To accommodate for all these extra chars we need 21 bits so we place it into a 32 bit number.
This is called **UTF-32**

### UTF-8
To waste less bits we use **UTF-8** which works off the following encoding scheme

| bytes | Byte 1   | Byte 2   | Byte 3   | Byte 4   |
| ----- | -------- | -------- | -------- | -------- |
| 1     | 0xxxxxxx | -        | -        | -        |
| 2     | 110xxxxx | 10xxxxxx | -        | -        |
| 3     | 1110xxxx | 10xxxxxx | 10xxxxxx | -        |
| 4     | 11119xxx | 10xxxxxx | 10xxxxxx | 10xxxxxx |
This helps us reduce the amount of wasted space and ontop of that is backwards compatible with ASCII!
