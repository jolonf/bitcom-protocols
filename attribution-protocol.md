# Attribution Protocol 

`14aRXSJYPorVuDNET3CzCWZmKh8K7dfqT7`

> Attribution metadata for a transaction.

Allows attribution metadata to be added to any transaction. Also includes fields to sponsor/tip the creator.

# Format

```
14aRXSJYPorVuDNET3CzCWZmKh8K7dfqT7
[name | ' ']
[contact | ' ']
[sponsor | ' ']
[defaultAmount | ' ']
[currency | ' ']
[... future fields]
```

All fields are optional and can contain a single space if not used. 
Additional fields may be added in the future so it is suggested that the Bitcom | operator is used between
protocols or the attribution is the last protocol in the transaction.

- `name` - The name of the contributor, this may not necessarily represent the name of the creator of the content
- `contact` - Any text can be used for contact including web address, email, social media handle, phone number, etc.
- `sponsor` - BSV or paymail address. Other handles/addresses can be used but may not be supported by the application.
- `defaultAmount` - Default amount in the specified `currency` to tip. A fixed point number with no currency symbols. Dot `.` separator, no commas `,`. The `defaultAmount` is only a suggestion and the application may not honour it.
- `currency` - Currency of the `defaultAmount`. Applications may use this currency even if the defaultAmount is overridden however it is not required.

# Example

The following example contains a B Protocol file with an attribution:

```
OP_FALSE
OP_RETURN
19HxigV4QyBv3tHpQVcUEQyq1pzZVdoAut // B:// file
[data]
[media type]
[encoding]
[file name]
|
14aRXSJYPorVuDNET3CzCWZmKh8K7dfqT7 // Attribution protocol
Vangelis
@vangelis
vangelis@moneybutton.com
0.10
USD
```

