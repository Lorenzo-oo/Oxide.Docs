---
title: Web Requests
after: timers
---

<script setup>
    import GithubLink from '../../../components/GithubLink.vue'
</script>

<GithubLink 
    link="https://github.com/OxideMod/Oxide.Core/blob/develop/src/Libraries/WebRequests.cs" 
    topPosition="10px" 
    leftPosition="330px" 
/>

# Web Requests Library

## `Enqueue`

The `Enqueue` method is used for sending `GET`, `POST`, `PUT`, `DELETE` and `PATCH` requests, the method also supports `Headers` which can be supplied via the arguments. The `timeout` argument is in seconds (`0` uses the 30 second default).

::: details Github Location
[`Enqueue`](https://github.com/OxideMod/Oxide.Core/blob/develop/src/Libraries/WebRequests.cs)
:::
