#作业-1

 1. 程序功能介绍
 2. readme
 4. 代码

## 1.程序功能介绍
3级菜单：运行程序输出第一级菜单，选择一级菜单某项，输出二级菜单，同理输出三级菜单。有返回上一级菜单的功能，让用户选择是否要退出，菜单数据保存在文件中。
###2.readme
看着先后输出的菜单进行输入，按b能够返回上级菜单，虚返回最上层菜单后按d退出程序。

###代码
import json

xxl = {'北京': {'天安': {"东京": ["尸体", "大多数已经腐烂！"], "伟人": ["红旗", "升旗仪式！"]},
    '长城': {"地狱": ["恶魔", "种类多，各种奇葩都有！"], "天使": ["坠落", "翅膀毛掉光了！"]},
    '堵车': {'堵车': ["车多", "还不如两条腿走！"], '加塞': ["拥挤", "捞出车祸！"]}},
    '江苏': {'无锡': {'荟聚': ["吃喝", "购物休闲好地方！"]}, '常州': {'恐龙': ["侏罗纪", "体验恐龙时代"]},
    '苏州': {'sbs': ["电视", "电视塔新建在南施街地铁口附近"]}},
    '广东': {}, }

while True:
    for i in xxl:
        print(i)
    choise = input("按d退出程序或者选择进入1》：")
    if choise in xxl:
        while True:
            for i2 in xxl[choise]:
                print("\t", i2)
            choise2 = input("选择进入2》：")
            if choise2 in xxl[choise]:
                while True:
                    for i3 in xxl[choise][choise2]:
                        print("\t\t", i3)
                    choise3 = input("选择进入3》：")
                    if choise3 in xxl[choise][choise2]:
                        for i4 in xxl[choise][choise2][choise3]:
                            print("\t\t", i4)
                        choise4 = input("最后一层，按b返回》：")
                        if choise4 == "b":
                            pass
                    if choise3 == "b":
                        break
            if choise2== "b":
                break
        if choise == "b":
            break
    if choise == "d":
        f = open("dic.json", 'w', encoding="utf-8")
        json.dump(xxl, f)
        break

