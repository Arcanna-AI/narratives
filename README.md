# Narratives
Narratives are Arcanna's take on creating and sharing reusable, *modifiable* prompts and simple agents that are included within the Arcanna platform and invokable via AI Assistant.
They are intended to be encompassed within one prompt, though the level of functionality and autonomy can vary substantially. 
Any time tool use is required by the Narrative, it will leverage Anthropic's _Model Context Protocol_ (MCP) for communication.

The goals of open-sourcing this repository are to:
* share what you'll get out of the box when trying/buying Arcanna
* enable others to suggest improvements or request new Narratives
* build in a transparent way that users of our platform can inspect

As part of our core ethos of transparency and customization, users can also **build their own Narratives** within the Arcanna platform.

## Narrative Format
This repository is intended to capture Narratives in YAML format that will make them easy to understand and easy to import to/export from Arcanna.
All Narratives will be organized by the first tag they are assigned within the platform, which will correlate with different functions within the SOC.

To have a valid Narrative, you must provide the following data in YAML format:

```yaml
name: "Name of Your Narrative"
author: "Your name or other attribution information"
description: |
  Describe your narrative in a clear and concise way so that others know what it does, any known limitations, and when to use it.
tags:
  - tags-like-this
  - one-per-line
tools: [which_mcp_tools_are_allowlisted]
prompt: |
  Your prompt goes here.
```

Note that tools should be comma-separated. If you do not want to restrict the set of tools that a Narrative can access, you can specify `[*]` as the list. This will appear within Arcanna's AI Assistant as an empty list.
