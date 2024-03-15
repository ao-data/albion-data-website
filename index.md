---
layout: default
title: Home
nav_order: 4
---
<p style="text-align: center;font-size: 30px">
      !! These tools are not affiliated with Albion Online !!
      <br>
      !! or Sandbox Interactive GmbH !!
</p>


# Welcome to the Albion Data Project!

The goal of this project is to collect and distribute realtime information for Albion Online. This is achieved with a 
downloadable client that monitors network traffic specifically for Albion Online, identifies the relevant information, 
and then ships it off to a central server which distributes the information to anyone who wants it.

[Click here to download the client.](https://github.com/ao-data/albiondata-client/releases)

[Client download stats](https://tooomm.github.io/github-release-stats/?username=ao-data&repository=albiondata-client)

<!-- # Contributing
This process is run on a [DigitalOcean Droplet](https://www.digitalocean.com) in order to ensure almost perfect uptime 
and high performance for the users. If you find this project beneficial to you then please consider a donation, thanks!! -->


# Player Information
If you would like to help the Albion Data Project, and all the web sites and applications that use the data provided by 
it, then the best thing you can do is download our client and run it whenever you're playing Albion Online.

The most recent releases can be found here: [https://github.com/ao-data/albiondata-client/releases](https://github.com/ao-data/albiondata-client/releases)

# Where Can I View The Data I Upload?
> Note that the client can only upload the market orders that you load in game, so be sure to browse the market for the 
prices that you need. When a price is uploaded, it is visible in the data immediately.

## The best way to make use of the data is by using the tools that are built on it:

- [Tools4Albion](https://www.tools4albion.com) provides calculators for crafting, farming, and reprocessing. Has a lot 
of useful information for users and developers alike.
- [Farm Profit Calculator](http://aofarm.skyline969.ca/) utilizes market data to provide a guide to the best farming 
options for you based on current prices.
- [Albion Helper](https://forum.albiononline.com/index.php/Thread/174675-Beta-Albion-Helper-Discord-Market-Bot-Crafting-Calculator/#post1270471)
 (forked from Albion Assistant) A discord bot to retrieve prices from Albion Online Data Project APIs. Maintained by Discord User Divined#9833.
- [Albionix Tools](https://albionix.app/) is a calculator for Transporting Item profitability and some market analysis. Maintained by Discord User Kytavian#4406.
- [Albion Online Tools](https://albiononlinetools.com/) is a site with a bunch of tools for Albion Online users. Maintained by Discord User legita.
- [Albion Free Market](https://albionfreemarket.web.app/) is a platform where you can assess market prices, discover cost-effective gear and simulate crafting outcomes. It's brought to you by the JP CodeCraft team. 
- [Albion Online Grind](https://albiononlinegrind.com/) offers a multifaceted toolkit that empowers you to manage islands efficiently, organise your stored items seamlessly, create visual Avalonian road maps, stay on top of important timers, calculate item enchantments with ease, and maximise farming profits. And much more. Maintained by Discord User ummahusla.


If you have a project you'd like to have listed here, contact a maintainer in discord to talk about it.

## Market data can be also be obtained through the API
### API Host URLs

- Albion Online West Server: `https://west.albion-online-data.com`
- Albion Online East Server: `https://east.albion-online-data.com`

### API Enpoints
- [Swagger documentation available here](https://west.albion-online-data.com/api/swagger).
- Item IDs can be found in the [formatted metadata](https://github.com/ao-data/ao-bin-dumps/tree/master/formatted) items.txt or items.json files.
- Location IDs or String Names can be found in the [formatted metadata](https://github.com/ao-data/ao-bin-dumps/tree/master/formatted) world.txt or world.json files.

For any of the following URLs, `.json` is optional and is the default. For XML, replace `.json` with `.xml`.

- Current Prices (Table View): [`/api/v2/stats/view/T4_BAG,T5_BAG?locations=Caerleon,Bridgewatch&qualities=2`](https://west.albion-online-data.com/api/v2/stats/view/T4_BAG,T5_BAG?locations=Caerleon,Bridgewatch&qualities=2)
- Current Prices (JSON): [`/api/v2/stats/prices/T4_BAG,T5_BAG.json?locations=Caerleon,Bridgewatch&qualities=2`](https://west.albion-online-data.com/api/v2/stats/prices/T4_BAG,T5_BAG?locations=Caerleon,Bridgewatch&qualities=2)
- Historical Prices (sell orders only):
  - **New!** [`/api/v2/stats/history/T4_BAG,T5_BAG.json?date=2-5-2020&end_date=2-12-2020&locations=Caerleon&qualities=2&time-scale=6`](https://west.albion-online-data.com/api/v2/stats/history/T4_BAG?date=2-5-2020&end_date=2-12-2020&locations=Caerleon&qualities=2&time-scale=6)
  - **New!** Hourly (time-scale=1): [`/api/v2/stats/history/T4_BAG,T5_BAG.json?time-scale=1`](https://west.albion-online-data.com/api/v2/stats/history/T4_BAG?time-scale=1)
  - **New!** Daily (time-scale=24): [`/api/v2/stats/history/T4_BAG,T5_BAG.json?time-scale=24`](https://west.albion-online-data.com/api/v2/stats/history/T4_BAG?time-scale=24)
  - **New!** For charts: [`/api/v2/stats/charts/T4_BAG,T5_BAG.json?date=2-5-2020&end_date=2-12-2020&locations=Caerleon&qualities=2&time-scale=6`](https://west.albion-online-data.com/api/v2/stats/charts/T4_BAG?date=2-5-2020&end_date=2-12-2020&locations=Caerleon&qualities=2&time-scale=6)
- Gold Prices:
  - **New!** Over time: [`/api/v2/stats/gold.json?date=2-5-2020&end_date=2-12-2020`](https://west.albion-online-data.com/api/v2/stats/gold?date=2-5-2020&end_date=2-12-2020)
  - **New!** Most recent X prices: [`/api/v2/stats/gold.json?count=2`](https://west.albion-online-data.com/api/v2/stats/gold?count=2)
  
### API Endpoint Rate Limits

- 180 per 1 minute
- 300 per 5 minutes 

### "I WANT ALL THE DATA FROM THE API"

Well, you can. You just need to do it in a way that doesn't hit the API rate
limit. Combine the item's you want to get data on, as well as locations. 
There's a 4096 character limit for the url length. You can fit a lot of
items and all the locations in a single call.

Something like [this](https://west.albion-online-data.com/api/v1/stats/prices/T2_SHOES_CLOTH_SET1,T3_SHOES_CLOTH_SET1,T4_SHOES_CLOTH_SET1,T4_SHOES_CLOTH_SET1@1,T4_SHOES_CLOTH_SET1@2,T4_SHOES_CLOTH_SET1@3,T4_SHOES_CLOTH_SET1@4,T5_SHOES_CLOTH_SET1,T5_SHOES_CLOTH_SET1@1,T5_SHOES_CLOTH_SET1@2,T5_SHOES_CLOTH_SET1@3,T5_SHOES_CLOTH_SET1@4,T6_SHOES_CLOTH_SET1,T6_SHOES_CLOTH_SET1@1,T6_SHOES_CLOTH_SET1@2,T6_SHOES_CLOTH_SET1@3,T6_SHOES_CLOTH_SET1@4,T7_SHOES_CLOTH_SET1,T7_SHOES_CLOTH_SET1@1,T7_SHOES_CLOTH_SET1@2,T7_SHOES_CLOTH_SET1@3,T7_SHOES_CLOTH_SET1@4,T8_SHOES_CLOTH_SET1,T8_SHOES_CLOTH_SET1@1,T8_SHOES_CLOTH_SET1@2,T8_SHOES_CLOTH_SET1@3,T8_SHOES_CLOTH_SET1@4,T4_SHOES_CLOTH_SET2,T4_SHOES_CLOTH_SET2@1,T4_SHOES_CLOTH_SET2@2,T4_SHOES_CLOTH_SET2@3,T4_SHOES_CLOTH_SET2@4,T5_SHOES_CLOTH_SET2,T5_SHOES_CLOTH_SET2@1,T5_SHOES_CLOTH_SET2@2,T5_SHOES_CLOTH_SET2@3,T5_SHOES_CLOTH_SET2@4,T6_SHOES_CLOTH_SET2,T6_SHOES_CLOTH_SET2@1,T6_SHOES_CLOTH_SET2@2,T6_SHOES_CLOTH_SET2@3,T6_SHOES_CLOTH_SET2@4,T7_SHOES_CLOTH_SET2,T7_SHOES_CLOTH_SET2@1,T7_SHOES_CLOTH_SET2@2,T7_SHOES_CLOTH_SET2@3,T7_SHOES_CLOTH_SET2@4,T8_SHOES_CLOTH_SET2,T8_SHOES_CLOTH_SET2@1,T8_SHOES_CLOTH_SET2@2,T8_SHOES_CLOTH_SET2@3,T8_SHOES_CLOTH_SET2@4,T4_SHOES_CLOTH_SET3,T4_SHOES_CLOTH_SET3@1,T4_SHOES_CLOTH_SET3@2,T4_SHOES_CLOTH_SET3@3,T4_SHOES_CLOTH_SET3@4,T5_SHOES_CLOTH_SET3,T5_SHOES_CLOTH_SET3@1,T5_SHOES_CLOTH_SET3@2,T5_SHOES_CLOTH_SET3@3,T5_SHOES_CLOTH_SET3@4,T6_SHOES_CLOTH_SET3,T6_SHOES_CLOTH_SET3@1,T6_SHOES_CLOTH_SET3@2,T6_SHOES_CLOTH_SET3@3,T6_SHOES_CLOTH_SET3@4,T7_SHOES_CLOTH_SET3,T7_SHOES_CLOTH_SET3@1,T7_SHOES_CLOTH_SET3@2,T7_SHOES_CLOTH_SET3@3,T7_SHOES_CLOTH_SET3@4,T8_SHOES_CLOTH_SET3,T8_SHOES_CLOTH_SET3@1,T8_SHOES_CLOTH_SET3@2,T8_SHOES_CLOTH_SET3@3,T8_SHOES_CLOTH_SET3@4,T4_SHOES_CLOTH_KEEPER,T4_SHOES_CLOTH_KEEPER@1,T4_SHOES_CLOTH_KEEPER@2,T4_SHOES_CLOTH_KEEPER@3,T4_SHOES_CLOTH_KEEPER@4,T5_SHOES_CLOTH_KEEPER,T5_SHOES_CLOTH_KEEPER@1,T5_SHOES_CLOTH_KEEPER@2,T5_SHOES_CLOTH_KEEPER@3,T5_SHOES_CLOTH_KEEPER@4,T6_SHOES_CLOTH_KEEPER,T6_SHOES_CLOTH_KEEPER@1,T6_SHOES_CLOTH_KEEPER@2,T6_SHOES_CLOTH_KEEPER@3,T6_SHOES_CLOTH_KEEPER@4,T7_SHOES_CLOTH_KEEPER,T7_SHOES_CLOTH_KEEPER@1,T7_SHOES_CLOTH_KEEPER@2,T7_SHOES_CLOTH_KEEPER@3,T7_SHOES_CLOTH_KEEPER@4,T8_SHOES_CLOTH_KEEPER,T8_SHOES_CLOTH_KEEPER@1,T8_SHOES_CLOTH_KEEPER@2,T8_SHOES_CLOTH_KEEPER@3,T8_SHOES_CLOTH_KEEPER@4,T4_SHOES_CLOTH_HELL,T4_SHOES_CLOTH_HELL@1,T4_SHOES_CLOTH_HELL@2,T4_SHOES_CLOTH_HELL@3,T4_SHOES_CLOTH_HELL@4,T5_SHOES_CLOTH_HELL,T5_SHOES_CLOTH_HELL@1,T5_SHOES_CLOTH_HELL@2,T5_SHOES_CLOTH_HELL@3,T5_SHOES_CLOTH_HELL@4,T6_SHOES_CLOTH_HELL,T6_SHOES_CLOTH_HELL@1,T6_SHOES_CLOTH_HELL@2,T6_SHOES_CLOTH_HELL@3,T6_SHOES_CLOTH_HELL@4,T7_SHOES_CLOTH_HELL,T7_SHOES_CLOTH_HELL@1,T7_SHOES_CLOTH_HELL@2?locations=4,7,8,301,1002,1006,1012,1301,2002,2004,2301,3002,3003,3005,3008,3301,4002,4006,4300,4301,5003&qualities=1,2,3,4,5) (too big to show on the page!).

We also ask that if you are going to write a service that continually hits the
API, please use Gzip compression. The server and bandwidth isn't free and while
the monthly bandwidth limit hasn't been exceeded that we're aware of, the 
more people that use the project and it's API, the closer we get to overages.

### Spreadsheets

Many people find it useful to load these APIs in spreadsheets such as Microsoft Excel or Google Sheets. There is no 
single best way to do this, but some of the common ways are as follows:

- [Excel Power Query](https://support.office.com/en-us/article/introduction-to-microsoft-power-query-for-excel-6e92e2f4-2079-4e1f-bad5-89f6269cd605)
- [Google Sheets IMPORTXML](https://support.google.com/docs/answer/3093342?hl=en)
  - Example: `=IMPORTXML("https://west.albion-online-data.com/api/v2/stats/prices/T4_BAG.xml?locations=Caerleon&qualities=2","//ArrayOfMarketResponse/MarketResponse")`
- [Google Sheets ImportJSON (third-party script)](https://github.com/bradjasper/ImportJSON)
  - Note: Some people have noticed issues with ImportJSON and repeating rows
  - Example: `=ImportJSON("https://west.albion-online-data.com/api/v2/stats/prices/T4_BAG.json?locations=Caerleon&qualities=2", "", "noHeaders")`

# Related Albion Tools
- [Albion Online Stats - DPS tracker](https://github.com/mazurwiktor/albion-online-stats)

# Configuration
You can see all of the current available command line parameters by launching the executable with 
`"C:\Program Files\Albion Data Client\albiondata-client.exe" -h` or by adding `-h` to the shortcut.
## Parameters
At the time of writing the following are the available (well-supported) configuration options:
```
"C:\Program Files\Albion Data Client\albiondata-client.exe" -h
  -d	If specified no attempts will be made to upload data to remote server.
  -debug
    	Enable debug logging.
  -events string
    	Whitelist of event IDs to output messages when debugging. Comma separated.
  -events-ignore string
    	Blacklist of event IDs to hide messages when debugging. Comma separated.
  -i string
    	Base URL to send PUBLIC data to, can be 'nats://', 'http://' or 'noop' and can have multiple uploaders. Comma separated. (default is "http+pow://pow.west.albion-online-data.com" or "http+pow://pow.east.albion-online-data.com" determined by the game server you connect to)
  -ignore-decode-errors
    	Ignore the decoding errors when debugging
  -l string
    	Listen on this comma separated devices instead of all available
  -minimize
    	Automatically minimize the window.
  -no-limit
    	Use all available CPU cores
  -o string
    	Parses a local file instead of checking albion ports.
  -operations string
    	Whitelist of operation IDs to output messages when debugging. Comma separated.
  -operations-ignore string
    	Blacklist of operation IDs to hide messages when debugging. Comma separated.
  -output-file
    	Enable logging to file.
  -p string
    	Base URL to send PRIVATE data to, can be 'nats://', 'http://' or 'noop' and can have multiple uploaders. Comma separated.
  -record string
    	Enable recording commands to a file for debugging later.
```

## Disable Start With Windows
1. Open up the program `Task Scheduler`.
1. Click on the `Task Scheduler Library` in the left side pane.
1. Find the task with the name `Albion Data Client`.
1. Right-click `Disable` to disable the task.

# Troubleshooting

Starting the client via the command line will allow the error message to persist. 
- Windows
  - Open a run command prompt window with `WIN + r`
  - Enter `"C:\Program Files\Albion Data Client\albiondata-client.exe"`
  - View application output
- MacOS
  - Open a terminal `COMMAND + SPACE` and type `terminal`
  - Enter `/path/to/albiondata-client`
  - View application output
- Linux
  - Open a terminal (too many ways to list, if you use Linux, you should know how)
  - Enter `/path/to/albiondata-client`
  - View application output

## Client crashing
### Device/Adapter Errors

Includes the following Error Messages:
- "No such device exists"
- "Error opening adapter: The system cannot find the device specified. (20)"
- "eth0: You don't have permission to capture on that device (socket: Operation not permitted)" (Linux/MacOS specific)

This means the client can't attach it self to the network interface to capture Albion Online data.

- Windows
  - Open a command prompt
  - Type `ipconfig.exe /all`
  - Look for the network adapter that give's you connectivity and find the `Physical Address` line:![Alt text](images/ipconfig.png)
  - Start the client with the `-l` (lower case L) argument, replacing the physical address of your card: `"C:\Program Files\Albion Data Client\albiondata-client.exe" -l "B4-2E-99-31-90-E2"`
- MacOS
  - Open a terminal
  - Type `ifconfig`
  - Look for the network adapter that give's you connectivity and find the `Physical Address` line:![Alt text](images/macos-ifconfig.png)
  - Start the client with the `-l` (lower case L) argument, replacing the physical address of your card: `/path/to/albiondata-client -l "14:7D:DA:DB:C6:29"`
- Linux (essentially the same as MacOS)
  - Open a terminal
  - Type `ifconfig`
  - Look for the network adapter that give's you connectivity and find the `Physical Address` line:![Alt text](images/linux-ifconfig.png)
  - Start the client with the `-l` (lower case L) argument, replacing the physical address of your card: `/path/to/albiondata-client -l "7E-13-57-B4-C4-3B"`

### MacOS/Linux needs sudo

[Original developer discussing the issue.](https://github.com/regner/albiondata-client/issues/125)

Running the Albion Online Data client with sudo is the easiest way to get going. But, you can work around needing full sudo if you understand Linux/MacOS permssions.

The following has been copied and modified to fit this project's use.

Note: `aod` group is short for "Albion Online Data". You'll need to substitute `/path/to/albiondata-client` with the actual path to your client.

```
Add a capture group and add yourself to it:

Source: https://github.com/bettercap/bettercap/issues/783#issuecomment-1021912001
sudo groupadd aod
sudo usermod -a -G aod $USER

Next, change the group of tcpdump and set permissions:

sudo chgrp aod /path/to/albiondata-client
sudo chmod 750 /path/to/albiondata-client
```

## Client receives "HTTP Error while proving pow. returned 902" message (POW Expired/doesn't exist)

This means your Albion Online Data client is taking too long to send data to our servers. This is slowed down on
purpose because we ask your computer to do some math that our server already has the answer to. We needed to add
this because bad actors/spammers were sending us bad data and this slowed them down. With that, we wanted to make
sure we didn't eat up all CPU cycles on your machine, so we limit it to [25% CPU](https://github.com/ao-data/albiondata-client/blob/master/client/uploader_http_pow.go#L32).

If you wish to bypass this and let your entire CPU be consumed while searching Albion Online markets, you can add 
the [-no-limit](https://www.albion-online-data.com/#parameters) parameter when running the Albion Online Data client
manually. But... (read next section)

## Client receives “403 Forbidden” message

This means you have requested POW and/or sent POW result with data very fast recently. The rate limits can be found
[here](https://github.com/ao-data/albiondata-gate/blob/main/config.rb#L7). Note, everything is x2 because to send 1
successful chunk of data, your Albion Online Data client must request a POW then submit the POW result + data. So,
for example, per_minute is 270*2, which means you can send 270 chunks of data per minute before being throttled.

# Developer Information
If you're building something to consume the data published by the
Albion Data Project here are some things you will need to know:
- NATS Connection String:
  - West Game Server:  nats://public:thenewalbiondata@nats.albion-online-data.com:4222
  - East Game Server:  nats://public:thenewalbiondata@nats.albion-online-data.com:24222
- NATS Topics:
  - `goldprices.ingest` (all gold prices that come in from data clients, including all duplicates)
  - `marketorders.ingest` (all orders that come in from data clients, including all duplicates)
  - `markethistories.ingest` (all histories that come in from data clients, including all duplicates)
  - `goldprices.deduped` (deduped gold prices that come in from data clients, read below about duplicate messages)
  - `marketorders.deduped` (deduped orders prices that come in from data clients, read below about duplicate messages)
  - `markethistories.deduped` (deduped histories prices that come in from data clients, read below about duplicate messages)
- Structure of data messages: [albiondata-client/lib](https://github.com/ao-data/albiondata-client/tree/master/lib)

Note: Duplicate Messages - As information comes into the NATS Server it is looked at and deduplicated over a 10 minute
 window. As a subscriber the goal is that you should only get the same message once every 5 minutes. This is of course 
 open for change as we go however. The reason we are sending the same message at all is two fold.

Note: Timestamp on Market History data is in Ticks. To convert ticks to epoch (a more common time format), you would do the following:
`(638181504000000000 / 10000) - 62136892800000` which in this example is `1681257600000`. Using [https://www.unixtimestamp.com/](https://www.unixtimestamp.com/)
to convert `1681257600000` to a human readable format results in `Wed Apr 12 2023 00:00:00 GMT+0000`. This should be enough
info to get you going in the programming/scripting language of your choosing to convert the timestamp to something usable.

New people connecting to the network may have missed previous messages. Along with that however we don’t have a good way
 of noticing things like market orders completing. To remove market orders from your application the current best idea 
 around is to keep track of the last time an order was seen, and then after not seeing it for X hours remove it has 
 probably having been completed.

## Database Table Exports

You can find daily table dumps on the server at [https://www.albion-online-data.com/database/](https://www.albion-online-data.com/database/). 
The export contains a .sql file for each table, and a .zip file for each table that contains a tab-separated .txt data 
file which can be imported into MySQL using common tools.

## Albion Data Projects
- [albiondata-client](https://github.com/ao-data/albiondata-client)
- [albiondata-deduper-dotNet](https://github.com/ao-data/albiondata-deduper-dotNet)
- [albiondata-sql-dotNet](https://github.com/ao-data/albiondata-sql-dotNet)
- [albiondata-api-dotNet](https://github.com/ao-data/albiondata-api-dotNet)
- [AlbionData.Models](https://github.com/ao-data/albiondata-models-dotNet) [![NuGet](https://img.shields.io/nuget/v/AlbionData.Models.svg)](https://www.nuget.org/packages/AlbionData.Models/)
- [albion-data-website](https://github.com/ao-data/albion-data-website) (This website)

# Contact Us
The best way to get in touch with us is on the Albion Online Fansites Discord server in either the #proj-albiondata or 
the #developers channel. A permanent invite link can be found here: [https://discord.gg/TjWdq24](https://discord.gg/TjWdq24)

# Is This Allowed

{: .note }

> Our position is quite simple. As long as you just look and analyze we are ok with it. The moment you modify or 
manipulate something or somehow interfere with our services we will react (e.g. perma-ban, take legal action, whatever).

> ~MadDave, Technical Lead at Sandbox Interactive for Albion Online, [source](https://forum.albiononline.com/index.php/Thread/51604-Is-it-allowed-to-scan-your-internet-trafic-and-pick-up-logs/?postID=512670#post512670)
