# Level-1

## 001 Hello World

````python
print('Hello World!')
````

## 002 打印沙漏



## 003 个位数统计

```python
N=list(input())
k=0
b=0
for k in range(10):
    for i in range(len(N)):
        if int(N[i])==k:
            b+=1
    if b!=0:
        print('%d:%d'%(k,b))
        b=0
```

对输入的数做列表操作,再用一个循环表示判断数字`k`出现`b`次

`k`循环每进行一次,表示一个数字判断完毕,`i`循环每循环一次表示`N`被遍历查找一次

##004 计算摄氏温度

```python
N=eval(input())
N=5*(N-32)/9
print('Celsius = %d'%N)
```

对输入数据进行`eval`处理再使用公式计算

## 005 考试座位号

```python
N=int(input(''))
list1=[[] for _ in range(N)]
for i in range(N):
    list1[i]=input().split(sep=' ')
M=int(input(''))
list2=input('').split(sep=' ')
for i in list2:
    for j in range(N):
        if list1[j][1]==i:
            print(list1[j][0],list1[j][2])
```

先输入整数`N`,再根据整数`N`建立一个空列表矩阵`list1`

将各行输入进行`split`分隔处理,分别存入`list1`中的相应位置,得到:

| 准考证号 | 试机座位号 | 考试座位号 |
| -------- | ---------- | ---------- |
| list1[0] | list1[1]   | list1[2]   |

最后根据输入要求查找`list1[1]`位置对应的数据输出`list1[0]`,`list1[2]`即可

## 006 连续因子

```python
N=int(input(''))
list1=[]
maxLen=0
isPrimary = True
for i in range(2,int(N**0.5)+1):
    M=N
    j=i
    list2=[]
    while M%j==0:
        isPrimary=False
        list2.append(str(j))
        M=M/j
        j+=1
    tempLen=j-i
    if tempLen>maxLen :
        list1=list2
        maxLen=tempLen
if isPrimary == True:
    print(1)
    print(N)
else:
    print(maxLen)
    print('*'.join(list1))
```

首先将输入的整数储存在`N`内,创建`list1`用来储存最长的连续因子序列,`maxLen`用来存储最大的序列长度

进行一个`for`循环,`i`从2开始取值,表示连续因子序列的起始值,将`N,i`储存在临时变量`M,j`中,`M`同时起到连续除法中储存商值的作用`M=M/j`,定义`list2`用于临时储存连续因子序列

在`while`循环中,如果`M`能够被`j`整除,那么首先能够判断这个数`N`不为素数,存在元素大于一个的连续因子序列的可能,其次将`j`的值存入`list2`中,`j+=1`再进入`while`循环,*值得注意的是,这里对于结果能不能得到输入的整数并无考虑,只是考虑是否存在连续的队列*,实际上是两次遍历的结果

`tempLen`储存了该连续因子序列的长度,在连续元素中,即序列末尾值减去序列起始值

再进行素数和长度的判断,输出最长的连续因子个数和最小(先)的连续因子序列,素数作为一种特殊情况,同时题中明确说了不考虑1,所以素数是不存在连续因子序列,要特殊考虑

## 007 念数字

```python
zidian={'0':'ling','1':'yi','2':'er','3':'san','4':'si','5':'wu',\
        '6':'liu','7':'qi','8':'ba','9':'jiu','-':'fu'}
shuru=input('')
list1=[]
for i in range(len(shuru)):
    li1.append(zidian.get(shuru[i]))
shuchu=' '.join(list1)
print(shuchu)
```

首先定义一个字典,将几种对应情况储存在里面,定义一个空列表`list1`用来储存结果

使用`for`循环遍历输入的内容,通过字典的`get`方法将对应值取出添加到`list1`中

## 008 求整数段和

```python
A,B=input('').split()
A=int(A);B=int(B)
k=0
sum1=0
for i in range(A,B+1):
    print('%5s'%i,end='')
    sum1+=i
    k+=1
    if k%5==0 or i ==B:
        print()
print('Sum = %d'%sum1)
```

输入`A,B`,定义`k`用来判断每行输出个数,定义`sum1`用来储存整数和

使用`for`循环遍历`[A,B]`每个整数进行格式化输出,每遍历一个数`k`的值就加一,当`k`被5整除时`k%5==0`,表示当前行已经输出5个数,进行换行操作,值得注意的是,第一个`k`的值不能等于0,不然开头就会换行

当遍历输出结束后,对需不需要换行再输出`Sum = X`也要判断,当输出个数刚好能被5整除时,不用进行换行操作

## 009 N个数求和



## 010 比较大小

```python
N=input('').split(sep=' ')
N=list(map(int,N))
N.sort()
N=list(map(str,N))
N='->'.join(N)
print(N)
```

先将输入数据转化为一个列表`N`,使用`map`方法将其转化为`整数型`来使用`sort`方法比较大小,*值得注意的是`sort`方法本身不返回任何值,只对列表`N`进行操作*,因为`join`方法只能对`字符串`进行操作,所以再次使用`map`方法将列表`N`内数据转换为`字符`类型,最后使用`join`再输出

## 011 A-B

