# level-live

Simple, light and correct [LevelDB](https://github.com/level/level) live read stream implementation.

---

**Fork of [voltraco/level-live](https://github.com/voltraco/level-live) with two PRs applied: [#1](https://github.com/voltraco/level-live/pulls/1) and [#2](https://github.com/voltraco/level-live/pulls/2). Published to npm as `@frando/level-live`**

---

## Usage

```js
const stream = new Live(db, { gt: 'prefix' })

stream.on('data', ({ type, key, value }) => {
  // ...
})
```

## Installation

```bash
$ npm install level-live
```

## API

### stream = new Live(db[, opts])

`opts` can be a levelup style range object with any of those options:

- `gt`
- `gte`
- `lt`
- `lte`
- `start`
- `end`

Additional options are:
- `old` set to false to skip past entries and only listen live

### Event `sync`

Emitted once the live stream finished the past and caught up to the present.

## License

MIT
