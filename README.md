from datetime import datetime

username=input("enter the name")

lists='''
rice 40/kg
dal  20/kg
mirchi 40/kg'''
price=0
pricelist=[]
totalprice=0
qlist=[]
plist=[]
ilist=[]
finallist=[]

items={}
items={'rice':40,"dal":20,"colgate":40,"mirchi":90,"bajji":60}
option=int(input(" if you want know the items press 1:"))
if option==1:
  print(lists)
  for i in (items):
    inp1=int(input("enter 1 if you want to buy items or 2 to exit:"))
    if inp1==2:
        break
    if inp1==1:
       item=input("enter the item")
       quantity=int(input("enter the number of quantity"))
       if item in items.keys():
          price=quantity*(items[item])
          pricelist.append((items,price,item,quantity))
          totalprice+=price
          qlist.append(quantity)
          plist.append(price)
          ilist.append(item)
          gst=(totalprice*5)/100
          finalprice=gst+totalprice
       else:
          print("enterd the wrong item")        
    else:
       print("you have enterd wrong number")
    inp=input("enter yes if you want bill")
    if inp=="yes":
     pass
    if finalprice!=0:
      print(25*"=","reddy market",25*"=")
      print(28*"-","jangaon",28*"-")
      print("NAME:",username,8*"",datetime.now())
      print(75*"-")
      print("sno",8*"","list",8*"","quantity",3*"","price")
      for i in range (len(pricelist)):
       print(i,8*"",15*"",ilist,qlist,8*"",plist)
       print(75*"-")
       print(50*"=","Total amount",totalprice)
       print("gst",50*"",gst)
       print(75*"-")
       print(50*"","final amount",finalprice)
