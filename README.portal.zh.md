> _Read this in another language: [English](README.md)_

## 灵动课堂 classroom_sdk

## 拉取模块代码，安装依赖项
```bash
yarn install:packages (nodejs 版本建议16及一下)
# 如果依赖装不上，确保分支正确，拉取代码时是否有token
# package.json.resolution是否有"@types/node": "20.11.15"，没有则加上
```

## 如何使用自己的 AppId 和 Secret 生成 RtmToken（portal项目已配置好）
```bash
# 如果.env 文件中包含 `REACT_APP_AGORA_APP_ID` 和 `REACT_APP_AGORA_APP_CERTIFICATE` 配置，客户端会为你自动生成 RTM Token
REACT_APP_AGORA_APP_ID=
REACT_APP_AGORA_APP_CERTIFICATE=
```

## 打包时.env如果没有以下配置，粘贴过去
```bash
# 测试
REACT_APP_AGORA_APP_ID='21d015747d8543f5bc70f182d82eeb94'
REACT_APP_AGORA_APP_CERTIFICATE='f807d3ed99ca4b8eb260424fc9053c5e'
# 正式
# REACT_APP_AGORA_APP_ID='7e527cb3f3554a828093f7f81716c32b'
# REACT_APP_AGORA_APP_CERTIFICATE='3b267676579e4de68c7fd175e28903f4'
REACT_APP_SHARE_LINK_PREFIX=
REACT_APP_AGORA_APP_ASSETS_CDN=https://solutions-apaas.agora.io/static
REACT_APP_RECORDING_LINK_PREFIX=https://solutions-apaas.agora.io/apaas/record
```

## 运行灵动课堂开发调试(protal集成的修改一般运行这个)
```bash
yarn dev:classroom
```

## 打包 灵动课堂的修改 分别运行
```bash
yarn pack:classroom:sdk
yarn pack:classroom:plugin
# 修改的子模块要确保仓库远端地址正确和分支正确
```

## 运用sdk和plugin
```bash
# sdk: packages/agora-classroom-sdk/lib 下的 edu_sdk.bundle.js
# plugin: packages/agora-plugin-gallery/lib 下的 edu_widget.bundle.js
# 将这两个文件上传至OSS 测试：oss://dbcproduct/web/SW/flexible-classroom/test_new/
# 发版时可将这两个文件替换至：oss://dbcproduct/web/SW/flexible-classroom/prod/
# 同时需要修改protal index.html声网js的src地址
```