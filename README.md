import webbrowser as wb
import datetime as dt
fh=open(r'e:\result2.rtf',"w")
today=dt.datetime.now()
fh.write(" ______________________________________________\n")
fh.write("|              Sri Durga Hotel                 |\n")
fh.write("|Date:                                         |\n")
fh.write("|"+str(today)+"                    |\n")
fh.write("|______________________________________________|\n")
fh.write("|sno| Item Name| Qty | unit Price|Total Price  |\n")
fh.write("|___|__________|_____|___________|_____________|\n")
print("________________________________________________________")
print("|1 Dosa|2 Idly |3 Puri|4 Vada |5 Upma |6 Pongal|7 Bonda|")
print("|Rs:30 |Rs: 10 |Rs: 30|Rs:10  |Rs:40  |Rs:40   |Rs:20  |")
print("|______|_______|______|_______|_______|________|_______|")
sum1=0
icount=0

def fun():
    print("Do you want any more items?")
    opt=input("(Y/N)")
    if opt=='Y' or opt=='y':
        return 1
    else:
        return 0
while(1):
    order=int(input("Enter your Item code:"))
    if(order==1):
        icount+=1
        iname="Dosa"
        nd=int(input("How many dosa you want?"))
        fh.write("|{} |{}|{}|Rs:30      |Rs:{}|\n".format(str(icount).center(3,' '),iname.center(10,' '),str(nd).center(4,' '),str(nd*30).center(10,' ')))
        sum1=sum1+nd*30
        res=fun()
        if res==0:
            break
    elif(order==2):
        icount+=1
        iname="Idly"
        ni=int(input("How many Idly you want?"))
        fh.write("|{} |{}|{}|Rs:10      |Rs:{}|\n".format(str(icount).center(3,' '),iname.center(10,' '),str(ni).center(4,' '),str(ni*10).center(10,' ')))
        sum1=sum1+ni*10
        res=fun()
        if res==0:
            break
    elif(order==3):
        icount+=1
        iname="Puri"
        np=int(input("How many puri you want?"))
        fh.write("|{} |{}|{}|Rs:30      |Rs:{}|\n".format(str(icount).center(3,' '),iname.center(10,' '),str(np).center(4,' '),str(np*30).center(10,' ')))
        sum1=sum1+np*30
        res=fun()
        if res==0:
            break
    elif(order==4):
        icount+=1
        iname="Vada"
        nv=int(input("How many Vada you want?"))
        fh.write("|{} |{}|{}|Rs:10      |Rs:{}|\n".format(str(icount).center(3,' '),iname.center(10,' '),str(nv).center(4,' '),str(nv*10).center(10,' ')))
        sum1=sum1+nv*10
        res=fun()
        if res==0:
            break
    elif(order==5):
        icount+=1
        iname="Upma"
        pu=int(input("How many plates of Upma you want?"))
        fh.write("|{} |{}|{}|Rs:40      |Rs:{}|\n".format(str(icount).center(3,' '),iname.center(10,' '),str(pu).center(4,' '),str(pu*40).center(10,' ')))
        sum1=sum1+pu*40
        res=fun()
        if res==0:
            break
    elif(order==6):
        icount+=1
        iname="Pongal"
        po=int(input("How many plates of pongal you want?"))
        fh.write("|{} |{}|{}|Rs:40      |Rs:{}|\n".format(str(icount).center(3,' '),iname.center(10,' '),str(po).center(4,' '),str(po*40).center(10,' ')))
        sum1=sum1+po*40
        res=fun()
        if res==0:
            break
    elif(order==7):
        icount+=1
        iname="Bonda"
        bo=int(input("How many bonda's you want?"))
        fh.write("|{} |{}|{}|Rs:20      |Rs:{}|\n".format(str(icount).center(3,' '),iname.center(10,' '),str(bo).center(4,' '),str(bo*20).center(10,' ')))
        sum1=sum1+bo*20
        res=fun()
        if res==0:
            break
    else:
        print("Invalid entry")
        res=fun()
cgst=(sum1*12/100)
sgst=(sum1*18/100)
asum1=(sum1+cgst+sgst)
fh.write("|____|__________|____|___________|_____________|\n")
fh.write("|Your Bill Amount is : Rs:{}                  |\n".format(sum1))
fh.write("|CGST 12% is         : Rs:{}                   |\n".format(int(cgst)))
fh.write("|SGST 18% is         : Rs:{}                   |\n".format(int(sgst)))
fh.write("|Amount Payable is   : Rs:{}                  |\n".format(int(asum1)))
fh.write("|______________________________________________|\n")
fh.write("|            THANK YOU VISIT AGAIN             |\n")
fh.write("|______________________________________________|\n")
fh.write("|sai durga hotel near mgb felicity mall,nellore|\n")
fh.write("|for more updates please contact:9897684321    |\n")
fh.write("|______________________________________________|\n")
fh.write("|      Email ID:durgahotel@gmail.com           |\n")
fh.write("|______________________________________________|\n")
fh.close()
print("Your bill amount is:",sum1)
em=input("Enter 1 for To print the bill or else press any key")
if(int(em)!=1):
    wb.open_new(r'e:\HOTELmanagement.py')
elif(int(em)==1):
    wb.open_new(r'e:\result2.rtf')
else:
    print("program terminated.")
