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
PWOTE allows and accepts both `POST` and `GET` requests to process requests for quicktasks and premade tasks. To process these quick tasks, we use URL parameters for quick tasks and premade tasks, `QT` and `PT` respectively with support for URL chaining accessable. 

```http
https://pwote.co/?qt=<site>&q=<parameters>

OR 

https://pwote.co/?pm=<site>&q=<parameters>
```
