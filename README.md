# luasql-adapter

[![GitHub Action](https://github.com/casbin-lua/luasql-adapter/workflows/test/badge.svg?branch=master)](https://github.com/casbin-lua/luasql-adapter/actions)
[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/casbin/lobby)

casbin-adapter is a LuaSQL based adapter for Casbin that supports policies from SQL-based databases (MySQL, PostgreSQL, SQLite3).

## Installation

First, install the corresponding driver of LuaSQL from LuaRocks based on the database you use:
- For MySQL, install luasql-mysql.
- For PostgreSQL, install luasql-postgres.
- For SQLite3, install luasql-sqlite3.

Then install the casbin-adapter from LuaRocks by
```bash
sudo luarocks install https://raw.githubusercontent.com/casbin-lua/luasql-adapter/master/casbin-adapter-1.0.0-1.rockspec
```

## Usage

To create a new Casbin Enforcer using a MySQL adapter, use:

```lua
local Enforcer = require("casbin")
local Adapter = require("casbin.mysql")

local a = Adapter:new(database, user, password, hostname, port) -- hostname, port are optional
local e = Enforcer:new("/path/to/model.conf", a) -- creates a new Casbin enforcer with the model.conf file and the database
```

For other adapters, replace `local Adapter = require("casbin.mysql")` with:
- `local Adapter = require("casbin.postgres")` for PostgreSQL adapter.
- `local Adapter = require("casbin.sqlite3")` for SQLite3 adapter. In SQLite3 adapter, only database field is required and others are optional.

## Getting Help

- [Lua Casbin](https://github.com/casbin/lua-casbin)

## License

This project is under Apache 2.0 License. See the [LICENSE](https://github.com/casbin-lua/luasql-adapter/blob/master/LICENSE) file for the full license text.