```python
a=input()
b=list(input())
for i in b:
    a=a.replace(i,"")
print(a)
```

`字符串`中有`replace`方法,可以直接替换,所以不把`a`的类型转换为`列表`,再使用一个`for`循环遍历比较

替换,输出

## 012 计算指数

```python
N=int(input(''))
M=2**N
print('2^%d = %d'%(N,M))
```

## 013 计算阶乘和

```python
N=int(input(''))
a=1
b=0
if N>0:
    for i in range(N,0,-1):
        for j in range(i,0,-1):
            a*=j
        b+=a
        a=1
print(b)
```

定义`a`用于存放每项阶乘值,`b`用来储存和值

使用一个`for`循环实现各项的计算,在代码中实现 $$B=N!+(N-1)!+...+1$$ 运算,完成一项计算时要重置`a`来进行下一项计算

## 014 简单题

```python
print('This is a simple problem.')
```

## 015 跟奥巴马一起画方块

```python
N,C=input('').split()
N=int(N)
for i in range(int(N/2+0.5)):
    print(N*C)
```

首先输入每行的个数(列宽)`N`和填充字符`C`,使用`for`循环$$50\%$$列数次,其中通过$$+0.5$$取整实现四舍五入

## 016 查验身份证





## 017 到底有多二

```python
N=int(input(''))
T=1
if N<0:
    T=T+0.5
    N=abs(N)
if N%2==0:
    T=T*2
N=list(str(N))
a=N.count('2')/len(N)
a=a*T
print('%.2f'%(a*100),end='')
print('%')
```

进行简单的`if`判断确定额外增加的参数`T`,如果是负数,那么程度增加$0.5$倍,如果是偶数`N%2==0`则在原来`T`的基础上增加$1$倍,则`T=T*2`,再利用`str`类型中的`count`方法计算$2$所占位数,最后计算,输出

## 018 大笨钟

```python
hh,mm=input().split(sep=':')
if int(hh)-12>0:
    hh = int(hh)
    if mm!='00':
        hh+=1
    print((hh-12)*'Dang')
else:
    print('Only %s:%s.  Too early to Dang.'%(hh,mm))
```

用`split(sep=':')`方法提取出`hh,mm`如果`hh`小于$12$,即时间早于12:00,那么输出`else`中内容,否则,判断`mm`是否为$00$,就是判断是否是整点,如果不是整点,那么敲钟的次数就为$hh-12+1$次,如果是整点,敲钟的次数就为$hh-12$次

## 019 谁先倒

```python
A,B=input('').split(sep=' ')
A=int(A)+1;B=int(B)+1
jia=yi=0
N=int(input(''))
for i in range(N):
    list1=input('').split(sep=' ')
    han=int(list1[0])+int(list1[2])
    if int(list1[1])==han and int(list1[3])!=han:
        A-=1
        jia+=1
        if A==0:
            break
    if int(list1[3])==han and int(list1[1])!=han:
        B-=1
        yi+=1
        if B==0:
            break
if A==0:
    print('A')
    print(yi)
else:
    print('B')
    print(jia)
```

模拟划拳过程,题目中给出的酒量是最多不倒下,我们把`A或B=0`视为倒下,即在给定的`A,B`$+1$就是倒下,所以对`A,B`都要$+1$考虑,同时,两个人同输或者同赢是不会出现任何`A,B`的改变,所以要特殊考虑这种情况,`jia,yi`分别用来记录喝的次数,倒下就用`break`结束程序,最后输出

## 020 帅到没朋友

```python
N=int(input(''))
list1=[]
list2=[]
set1=set()    #存放朋友圈中出现过的id
for _ in range(N):
    list1=input().split()
    del list1[0]
    if len(list1)==1:	#len(list1)其实就是之前删除的list1[0]
        continue
    else:
        for i in range(len(list1)):
            set1.add(list1[i])
M=int(input(''))
list3=input('').split(sep=' ')
for i in list3:
    if i not in set1 and i not in list2:
        list2.append(i)
if list2!=[]:
    list2=' '.join(list2)
    print(list2,end='')
else:
    print('No one is handsome')
```

定义两个列表,`list1`用来临时储存每行的输入,`list2`用来储存最后的输出,使用`set`类型储存朋友圈中出现过的id而不能使用`list`类型,因为在测试点中存在大量数据,使用`list`储存数据会导致超时错误

`len(list1)==1`是为了排除*只有自己一个人在朋友圈的人*

最后输出中`i not in set1 and i not in list2`使用`list`判断而不用`set`是因为`set`是一个无序序列,不满足题意

## 021 重要的话说三遍

```python
print('I\'m gonna WIN!\n'*3,end='')
```

*I'm*中的单引号要进行转义处理,或者代码中选用双引号`""`

## 022 奇偶分家

```python
jishu=0
oushu=0
N=int(input(''))
list1=input().split(sep=' ')
list1=list(map(int,list1))
for i in range(N):
    if list1[i]%2==0:
        oushu+=1
    else:
        jishu+=1
print(jishu,oushu)
```

