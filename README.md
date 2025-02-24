# docker-compose-files
分享一些 docker 容器 docker-compose 安装模板。

**注意：**

1. `.env`文件为一些敏感的环境变量值，包括用户名、密码、图标等自定义内容，可在此修改，内附说明。
2. 由于`docker-compse`默认会创建一个单独的网络，容器多了之后容易造成网络过多、地址空间用完、且使用`traefik`监听自动反向代理无法监听多个网络等问题，所以利用`networks`使用外部网络解决以上问题，`unet`为网络名，替换为自己需要的即可。若需要默认创建网络，删除所有的`networks`模块即可。
3. 若使用`traefik`，可使用`labels`标签来设置自动反向代理。`labels`标签中`net.unraid.docker.webui=${webui}`为 `unraid`的容器`webui`地址，`net.unraid.docker.icon=${icon}`为界面显示的图标地址。非`unraid`设备可删除这两个`label`。
