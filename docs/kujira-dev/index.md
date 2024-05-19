--- 
title: Kujira Dev Playground
summary: Some Kujira Dev Resources
authors:
  - Joe (deving.zone)
date: 2024-05-07
#some_url: https://example.com
---

# Kujira Dev Playground

- <https://docs.kujira.app/developers/developer-kickstart-page>

![](img/sample-diagram.drawio)

### building blocks

## JavaScript / TypeScript

## Elixir

[//]: # ()
[//]: # (```python)

[//]: # (def fn&#40;&#41;:)

[//]: # (    pass)

[//]: # (```)

[//]: # ()
[//]: # (```)

[//]: # (Fenced code blocks are like Standard)

[//]: # (Markdown’s regular code blocks, except that)

[//]: # (they’re not indented and instead rely on)

[//]: # (start and end fence lines to delimit the)

[//]: # (code block.)

[//]: # (```)

## Architecture

INSERT NICE IMAGE OF STACK ^^ 
*Above: Cupcake indexer in progress*

## GIT Repositories

### pond

Pond is an easy way to set up a local Kujira development chain. It uses docker containers to set up two local Kujira chains, price feeder and an IBC relayer connecting both chains.

The second chain is meant to test IBC related things and therefore has only one validator and no price feeder.

<https://github.com/Team-Kujira/pond>



Feeder:  127.0.0.1:10171->10171/tcp
Kujira1-1:  127.0.0.1:10117->10117/tcp, 127.0.0.1:10156-10157->10156-10157/tcp, 127.0.0.1:10190->10190/tcp
Kujira2-1:  127.0.0.1:20117->20117/tcp, 127.0.0.1:20156-20157->20156-20157/tcp, 127.0.0.1:20190->20190/tcp


this config worked in https://github.com/Team-Kujira/explorer
> config :explorer, Explorer.Node, host: "localhost", port: 10190, websocket: "ws://localhost:10157"


### pond-ex

The quickest way to start building your app on the Kujira DeFi Blockchain

<https://github.com/Team-Kujira/pond-ex>


kujira-ex Docs https://hexdocs.pm/kujira
Kujira Developer Docs https://docs.kujira.app/developers/developer-kickstart-page
Phoenix Website: https://www.phoenixframework.org/
Phoenix Guides: https://hexdocs.pm/phoenix/overview.html
Phoenix Docs: https://hexdocs.pm/phoenix
Phoenix Forum: https://elixirforum.com/c/phoenix-forum

https://github.com/Team-Kujira/explorer

### FIN API

<https://github.com/Team-Kujira/fin-api>

### pond-images

https://github.com/Team-Kujira/pond-images/blob/main/feeder/Dockerfile


### Community Sample Repositories

https://github.com/jpKuji/kujira_walletconnect_js_next





@Developer as part of the Kujira Team's commitment to open-sourcing the core dApps, and building more robust, RPC-free, scalable infrastructure that allows better apps and better UX to be built, we've begun work on the API that we will migrate FIN to.

Instead of making dozens of individual RPC requests, requiring the UI client to determine which RPC it wants to connect to, and partially loading parts of each page at a time etc etc, this API will seek to build out interfaces that are built for the UI itself, and smartly scalable

The first endpoint is available at https://api.fin.kujira.network/api/contracts

The key difference here is that these are officially supported by the Kujira Team. The code is all open source at https://github.com/Team-Kujira/fin-api, so if it suits your needs for a FIN-related project, then it makes it super easy to clone and deploy your own backend (recommend http://gigalixir.com/ for git push related deploys), and we'll welcome community contributions

This also lays the groundwork for instant-updates of new FIN markets when proposals pass an PILOT sales complete. As a good demonstration of why a direct RPC architecture isn't scalable, this one endpoint requires around 300 individual gRPC calls to fetch token traces, metadata etc, but this very rarely, if ever, changes. This architecture allows us to invalidate the data in response to a MsgInstantiate for a FIN Code ID, instead of request it every-single-time a user loads FIN

Any questions fire away. We'll be building these out and adding new ones for the other apps over time
From our end, the first integration of this API will be into Sonar, to allow new FIN Pairs to be listed the second that proposals pass and PILOT sales are executed