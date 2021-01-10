![](https://pbs.twimg.com/profile_banners/1123765884680585218/1596774649/1500x500)

## Usage
This quicktask documentation covers and supports versions 4.4.9A of PWOTE and onwards. Older versions of PWOTE or expiremental versions may not cover or use quick tasks or premade tasks like presented in this documentation. 

Quick Tasks and Premade Tasks allow users to create and start tasks from anywhere in the world. 


## Format
PWOTE allows and accepts both `POST` and `GET` requests to process requests for quicktasks and premade tasks. To process these quick tasks, we use URL parameters for quick tasks with support for URL chaining accessable. 

```http
https://pwote.co/?qt=<site>&q=<query>
```

|   Query   |  Description              | Required?              | Default              | Example |
|-----------|---------------------------|------------------------|----------------------|----------------------|
| `kw`      |  Keyword/URL              | Required without `pid` |                      | `https://pwote.co/?qt=ftlus&kw=+yeezy,+350,+boost,-700` |
| `id`      |  Product ID               | Required without `key` |                      | `https://pwote.co/?qt=ftlus&id=55088118`
| `s`       |  Product Size             | Optional               | `random`             | `https://pwote.co/?qt=ftlus&id=55088118&s=9.5 (single size)` `https://pwote.co/?qt=ftlus&id=55088118&s=7-10.5 (size range)` | 
| `style`   |  Product Style            | Required for FNL/JD      |                      | `https://pwote.co/?qt=fnlus&id=prod1360195&style=555088` |
| `pl`      |  Proxy List               | Optional               |  First List In Bot   | `https://pwote.co/?qt=ftlus&id=55088118&pl=1 (first list)` `https://pwote.co/?qt=ftlus&id=55088118&pl=proxy-list.json (specific)` |
| `mode`    |  Task mode                | Optional               |  `safe`              | `https://pwote.co/?qt=ftlus&id=55088118&mode=fast2` |
| `cs`      | Captcha Sharing Method    | Optional               |  `none`              | `https://pwote.co/?qt=ftlus&id=55088118&cs=cm` | 
| `start`   |  Should Tasks Auto Start  | Optional               |  `true`              | `https://pwote.co/?qt=ftlus&id=55088118&start=true` | 
| `st`^     |  Start Time of Tasks      | Optional               |                      | `https://pwote.co/?qt=ftlus&id=55088118&st=1610298110` | 
^ Start time needs to be in UNIX time. 

### Captcha Sharing
We use the term "Captcha Sharing" as a universal term for apis and captcha sharing. 
| Captcha API Name | Code | 
|------------------|------|
| Captcha Monster  | `cm` |
| 2Captcha         | `2c` | 
| AntiCaptcha      | `ac` | 
| In-House API (preferred) | `api` | 

### Site Codes and Modes
To make it easier for the developers, we decided to add "site codes" as aliases for our sites. These site codes must be used in quick tasks and developers *cannot* use the actual site names. At the time of writing this, all modes are supported with quick tasks, including the new modes in the 1.0 version of our bot. These modes work directly with the `mode` query shown above. 

| Code                | Site             | Modes Supported | Captcha Source Supported? |
|--------------------|-------------------|-------------------|-------------------|
| `ftlus` | Footlocker US (Footsites) | `fast1`, `fast2`, `safe`, `safeqit` | Yes | 
| `ftlca` | Footlocker CA (Footsites) | `fast1`, `fast2`, `safe` | Yes |
| `ftac` | Footaction (Footsites) | `fast1`, `fast2`, `safe`, `safeqit` | Yes | 
| `ftea` | EastBay (Footsites) | `fast1`, `fast2`, `safe`, `safeqit` | Yes | 
| `ftch` | ChampsSports (Footsites) | `fast1`, `fast2`, `safe`, `safeqit` | Yes | 
| `fnlus` | Finishline US | `release`, `safe` | Yes | 
| `jdus` | JDSports US | `release`, `safe` | Yes | 
| `snipes` | Snipes USA | `fast`, `safe`, `fastqit`, `safeqit` | No |
| `crocs` | Crocs USA | `fast`, `safe`, `fastqit`, `safeqit` | No |
| `ys` | Yeezysupply | `normal`, `advanced` | Yes |
| `nf` | Nike Desktop Frontend | `fast` | No |
| `nb` | Nike Desktop Backend | `fast`, `safe` | No | 

### Link Quicktasks
We also support using URL's to create quicktasks. With URL quicktasks, we only support starting as soon as the request is recieved, but this may be easier for monitor developers. 

```
https://pwote.co/?qt= (URL)
https://pwote.co/?qt=https://www.eastbay.com/en/product/~/55088118.html
```

You can also use this method to quickly link change all of the tasks, here is an example:
```
https://pwote.co/?qt=lc&url=https://www.eastbay.com/en/product/~/55088118.html (all Eastbay tasks)
https://pwote.co/?qt=lc&id=55088118 (all tasks)
https://pwote.co/?qt=lc&site=ftea&id=55088118 (all Eastbay tasks)
```
