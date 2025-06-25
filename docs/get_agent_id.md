# Get ThousandEyes Agent Id for the creation of the ThousandEyes HTTP test

When creation the ThousandEyes HTTP test you may see an error related to the agent.
We can use a different agentId.

## Search for a new agentId

- Use the following Postman request to get the agents ![ThousandEyes get agents](img/postman/getAgents.png)
- In the resposne, search for an agent
    - E.g `Barcelona`
- Save the `agentId` into the variable `ThousandEyes_agent_id` in Postman ![ThousandEyes agentId](img/postman/agentId.png)
