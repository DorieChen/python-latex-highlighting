def FourColorLabel(GuanXiJuZheng):
    Num=len(GuanXiJuZheng)
    Color=[-1 for i in range(Num)]
    n=m=1
    #染色第一个区域，先设置为1
    while m<=Num:
        while n<=4 and m<=Num:
            flag=True
            for k in range(m-1):
                if GuanXiJuZheng[m-1][k]==1 and Color[k]==n:
                    flag=False    #染色有冲突
                    n+=1
                    break    
            if flag:
                Color[m-1]=n;
                m+=1
                n=1
        if n>4:                 # 超出标记范围e68a847a686964616f31333335343961 必须回退
            m-=1
            n=Color[m-1]+1
    return Color
 
GuanXiJuZheng=[
                [0,1,0,0,0,0,1],
                [1,0,1,1,1,1,1],
                [0,1,0,1,0,0,0],
                [0,1,1,0,1,0,0],
                [0,1,0,1,0,1,0],
                [0,1,0,0,1,0,1],
                [1,1,0,0,0,1,0]
             ]
for i in FourColorLabel(GuanXiJuZheng):
    print (i)
