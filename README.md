# promaphore

Promise Semaphore

```
npm install promaphore
```

## Usage

``` js
const Semaphore = require('promaphore')

const s = new Semaphore(2) // 2 is the max operation count

if (await s.wait()) { // wait for the to enter the block (only 2 can be in here at once)
  s.signal() // signal that you are exiting the block
}
```

If you want to await all pending operations do `await s.flush()`
If you want to signal all pending waits do `s.destroy()`

## License

MIT
