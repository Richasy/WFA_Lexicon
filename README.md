# WFA词库说明

> 感谢你的使用，希望我没有做好的事，能在你手里做得更好
———— Richasy.云之幻

目前为适配新版本WFA，词库已经转向新版本。

## 文件说明

1. `WF_Dict`: 包含了游戏所需的绝大部分字段、名称、物品的翻译
2. `WF_Invasion`: 特化后的入侵奖励翻译，包含所有的入侵任务奖励
3. `WF_Lib`: 资料库索引，每一个物品的特殊标识是`uniqueName`，`type`表示该物品的所属类别
4. `WF_NightWave`: 午夜电波翻译表，对应的所有任务名和任务描述的翻译
5. `WF_Sale`: 从Warframe Market直接获取的所有可售卖物品的清单，未来会逐步完成翻译工作
6. `WF_Riven`, `WF_AllRiven`: 前者包含所有有效的紫卡武器，后者则包括这些武器的变体，比如Prime或者赤毒版本等。`rank`表示裂罅倾向性的等级，`modulus`表示计算系数

---

## 如何使用图片

**显示Lib中的图片**

你可以通过`WF_Lib`中的`thumb`字段获取图片名，如果要显示图片，你需要加上前缀：

`https://cdn.warframestat.us/img/${item.thumb}`

国内用户访问该网址可能不太能连得上，你可以考虑前往[WFCD/warframe-items](https://github.com/WFCD/warframe-items)中下载所有图片，并自行托管。

**显示Sale中的图片**

图片链接加上前缀后如下：

`https://warframe.market/static/assets/${item.thumb}`

## 配合API

词库需要配合WFA的API使用才能达到最大化的效果。

- API文档：[API介绍](https://www.richasy.cn/document/wfa/data/)
- SDK(C#): [WFA SDK](https://github.com/Richasy/WFA-SDK)

其中，SDK包含了对词库文件的转化方法：

```csharp
List<Dict> dicts = client.ParseDictJson(dictString);
```

## 其它

为了压缩文件体积，提高下载速度，所有的json文件去除了格式，以紧密方式排布，不考虑可读性。    