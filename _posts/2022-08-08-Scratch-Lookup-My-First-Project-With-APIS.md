---
title: "Scratch Lookup - My first project with APIs"
date: 2022-8-8
---


![image](https://scratch.mit.edu/images/scratch-og.png)

## The Idea

One day I was sitting at my computer bored and suddenly I thought:
> "What is there was a Scratch API. How funny would that be!"

So I went and searched it up on my computer. A Scratch [wiki](https://en.scratch-wiki.info/wiki/Scratch_Wiki_Home) page for it came up and it surprised me. I had some knowledge of APIs but no experience. I knew I had to create an app that uses the API.

## Scratch API

Scratch API, is an API like anything else but for [Scratch](https://scratch.mit.edu). The way it works is you go to a page you want an API for and you just change the subdomain to `api.scratch`. For example, if I wanted the API for my profile, I would go to `api.scratch.mit.edu/users/lasertag72` and at the page, it would return:
```
{
    "id": 39902949,
    "username": "lasertag72",
    "scratchteam": false,
    "history": {
        "joined": "2018-12-19T03:59:51.000Z"
    },
    "profile": {
        "id": 39027670,
        "images": {
            "90x90": "https://cdn2.scratch.mit.edu/get_image/user/39902949_90x90.png?v=",
            "60x60": "https://cdn2.scratch.mit.edu/get_image/user/39902949_60x60.png?v=",
            "55x55": "https://cdn2.scratch.mit.edu/get_image/user/39902949_55x55.png?v=",
            "50x50": "https://cdn2.scratch.mit.edu/get_image/user/39902949_50x50.png?v=",
            "32x32": "https://cdn2.scratch.mit.edu/get_image/user/39902949_32x32.png?v="
        },
        "status": "",
        "bio": "I'm retired \n\nstatus = %1\n\nnvm hehehehhe",
        "country": "United States"
    }
}
```

## Problems With Implementation

When I tried to access the API it gave me an error mentioning [Cross-origin resource sharing](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjTpY2fmbj5AhW8DkQIHfivCxgQFnoECAUQAQ&url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FHTTP%2FCORS&usg=AOvVaw2xmyG8mpAqKyMiOwPBDkob) or CORS. If you go to the finished project linked below then you'd see at the top with big red text it requires you to install [this](https://chrome.google.com/webstore/detail/cross-domain-cors/mjhpgnbimicffchbodmgfnemoghjakai?hl=en) to allow the project to access the API. I soon plan to figure out how to get the project to work without this extension but as of right now, you have to install the extension

## The Finished Project

You can see and contribute the finished project [here](https://github.com/nikhilhex/Scratch-Lookup).
