# 硕士生框架

Frame <Master>
  AKO: <Student> //预定义槽名
  Major: Unit (Major) //专业
    If-Needed: Ask - Major //询问赋值
    If-Added: Check-Major //后续处理
  Field: Unit (Field) //方向
    If-Needed : Ask - Field //询问赋值
  Advisor: Unit (Last-name, First-name) //导师
    If-Needed : Ask -Visor //询问赋值
  Project: Area (National, Provincial, Other) //项目
    Default: National //缺省
  Paper: Area (SCI, EI, Core, General) //论文
    Default: Core //缺省
  这里，用到了一个系统预定义槽名AKO，其含义为"是一种"。
  当AKO作为下层框架的槽名时，其槽值为上层框架的框架名，表示该下层框架所描述的事物比其上层框架更具体。并且，由AKO所联系的框架之间具有属性的继承关系。