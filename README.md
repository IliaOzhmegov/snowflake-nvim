# snowflake-nvim

A fast Snowflake query client for Neovim, powered by a persistent Python backend.

snowflake-nvim avoids spawning SnowSQL for every query. It keeps a local Python
worker alive, reuses Snowflake connections where possible, and provides a
Neovim-native query workflow for SSO-heavy environments.

> Status: early MVP / experimental. Not ready for daily use yet.

## Why?

Existing Neovim database workflows often rely on spawning external CLIs such as
SnowSQL. For Snowflake environments using browser-based SSO, that can make
interactive querying slow.

snowflake-nvim is designed around a persistent local Python worker instead.

## MVP scope

- Connect to Snowflake with external browser authentication
- Keep a persistent backend process per Neovim session
- Execute current selection, current statement, or whole buffer
- Show query results in a scratch buffer
- Cancel running queries
- Support multiple named profiles
- Provide `:checkhealth snowflake`

## Non-goals

- Replacing vim-dadbod
- Supporting non-Snowflake databases
- Implementing the Snowflake protocol in Lua
- Acting as a long-running network service
