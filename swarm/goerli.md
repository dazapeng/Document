
# Centos7下以太坊测试网goerli的RPC服务器搭建

### 相关阅读
##### [Centos7 快速安装 Swarm Bee(含多节点启动脚本)](bee.md)
##### [Centos7 安装 Swarm Bee](https://xidusoft.com/?p=205)
##### [Swarm/Bee 相关资源链接](https://xidusoft.com/?p=46)
##### [Swarm/Bee 相关资源链接](https://xidusoft.com/?p=46)
##### [Bee 节点常用命令](https://xidusoft.com/?p=53)
##### [Swarm节点管理平台操作手册](https://xidusoft.com/?p=217)

## (1) 硬件要求
```
2核心4G内存，1M带宽，50G硬盘，有可能会内存不够闪退，可以加1G的swap交易分区

商业化应用建议 2核心8G以上，5M带宽。
```
## (2) bin包下载
### 官网下载指定系统的包 https://geth.ethereum.org/
```
wget https://gethstore.blob.core.windows.net/builds/geth-linux-amd64-1.10.3-991384a7.tar.gz

```

## (3) 安装启动
```
mkdir /data/geth

wget https://gethstore.blob.core.windows.net/builds/geth-linux-amd64-1.10.3-991384a7.tar.gz

cd /data/geth
tar zxvf geth-linux-amd64-1.10.3-991384a7.tar.gz
mv geth-linux-amd64-1.10.3-991384a7 bin

nohup ./bin/geth --datadir /data/geth/goerli \
--goerli --rpc --rpcapi "admin,debug,eth,miner,net,personal,txpool,web3" \
--port "30303" --cache=4096 --rpcport 8545 \
--rpcaddr 0.0.0.0 \
--maxpeers 999 --maxpendpeers 999 > output.log 2>&1 &

```

## (4) 防火墙开通8545对指定的节点IP可

## (5) 测试是否同步成功
```
./bin/geth attach http://localhost:8545

返回false为同步完成。

```

 
