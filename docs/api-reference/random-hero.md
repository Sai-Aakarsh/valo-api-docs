# Random Agent Route

## [Base URL](./overview.md/#base-url)

```plaintext
https://valo-api.vercel.app
```

## `/random-agent` Endpoint

### Description

The Random Agent endpoint returns a random Valorant agent. This can be useful for applications that want to suggest a random agent to players. Can be used without an API key. Can also be used with a role query parameter to get a random agent of a specific role which can be any of the following: `duelist`, `initiator`, `sentinel`, `controller`.

### HTTP Method

`GET`

### Endpoints

- `/random-agent`
- `/random-agent/{role}`

## Command Setup for Chatbots

To use the Random Agent endpoint in your chatbot, you can set up a command that fetches a random agent from the API. Below are examples for popular chatbots:

To add a new command in your chatbot for the route without role, use the following syntax:

=== "Nightbot"

    ```bash
    !addcom !randomagent $(urlfetch https://valo-api.vercel.app/random-agent)
    ```

=== "StreamElements"

    ```bash
    !cmd add !randomagent $(customapi https://valo-api.vercel.app/random-agent)
    ```

=== "Fossabot"

    ```bash
    !addcmd !randomagent $(customapi https://valo-api.vercel.app/random-agent)
    ```

=== "Streamlabs Chatbot"

    ```bash
    !command add !randomagent ${readapi https://valo-api.vercel.app/random-agent}
    ```

To add a new command in your chatbot for the route with role, use the following syntax (replace `<role>` with the desired role: `duelist`, `initiator`, `sentinel`, `controller` which can be queried in chat):

=== "Nightbot"

    ```bash
    !addcom !randomagent $(urlfetch https://valo-api.vercel.app/random-agent/$(1))
    ```

=== "StreamElements"

    ```bash
    !cmd add !randomagent $(customapi https://valo-api.vercel.app/random-agent/$(1))
    ```

=== "Fossabot"

    ```bash
    !addcmd !randomagent $(customapi https://valo-api.vercel.app/random-agent/$(1))
    ```

=== "Streamlabs Chatbot"

    ```bash
    !command add !randomagent ${readapi https://valo-api.vercel.app/random-agent/${1}}
    ```

### Example Message Requests in Chat

- `!randomagent` - Returns a random Valorant agent.
- `!randomagent duelist` - Returns a random Valorant duelist agent.
- `!randomagent initiator` - Returns a random Valorant initiator agent.
