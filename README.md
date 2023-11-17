
## Installation

This package is in JavaScript, install with npm:

```bash
  npm install sms-packet-count
```
    
## SMS-PACKET-COUNT
The determination of SMS packet count involves assessing encoding methods (GSM 7-bit or Unicode) for character representation, with GSM 7-bit accommodating limited characters and Unicode supporting a broader set, influencing the segmentation of messages into packets for transmission efficiency.
## Unicode Encoding
Unicode is a character encoding standard that represents most of the world's written languages. It uses a 16-bit encoding scheme, allowing it to represent a wide range of characters. In SMS messages, Unicode encoding is used when the message includes characters outside the GSM 7-bit character set.


- Character Set: Unicode can represent a vast number of characters, including special characters, emojis, and characters from various languages.
- Size: Each Unicode character is represented using 16 bits (2 bytes).
- Message Length: Unicode-encoded messages will have a maximum length of 70 characters per SMS.

## GSM 7-bit Encoding
GSM 7-bit encoding is a character encoding standard specifically designed for SMS messages in GSM networks. It is a compact encoding that allows for the transmission of text messages using a 7-bit alphabet.



- Character Set: The GSM 7-bit character set includes the basic Latin alphabet, digits 0-9, and some special characters.
- Size: Each character is represented using 7 bits, allowing for 128 different characters.
- Message Length: GSM 7-bit encoded messages will have a maximum length of 160 characters per SMS.



## Packet Count:


The concept of "packet count" is more commonly associated with data communication protocols like TCP/IP, where data is divided into packets for transmission. In the context of SMS, messages are usually referred to in terms of character count or message parts.



- Message Parts: If a message exceeds the maximum length for a single SMS (e.g., more than 160 characters for GSM 7-bit or 70 characters for Unicode), it will be split into multiple parts.
- Concatenation: These parts are then sent separately, and the receiving device must reassemble them to reconstruct the complete message.
- Message Length: Unicode-encoded messages will have a maximum length of 70 characters per SMS.
- Header Overhead: When messages are split, each part includes a header that consumes some of the available character space.


In summary, when working with SMS messages, consider the character encoding (Unicode or GSM 7-bit) and be aware of the maximum length limitations. If a message exceeds these limits, it will be split into multiple parts, and each part may be subject to additional header overhead. The actual "packet count" would depend on the length of the message and the encoding used.
## Usage/Examples

```javascript
import {getCharset , getPartCount} from 'sms-packet-count'

const message = "Eren Yeager (エレン・イェーガー Eren Yēgā?) was a former member of the Survey Corps. He was the main protagonist of Attack on Titan. He lived in Shiganshina District with his parents until the fall of Wall Maria, where he impotently witnessed his mother being eaten by a Titan.[33] This event would lead to Eren's intense hatred towards the Titans as he swore to wipe all of them off the face of the Earth.Soon afterward, his father, Grisha Yeager, found him and gave him the key to his basement, instructing Eren to find it at all costs and retake Wall Maria.[ He then injected Eren with a Titan serum."

console.log(getCharset(message) , getPartCount(message));

```


## Usage/Examples - Node 

```javascript
const { getCharset, getPartCount, getCharacterCount } = require('sms-packet-count');


const message = "Eren Yeager (エレン・イェーガー Eren Yēgā?) was a former member of the Survey Corps. He was the main protagonist of Attack on Titan. He lived in Shiganshina District with his parents until the fall of Wall Maria, where he impotently witnessed his mother being eaten by a Titan.[33] This event would lead to Eren's intense hatred towards the Titans as he swore to wipe all of them off the face of the Earth.Soon afterward, his father, Grisha Yeager, found him and gave him the key to his basement, instructing Eren to find it at all costs and retake Wall Maria.[ He then injected Eren with a Titan serum."

console.log(getCharset(message) , getPartCount(message) , getCharacterCount(message));

```




## Authors

- [@Huzaifa Khalil](https://github.com/HUZAIFAKHALIL)


## Features

- The system can identify the encoding used when sending an SMS message.
- It can break down the SMS into individual packets and provide the total number of packets.
- The system calculates the character count of the characters used in the SMS.
- It is compatible across different platforms.





