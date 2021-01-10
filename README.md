![](https://pbs.twimg.com/profile_banners/1123765884680585218/1596774649/1500x500)

## Usage
This quicktask documentation covers and supports versions 4.4.9A of PWOTE and onwards. Older versions of PWOTE or expiremental versions may not cover or use quick tasks or premade tasks like presented in this documentation. 

Quick Tasks and Premade Tasks allow users to create and start tasks from anywhere in the world. 

### Supported Sites
- [US/CA Footsites](#footsites)
- [Finishline](#finishline)
- [JD Sports](#jdsports)
- [Yeezysupply](#yeezysupply)
- [Snipes USA](#snipes)
- [Crocs USA](#crocs)
- [Nike Desktop](#nike)

## Format
PWOTE allows and accepts both `POST` and `GET` requests to process requests for quicktasks and premade tasks. To process these quick tasks, we use URL parameters for quick tasks with support for URL chaining accessable. 

```http
https://pwote.co/?qt=<site>&q=<query>
```

|   Query   |  Description              | Required?              | Default              | Example |
|-----------|---------------------------|------------------------|----------------------|----------------------|
| `kw`      |  Keyword/URL              | Required without `pid` |                      | `https://pwote.co/?qt=ftlus&kw=+yeezy,+350,+boost,-700` |
| `id`      |  Product ID               | Required without `key` |                      |
| `s`       |  Product Size             | Optional               | `random`             |
| `style`   |  Product Style            | Needed for FNL/JD      |                      |
| `pl`      |  Proxy List               | Optional               |  First List In Bot   |
| `mode`    |  Task mode                | Optional               |  `safe`              |
| `start`   |  Should Tasks Auto Start  | Optional               |  `true`              |
| `st`*     |  Start Time of Tasks      | Optional               |                      |

