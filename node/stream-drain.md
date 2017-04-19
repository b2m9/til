# Use drain to write lots of stuff via streams

If you print out big chunks of data via `console.log` you may run into trouble.
A better approach is actually to use streams [1]:

```ecmascript 6
function writeOutput (writer, data, encoding, callback) {
  'use strict'
  let i = 0
  let l = data.length

  write()

  function write () {
    var ok = true

    for (i = 0; i < l; i++) {
      if (i === l - 1) {
        // Last time
        writer.write(data[i] + '\n', encoding, callback)
      } else {
        // see if we should continue, or wait
        // don't pass the callback, because we're not done yet.
        ok = writer.write(data[i] + ' ', encoding)
      }

      if (!ok) break
    }

    if (i < l) {
      // had to stop early!
      // write some more once it drains
      writer.once('drain', write)
    }
  }
}

writeOutput(process.stdout, lotsOfData, 'utf-8', process.exit)
```

References:

- [1] [Nodejs.org: Streams](https://nodejs.org/api/stream.html#stream_event_drain)
