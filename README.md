<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

-   [MessagesManager][1]
    -   [Parameters][2]
    -   [\_messages][3]
    -   [getMessage][4]
        -   [Parameters][5]
    -   [getMessages][6]
        -   [Parameters][7]
    -   [recognizeMessage][8]
        -   [Parameters][9]
-   [Buffer][10]
    -   [Parameters][11]
    -   [Properties][12]
    -   [handleData][13]
        -   [Parameters][14]
    -   [\_removeFromByteBuffer][15]
        -   [Parameters][16]
    -   [subscribe][17]
        -   [Parameters][18]
    -   [readMessage][19]
        -   [Parameters][20]
-   [MessageFragment][21]
    -   [Properties][22]
-   [Message][23]
    -   [Parameters][24]
    -   [Properties][25]
    -   [name][26]
    -   [fragments][27]
    -   [getPattern][28]
    -   [generateBytes][29]
        -   [Parameters][30]

## MessagesManager

### Parameters

-   `messages` **[Array][31]&lt;[Message][32]>** 

### \_messages

Type: [Array][31]&lt;[Message][32]>

### getMessage

#### Parameters

-   `name` **[String][33]** Message name

### getMessages

#### Parameters

-   `names` **[Array][31]&lt;[String][33]>** Array of message names

### recognizeMessage

Recognize a message from an array of bytes

#### Parameters

-   `bytes` **[Array][31]** 
-   `messages` **[Array][31]&lt;[Message][32]>** 

Returns **[Boolean][34]** Returns false if no message is found

Returns **[Object][35]** Returns an Object {type,bytes,values} if a message is found

## Buffer

### Parameters

-   `options` **[Object][35]** 
    -   `options.isMessageStart` **[Object][35]** 
    -   `options.recognizeMessage` **[Object][35]** Function that recognize a message from an array of bytes, it must return false or an Object with a property 'type'
-   `readMessageTimeout` **[Number][36]?** The value of Buffer.readMessageTimeout

### Properties

-   `readMessageTimeout` **[Number][36]** Time (in milliseconds) after which readMessage will throw an error if no data is received

### handleData

Functions that receive chunks of data and recognize the messages

#### Parameters

-   `data` **[Array][31]&lt;[Number][36]>** 

### \_removeFromByteBuffer

Removes N bytes from the buffer

#### Parameters

-   `n` **[Number][36]** Number of bytes to be removed. With n=-1 it emptys the buffer

### subscribe

Subscribe to a message

#### Parameters

-   `options` **[Object][35]** 
    -   `options.msg` **[Message][32]** Message
    -   `options.once` **[Boolean][34]**  (optional, default `true`)
    -   `options.all` **[Boolean][34]**  (optional, default `false`)
    -   `options.callback` **[Function][37]** 

Returns **[Function][37]** unsubscribe callback

### readMessage

Read a message from the serialport

#### Parameters

-   `msg` **[String][33]** Message
-   `options` **[Object][35]**  (optional, default `{}`)
    -   `options.timeout` **[Number][36]?** If not set it uses the readMessageTimeout that was passed to the constructor

Returns **[Message][32]** message

## MessageFragment

Message Fragment

Type: [Object][35]

### Properties

-   `name` **[String][33]** Name of the fragment
-   `desc` **[String][33]?** Description of the fragment
-   `pattern` **[Array][31]&lt;([Number][36] \| [Function][37] \| [String][33])>** Defines the fragment byte pattern. undefined works as a wildcard for a byte and "\*" for multiple bytes
-   `default` **[Array][31]** Used when a message is created

## Message

### Parameters

-   `name` **[String][33]** 
-   `fragments` **[Array][31]&lt;[MessageFragment][38]>** 

### Properties

-   `name` **[String][33]** 

### name

Type: [String][33]

### fragments

Type: [Array][31]&lt;[MessageFragment][38]>

### getPattern

Return pattern

Returns **[Array][31]** Array of Bytes and Function that return array of bytes

### generateBytes

Generate the raw message

#### Parameters

-   `data` **[Object][35]** Dictionary with array of bytes (optional, default `{}`)

Returns **[Array][31]&lt;[Number][36]>** Array of bytes

[1]: #messagesmanager

[2]: #parameters

[3]: #_messages

[4]: #getmessage

[5]: #parameters-1

[6]: #getmessages

[7]: #parameters-2

[8]: #recognizemessage

[9]: #parameters-3

[10]: #buffer

[11]: #parameters-4

[12]: #properties

[13]: #handledata

[14]: #parameters-5

[15]: #_removefrombytebuffer

[16]: #parameters-6

[17]: #subscribe

[18]: #parameters-7

[19]: #readmessage

[20]: #parameters-8

[21]: #messagefragment

[22]: #properties-1

[23]: #message

[24]: #parameters-9

[25]: #properties-2

[26]: #name

[27]: #fragments

[28]: #getpattern

[29]: #generatebytes

[30]: #parameters-10

[31]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array

[32]: #message

[33]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String

[34]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean

[35]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object

[36]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number

[37]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function

[38]: #messagefragment
