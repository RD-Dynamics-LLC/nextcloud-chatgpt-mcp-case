# From folders to dialogue: connecting Nextcloud to ChatGPT

**RD Dynamics LLC · Case · Engineering software · 26 September 2026**

A private MCP gateway lets engineers search and read documents from a conversation while keeping access scoped to an allowed part of Nextcloud.

In engineering work, the right document often exists, but finding it takes time: recall a name, browse folders, choose the right revision, then return to the task. RD Dynamics LLC tested another route. A user asks a question in ChatGPT and a connected tool queries an allowed area of Nextcloud.

Source files remain in the company storage. The conversation receives only the result of a specific permitted request: search matches, extracted text from a selected document, or a folder listing. This shortens the path from a question to its source.

## Three operations with a bounded scope

| Tool | What it does |
| --- | --- |
| `search` | Find indexed material by name or text marker. |
| `fetch` | Retrieve extracted content from a selected document. |
| `list_folder` | List indexed items in an allowed folder. |

## How it works

Our MCP gateway sits between ChatGPT and Nextcloud. It indexes the allowed area, enforces the configured access boundary, and uses Nextcloud interfaces to read metadata and content. In ChatGPT, it is a private MCP app in developer mode with the three tools above.

ChatGPT → Private tunnel → MCP gateway → Nextcloud

The connection uses OpenAI Secure MCP Tunnel. A client inside the private environment initiates an outgoing connection, so the gateway does not need an open incoming MCP port. The requested result is returned to the conversation; the source and access rules remain in the company environment.

## Where it helps

The interface is useful for design notes, calculation reports, revisions of technical descriptions, 3D printing documentation and research records. An engineer can find a note, open a selected item and inspect neighbouring files. The answer can be checked against the original in Nextcloud; the conversation simplifies navigation.

## What we verified

From ChatGPT, we completed three operations: a marker search, retrieval of content from an existing file, and a listing of an indexed folder. The gateway and indexer worked, the tunnel was available, and the external incoming MCP port remained closed.

The exposed tools cannot create, edit, move, delete or share files. The check did not modify Nextcloud data.

## Why we are sharing this

RD Dynamics LLC builds tools for its own engineering and research work and is ready to share solutions that may be useful to other teams. We welcome the practice of openly sharing developments and plan to publish new working tools in an open repository for adaptation and use in next-generation industry.

We are also actively designing robotic systems and developing new neural and graph models, including for unmanned devices.

More information about the company and our developments is available at [rddynamics.pro](https://rddynamics.pro/).

[Read this case on our website](https://rddynamics.pro/cases/nextcloud-chatgpt-en.html).

© 2026 RD Dynamics LLC. This repository contains the case study; gateway source code is not published here.
