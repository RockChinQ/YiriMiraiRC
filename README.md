# YiriMirai

[![Licence](https://img.shields.io/github/license/YiriMiraiProject/YiriMirai)](https://github.com/YiriMiraiProject/YiriMirai/blob/master/LICENSE)
[![PyPI](https://img.shields.io/pypi/v/yiri-mirai)](https://pypi.org/project/yiri-mirai/)
![Python Version](https://img.shields.io/pypi/pyversions/yiri-mirai)
[![Document](https://img.shields.io/badge/document-vercel-brightgreen)](https://yiri-mirai.vercel.app)

一个轻量级、低耦合度的基于 mirai-api-http 的 Python SDK。

**本项目适用于 mirai-api-http 2.X 版本**。

目前仍处于开发阶段，各种内容可能会有较大的变化。

## 安装

从 PyPI 安装：

```shell
pip install yiri-mirai
# 或者使用 poetry
poetry add yiri-mirai
```

此外，你还可以克隆这个仓库到本地，然后使用 `poetry` 安装：

```shell
git clone git@github.com:Wybxc/YiriMirai.git
cd YiriMirai
poetry install
```

## 使用

```python
from mirai import Mirai, FriendMessage, WebSocketAdapter

if __name__ == '__main__':
    bot = Mirai(12345678, adapter=WebSocketAdapter(
        verify_key='your_verify_key', host='localhost', port=6090
    ))

    @bot.on(FriendMessage)
    async def on_friend_message(event: FriendMessage):
        if str(event.message_chain) == '你好':
            await bot.send(event, 'Hello World!')

    bot.run()
```

更多信息参看[文档](https://yiri-mirai.vercel.app/)。

## 社区

QQ 群：766952599（[链接](https://jq.qq.com/?_wv=1027&k=PXBOuBCI)）

Github Discussion（[链接](https://github.com/YiriMiraiProject/YiriMirai/discussions)）

Discord（[链接](https://discord.gg/RaXsHFC3PH)）

## 开源协议

由于 mirai 及 mirai-api-http 均采用了 AGPL-3.0 开源协议，本项目同样采用 AGPL-3.0 协议。

请注意，AGPL-3.0 是传染性协议。如果你的项目引用了 YiriMirai，请在发布时公开源代码，并同样采用 AGPL-3.0 协议。
