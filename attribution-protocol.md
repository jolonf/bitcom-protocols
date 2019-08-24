# Attribution Protocol 

`14aRXSJYPorVuDNET3CzCWZmKh8K7dfqT7`

> Attribution metadata for a transaction.

Allows attribution metadata to be added to any transaction. Also includes fields to sponsor/tip the creator. A transaction may have multiple attribution protocols allowing multiple contributors to be sponsored. 

# Format

```
14aRXSJYPorVuDNET3CzCWZmKh8K7dfqT7
[name | ' ']
[contact | ' ']
[license | ' ']
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
- `license` - e.g. Creative Commons (e.g. `CC BY`), copyright, GPL, MIT, etc.
- `sponsor` - BSV or paymail address. Other handles/addresses can be used but may not be supported by the application.
- `defaultAmount` - Default amount in the specified `currency` to tip. The `defaultAmount` is only a suggestion and the application may not honour it. A fixed point number with no currency symbols. Dot `.` separator, no commas `,`.
- `currency` - Currency of the `defaultAmount`. Applications may use this currency even if the `defaultAmount` is overridden however it is not required.

# Example

The following example contains a B protocol file followed by a single attribution protocol:

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
Copyright 1977
vangelis@moneybutton.com
0.10
USD
```

This example includes two attribution protocols:

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
Copyright 1984
vangelis@moneybutton.com
0.10
USD
|
14aRXSJYPorVuDNET3CzCWZmKh8K7dfqT7 // Attribution protocol
Jon
@jon
Copyright 1984
jon@moneybutton.com
0.10
USD
```
