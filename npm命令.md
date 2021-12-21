1. 换源
```
#更换淘宝的镜像网址
npm config set registry http://registry.npm.taobao.org 
#查看当前镜像
npm get registry 
```

2. npm取消淘宝镜像
```
npm config delete registry
```

3. 设置http代理
```
npm config set proxy=http://代理服务器地址:8080
```

4. 取消代理
```
npm config delete proxy
```

5. 查看代理信息（当前配置）
```
npm config list
```