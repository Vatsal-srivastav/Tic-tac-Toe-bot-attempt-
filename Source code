a={'a1':'_','a2':'_','a3':'_'}
b={'b1':'_','b2':'_','b3':'_'}
c={'c1':'_','c2':'_','c3':'_'}
r1={'a1':'_','b1':'_','c1':'_'}
r2={'a2':'_','b2':'_','c2':'_'}
r3={'a3':'_','b3':'_','c3':'_'}
x={'a1':'_','b2':'_','c3':'_'}
z={'a3':'_','b2':'_','c1':'_'}
l=[a,b,c,r1,r2,r3,x,z]
board=[r1,r2,r3]
corner=['a1','c1','a3','c3']
edges=['a2','b1','c2','b3']
turns=0
trick=False
s=input('will you make first move? (y/n)')
if (s=='y'):
    print ('  a b c')
    for i in board:
        if i == r1:
            print('1',end=' ')
        if i == r2:
            print('2',end=' ')
        if i == r3:
            print('3',end=' ') 
        for y in i:
              print (i[y],end=' ')
        print(' ')
    pm=input('What will you play?')
    for i in l:
        if pm in i:
            i[pm]='x'
    print('you played :',pm) 
    turns+=1
game=True
while (game==True): 
      print ('  a b c')
      for i in board:
          if i == r1:
            print('1',end=' ')
          if i == r2:
            print('2',end=' ')
          if i == r3:
            print('3',end=' ') 
          for y in i:
              print (i[y],end=' ')
          print(' ')
      moves={'b2':0,'a1':0,'c1':0,'a3':0,'c3':0,'a2':0,'b1':0,'c2':0,'b3':0}
      for i in l:
         val=tuple(dict.values(i))
         t=val.count('o')
         f=val.count('x')
         if(t==2)and(f==0):
             for j in i:
                 moves[j]+=50
         if(t==0)and(f==2):
             for j in i:
                 moves[j]+=40
         if(t==0)and(f==1):
             for j in i:
                 moves[j]+=3
         if(t==1)and(f==0):
             for j in i:
                 moves[j]+=2
         if(t==0)and(f==0):
             for j in i:
                 moves[j]+=1
         else:
             for j in i:
                 moves[j]-=1     
      if (turns==0) and (s=='n'):
          moves['a1']=40
      if (turns==2) and (s=='n') and (pm not in corner):
          moves['c3']=40  
      if (turns==2) and (s=='n') and (pm=='c2'):
          moves['c1']=40
      if (turns==2) and (s=='n') and (pm=='b3'):
          moves['a3']=40
      if (turns==2) and (s=='n') and (pm=='b1'):
          moves['a3']=40
      if (turns==2) and (s=='n') and (pm=='a2'):
          moves['c1']=40
      if (turns==2) and (s=='n') and (pm in corner):
          moves['c1']=40
          moves['a3']=40
      if ((s=='y') and (pm in corner)):
          lm=pm
          s=' '
          trick=True
      if ((turns==3) and (trick==True)):
          if ((lm in z) and (pm in z)):
              moves['b1']=40
          if ((lm in x) and (pm in x)):
              moves['b1']=40
      for i in board:
          for j in i:
              if (i[j]=='o') or (i[j]=='x'):
                  moves[j]-=99
      max=-99999999
      for i in moves:
         if moves[i]>max:
             max=moves[i]
             sm=i
      print('it played :',sm)
      for i in l:
        if sm in i:
            i[sm]='o'
      print ('  a b c')
      for i in board:
          if i == r1:
            print('1',end=' ')
          if i == r2:
            print('2',end=' ')
          if i == r3:
            print('3',end=' ')
          for y in i:
              print (i[y],end=' ')
          print(' ')
      turns+=1
      draw=0
      for i in l:
         val=tuple(dict.values(i))
         t=val.count('o')
         f=val.count('x')
         draw=draw+t+f
         if ((t==3) or (f==3)):
            game=False
            print('match over')
            break
      if(draw==24):
         print ('its a draw')
         game=False
         print('match over')   
      for i in l:
         val=tuple(dict.values(i))
         t=val.count('o')
         f=val.count('x')
         if ((t==3) or (f==3)):
            game=False
            print('match over')
            break   
      if game==False:
          break
      validmove=False 
      while(validmove==False):    
          pm=input('what will you play?')
          for i in l:
                if ((pm in i) and (i[pm]=='_')):
                    i[pm]='x'
                    validmove=True
          if (validmove==False):
                 print('Sorry, the move is invalid ')          
      print('you played :',pm)
      turns+=1
      draw=0
      for i in l:
         val=tuple(dict.values(i))
         t=val.count('o')
         f=val.count('x')
         draw=draw+t+f
         if ((t==3) or (f==3)):
            game=False
            print('match over')
            print ('  a b c')
            for i in board:
                 if i == r1:
                    print('1',end=' ')
                 if i == r2:
                    print('2',end=' ')
                 if i == r3:
                    print('3',end=' ') 
                 for y in i:
                   print (i[y],end=' ')
                 print(' ')
            break
      if(draw==24):
         print ('its a draw')
         print ('  a b c')
         for i in board:
                 if i == r1:
                    print('1',end=' ')
                 if i == r2:
                    print('2',end=' ')
                 if i == r3:
                    print('3',end=' ') 
                 for y in i:
                   print (i[y],end=' ')
                 print(' ')
         game=False
