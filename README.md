# sharedb-postgres

PostgreSQL database adapter for [sharedb](https://github.com/share/sharedb). This
driver can be used both as a snapshot store and oplog.

Doesn't support queries (yet?).

Moderately experimental. (This drives [Synaptograph](https://www.synaptograph.com)'s backend, and [@nornagon](https://github.com/nornagon) hasn't noticed any issues so far.)


## Usage

`sharedb-postgres` wraps native [node-postgres](https://github.com/brianc/node-postgres), and it supports the same configuration options.

To instantiate a sharedb-postgres wrapper, invoke the module and pass in your
PostgreSQL configuration as an argument. For example:

```js
var db = require('sharedb-postgres')({host: 'localhost', database: 'mydb'});
var backend = require('sharedb')({db: db})
```

## Error codes

PostgreSQL errors are passed back directly.

## Changelog

Note that version 3.0.0 introduces breaking changes in how you specify
connection parameters. See the [changelog](CHANGELOG.md) for more info.