首先定义`jishu,oushu`来分别储存奇偶个数,把输入数据存入`list`并通过`map`函数转换为可计算类型`int`,对`list1`遍历判断,如果能被2整除就代表为偶数,否则为技术,最后输出

## 023 输出GPLT

```python
N=input('').upper()
G=N.count('G');P=N.count('P');L=N.count('L');T=N.count('T')
N=list(N)
M=0
while G+P+L+T!=0:
    if G!=0:
        print('G',end='')
        N.remove('G')
        G-=1
    if P!=0:
        print('P',end='')
        N.remove('P')
        P-=1
    if L!=0:
        print('L',end='')
        N.remove('L')
        L-=1
    if T!=0:
        print('T', end='')
        N.remove('T')
        T-=1
print()
```

先把输入字符用`upper`方法全部转换为大写,忽略大小写影响,然后计算字符串中`G,P,L,T`各自的数量,在之后的判断中,每输出一次就$-1$

如果不用变量储存个数而是使用`in`方法判断会导致空间复杂度过大最后一个测试点超时

## 024 后天

```python
N=int(input())
M=(N+2)%7
if M==0:
    M=7
print(M)
```

对数据进行取模运算,但在星期五时取模的结果为$0$不符合题意,此时要特殊考虑,输出$7$

## 025 正整数A+B

```python
N=input().split(' ',1)
if len(N)==1:
    N.insert(0,' ')
a=b='?'
if N[0].isdigit():
    if 1000>=int(N[0])>0:
        a=int(N[0])
if N[1].isdigit():
    if 1000>=int(N[1])>0:
        b=int(N[1])
if a=='?'or b=='?':
    c='?'
else:
    c=str(a+b)
print('%s + %s = %s'%(a,b,c))
```

首先把输入数据分成`A`和`B`,值得注意的是这里只能分隔一次,不然会导致第三个点不过,然后进行一个判断,来排除`A`为空串的情况,如果`A`为空串就用`insert`函数在列表N~0~处插入一个来代替空串`A`,再是对数据进行判断,如果全为数字再判断是否在$[1,1000]$内,最后输出结果,格式化输出要使用`str`数据类型,因为要兼顾输出`?`和数字,所有的结果也要转换为`str`类型

| 特殊测试数据 | 预期输出结果 |
| ------------ | ------------ |
| 100  100     | 100 + ? = ?  |
| 20           | ? + 20 = ?   |

## 026 I Love GPLT

```python
N=list('I Love GPLT')
for i in range(len(N)):
    print(N[i])
```

## 027 出租

```python
N=list(map(int,list(input(''))))
list1=list(set(N))
list1.sort(reverse=True)
list2=[]
for i in range(len(N)):
    list2.append(str(list1.index(N[i])))
list1=list(map(str,list1))
list1=','.join(list1)
list2=','.join((list2))
print('int[] arr = new int[]{%s};'%list1)
print('int[] index = new int[]{%s};'%list2)
```

首先用`map`方法把输入的数据转化为`int`整数型方便后续比较,利用列表的`sort`方法来完成降序`reverse=True`并存到`list1`,再用一个`for`循环找到每个数在`list1`中对应的下标,记录在`list2`中最后输出

## 028 判断素数

```python
def fun(M):
    if M<=1:
        return False
    for i in range(2, int(M**0.5) + 1):
        if M % i == 0:
            return False
    return True
N=int(input(''))
for _ in range(N):
    M=int(input(''))
    if fun(M):
        print('Yes')
    else:
        print('No')
```

把求素数的代码放在函数语句中执行可以提高运行效率,先对数据进行一个判断,排除$1$的情况,如果`M`能被$[2,\sqrt{M}]$区间的数整除,说明`M`不是一个素数,返回`False`,最后输出

> 如果一个数可以拆分为两个因数,那么这两个因数必然有一个因数小于此数的平方根,有一个因数大于此数的平方根。

$$
a*b=x
两边同时乘以\frac{1}{b*\sqrt{x}}得到\frac{a}{\sqrt{x}}=\frac{\sqrt{x}}{b}
$$

$$
若a<\sqrt{x},则\sqrt{x}<b
$$

## 029 是不是太胖了

```python
H=int(input(''))
M=(H-100)*0.9*2
print('%.1f'%m)
```

按公式计算输出

## 030 一帮一

```python
N=int(input(''))
list1=[]    #储存原始数据
list2=[]    #储存女性
list3=[]    #储存男性
for _ in range(N):
    M=input().split()
    list1.append(M)
    if M[0]=='0':
        list2.append(M[1])
    else:
        list3.append(M[1])

for i in range(N//2):
    if list1[i][0]=='0':
        print(list1[i][1],list3.pop())
    else:
        print(list1[i][1], list2.pop())
```

定义三个列表,其中`list1`用来存放原始数据,完成按成绩高低输出,`list2,list3`分别用来储存男性,女性名单,用来匹配,使用`for`循环按照`list1`中的数据顺序进行遍历查找,如果`list[i][0]`为`'0'`则到`list3`中找最末尾的元素,实现成绩优劣,性别不同的配对

| list1~0~ | list1~1~ |
| -------- | -------- |
| 性别     | 姓名     |

