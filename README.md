mian函数

```Python
 import tools
while True:
    # TODO 显示菜单功能
    tools.show_menu()
    str_act=input("选择希望执行的操作")
    print("选择的操作是 %s" %str_act)
    if str_act in["1","2","3"]:
        if str_act=="1":
            tools.add_card()
        elif str_act=="2":
            tools.show_card()
        elif str_act=="3":
            tools.search_card()
    elif str_act=="0":
        print("已退出该系统") # 为0是退出
        break
    else:
        print("不在该数值内")

```

tools函数

```Python
card_list=[]
def show_menu():
    print("*"*50)
    print("名片管理系统")
    print("1 新增名片")
    print("2 显示名片")
    print("3 搜索名片")
    print("0 退出系统")
    print("*" * 50)
def add_card():
    print("*"*50)
    print("新增名片")
    name=input("输入姓名：")
    phone_num=input("输入电话号：")
    card_dict={"key_name":name,
               "key_num":phone_num}
    card_list.append(card_dict)
    #print(card_list)
    print("新增%s成功"%card_dict)
def show_card():
    if len(card_list)==0:
        print("未存在名片")
    else:
        print("显示名片")
        for card_dict in card_list:
            print(card_dict["key_name"],card_dict["key_num"])
            #Sprint(card_dict)
            #print(card_dict)
         #   print(card_dict["key_name"],["key_num"])

def search_card():
    print("查询名片")
    find_name=input("查询姓名")
    for card_dict in  card_list:
        if card_dict["key_name"]==find_name:
            print(card_dict["key_num"])
            break
    else:
        print("未找到%s",find_name)

```
