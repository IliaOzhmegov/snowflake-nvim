# snowflake-nvim

A fast Snowflake query client for Neovim, powered by a persistent Python backend.

snowflake-nvim avoids spawning SnowSQL for every query. It keeps a local Python
worker alive, reuses Snowflake connections where possible, and provides a
Neovim-native query workflow for SSO-heavy environments.

## MVP scope

- Connect to Snowflake with external browser authentication
- Keep a persistent backend process per Neovim session
- Execute current selection, current statement, or whole buffer
- Show query results in a scratch buffer
- Cancel running queries
- Support multiple named profiles
- Provide `:checkhealth snowflake`

- ## Non-goals

- Replacing vim-dadbod
- Supporting non-Snowflake databases
- Implementing the Snowflake protocol in Lua
- Acting as a long-running network service
