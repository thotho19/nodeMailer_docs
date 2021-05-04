# nodeMailer_docs

**STMP** = Simple Mail Transfer Protocol <br>
**POP3** = Post Office Protocol <br>
**AMQP** = Advanced Message Queuing Protocol <br>
# Setting it up nodemailer <br>

1. To send emails you need a transporter object:
    
```json
let transporter = nodemailer.createTransport(transport[, defaults])
```
* transporter is going to be an object that is able to send mail
* transport is the transport configuration object, connection url or a transport plugin instance
* defaults is an object that defines default values for mail options

2. Once you have a transporter object you can send mail with it:

```json
transporter.sendMail(data[, callback])
```

* data defines the mail content (see Message Configuration for possible options)
* callback is an optional callback function to run once the message is delivered or it failed
     - err is the error object if message failed
     - info includes the result, the exact format depends on the transport mechanism used
          - info.messageId most transports should return the final Message-Id value used with this property
          - info.envelope includes the envelope object for the message
          - info.accepted is an array returned by SMTP transports (includes recipient addresses that were accepted by the server)
          - info.rejected is an array returned by SMTP transports (includes recipient addresses that were rejected by the server)
          - info.pending is an array returned by Direct SMTP transport. Includes recipient addresses that were temporarily rejected together with the server response
          - response is a string returned by SMTP transports and includes the last SMTP response from the server
** bulk mail ** = if you need to send 10 million messages at once.
** CC ** = send a copy from the message to specific one <br>
** BBC ** = it is best to use the Blind Carbon Copy (BCC) feature when sending an email message to a large number of people. When you place email addresses in the BCC field of a message, those addresses are invisible to the recipients of the email. <br>

