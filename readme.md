
# pull-spawn-process

> Use pull-streams with `child_process.spawn` stdio

A convenient wrapper around [`child_process.spawn`]() for use with [`pull-stream`](https://github.com/pull-stream/pull-stream)

```js
var cat = spawn('cat', ['somefile.txt'])

// Read the process's stdout
pull(cat, drain(console.log))

// Write process stdin
pull(values(['foo', 'bar']), cat)
```

Returns a duplex stream with an additional `error` prop to handle `proc.stderr`.  The other child_process methods are available too.

## Install

```sh
npm install --save pull-spawn-process

# with yarn
yarn add pull-spawn-process
```

## Usage

### `spawn(command, args?, options?)`

The signature is the same as [`child_process.spawn`](https://nodejs.org/api/child_process.html#child_process_child_process_spawn_command_args_options), except returns a duplex pull-stream.

```js
var cat = spawn('cat')
var echo = spawn('echo', ['foo', 'bar'])
var eslint = spawn('eslint', files, { stdio: 'inherit' })
```

The rest of the `ChildProcess` methods are exposed on the object

---

Maintained by [Jamen Marz](https://git.io/jamen) (See on [Twitter](https://twitter.com/jamenmarz) and [GitHub](https://github.com/jamen) for questions & updates)

