该项目为通过[OnlineJudge 2.0](https://github.com/QingdaoU/OnlineJudge)二次开发得到的

目的是去掉多余的功能, 只保留最精简最核心的内容.

# 部署方法



1. 安装必要的依赖

   ```
   sudo apt-get update && sudo apt-get install -y vim python-pip curl git
   pip install docker-compose
   ```

2. 安装 Docker

   国内用户使用脚本一键安装: `sudo curl -sSL https://get.daocloud.io/docker | sh`
   国外用户使用脚本一键安装: `sudo curl -sSL get.docker.com | sh`

3. 下载项目

   ```
   git clone https://github.com/JFJeffreyWang/Mini-Hackathon.git
   ```

4. 启动服务

   ```
   cd Mini-Hackathon/OnlineJudgeDeploy
   docker-compose up -d
   ```
# 使用

   超级管理员默认账号 `root` 密码 `rootrootroot`

# 前端二次开发

1. 在`front_end/src`中进行二次开发

2. 运行`npm run dev`可以在本地部署和预览前端

3. 运行`npm run build`可以得到一个dist文件夹

   将 `dist` 文件夹复制到服务器上某个目录下，比如 `/data/OnlineJudgeDeploy/data/backend/dist`，然后修改 `docker-compose.yml`，在 `oj-backend` 模块中的 `volumes` 中增加一行 `- /data/OnlineJudgeDeploy/data/backend/dist:/app/dist` （冒号前面的请修改为实际的路径），然后 `docker-compose up -d` 即可。