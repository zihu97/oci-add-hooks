Usage可见README.md

从func processBundle看--bundle <path/to/bundle>是必须的

通过序列化config.json和hook-config.json，然后通过mergeHook+merge进行合并，再通过writeFile回写config.json

实际上该tool完成的就是将hook插入config.json，是runc的wrapper，做一些定制化的操作，然后通过配置/etc/docker/daemon.json中的"runtimes"使得docker engine可以用到该low level runtime