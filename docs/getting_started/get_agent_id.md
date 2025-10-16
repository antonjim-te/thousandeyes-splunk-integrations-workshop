# Get ThousandEyes Agent Id for the creation of the ThousandEyes HTTP test

When creation the ThousandEyes test you will need to select an agent.

## Search for a new agentId

- Use the following Bruno request to get the agents ![ThousandEyes get agents](../img/bruno/getAgents.png)
- In the response, search for an agent
    - E.g `Barcelona` or `Atlanta`

- Save the `agentId` into the variable `ThousandEyes_agent_id` in Bruno ![ThousandEyes agentId](../img/bruno/agent_id.png)
