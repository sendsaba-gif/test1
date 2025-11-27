# test1# menu={
#     "items":[
#         {"item_number":1, "name":"chips", "price":1.50},
#         {"item_number":2 ,"name":"chocolate bar", "price":2.30},
#         {"item_number":3, "name":"cola", "price":200},
#         {"item_number":4 ,"name":"juice", "price":2.50}
        
#     ],
# }


menu={
        1:{"name":"chips", "price":1.50},
        2 :{"name":"chocolate bar", "price":2.30},
        3 :{"name":"cola ", "price":2.30},
        4 :{"name":"juice", "price":2.30},
}

cart = []

print("-----")
print("Welcome to our vending machine")
for key,value in menu.items():
    print(f"{key} - {value.get('name')} - ${value['price']} ")

while True:
    choice  = input("pick one item from  the machine or type done to exit/finish: ")

    if choice.lower() == 'done':
        break

    try:
        item_num = int(choice)
        if item_num in menu:
            cart.append(menu[item_num])
            print(f"Added {menu[item_num]["name"]}")
        else:
            print("Invalid choice!")

    except ValueError:
        print("please enter a valid input")


print("Receipt")

total = sum(item['price'] for item in cart)
for item in cart:
    print(f"{item['name']} - ${item['price']}")
print(total)

