# 基本概念
## format格式化 
 [format用法](https://www.itread01.com/content/1544842809.html)

[string format]([https://extenshu.com/2017/09/24/python%E5%88%9D%E5%AD%B8%E9%87%8D%E9%BB%9E-04-%E8%81%8A%E8%81%8Aprint/](https://extenshu.com/2017/09/24/python%E5%88%9D%E5%AD%B8%E9%87%8D%E9%BB%9E-04-%E8%81%8A%E8%81%8Aprint/)

- 對於每一個大括號，在後面的引數中找到對應的引數插進來
- format操作類似於於將傳入的引數製成多個數據的資料結構元組或者字典，然後依照索引插入引數
- 定義變數之索引、名稱、控制輸出長度和格式、格式化傳入資料的格式需求
```alias
`print``(``'Hello, {:s}. You have {:d} messages.'``.``format``(``'Rex'``,` `999``))`

`## Output:`

`# Hello, Rex. You have 999 messages.`
```
- 這裡的用法是，在字串裡面「挖洞」，放入你想要的變數，使用{:型別}來達成，想要放入字串變數則是{:s}，整數是{:d}，而浮點數則是{:f}

```alias
`print``(``'Hello, {0:s}. You have {1:d} messages. Good luck to you, **{0}**'``.``format``(``'Rex'``,` `999``))`

`## Output:`

`# Hello, Rex. You have 999 messages. Good luck to you, **Rex**`
```
- 冒號前可以自訂變數的index，如果你有要重覆使用那個變數時就可以用的到，例如{0:s}。但定義過的變數，要再使用時，請直接使用{變數index}，後面的:型別就不要再加上了，因為已經宣告過了再宣告會有衝突


# 語法


- \  目的是要正確顯示 
- .2f 表示小數後2位(float)
- 表示字串使用單雙括弧都可
- {} 表示留一個顯示位置
- {: } 位置中冒號表示設定
- .format 表示格式化
- < 表示向左對齊,反之向右
- ,元素之間要用逗點區隔
- [] 中括號取索引值(在處理資料組的時候，每一筆資料的位置（也就是它的索引值）)

## 字串
[字串處理](https://drive.google.com/drive/folders/1CduaHuHoLplHxKODixOTrnbchjwE5UnU)

- str.isalpha(s)	# 若字串參數s的所有字元都是英文字母，就傳回True，否則傳回False
- str.isdigit(s) 	# 若字串參數s的所有字元都是阿拉伯數字，就傳回True，否則傳否False
- **str.isalnum(s) 	# 若字串參數s的所有字元都是英文/阿拉伯數字，就傳回True，否則傳否False**(用來檢驗是否為符號,如果非英文/數字,則是符號)
```alias
str.isalnum('123.45') 	# 字串包含的小數點不是英文字母及數字	
False
str.isalnum('5apples')		 
True
```
- str.lstrip([chars]): 從字串"左側"刪除選擇性參數chars所指定的字元 	
- str.rstrip([chars]): 從字串"右側"刪除選擇性參數chars所指定的字元
- **str.strip([chars])：從字串"兩側"刪除選擇性參數chars所指定的字元，一旦碰到不是指定的字元就停止刪除，然後傳回剩下的字串。(參數chars可以省略不寫，表示指定的字元為空白，即刪除字串兩側的空白。)**

```alias
a = "Learning python Is funny"
"Learning python Is funny".strip("ny") # 刪除字串兩側ny
'Learning python Is fu'
```
```alias
'	spacious	'.strip() # 刪除字串兩側的空白
'spacious'
```



# Python function函式
[Python函式](https://sites.google.com/site/zsgititit/home/python-cheng-shi-she-ji/python-han-shi-7)

[利用函式處理單一的特定功能](https://medium.com/ccclub/ccclub-python-for-beginners-tutorial-244862d98c18)

[函式講義](https://classroom.google.com/u/0/c/NDg0MjYxMjEyMjNa/m/NDg1OTU2NjA0MjFa/details?hl=zh-TW)

- function 是一個建構程式時的小區塊，它就像是一台機器，你可以自行指定它的功能，以及所需要的原料（輸入）、產出（輸出）
自動販賣機就像是一個 function ，他的 input 是硬幣和商品的選擇， output 則是你所選的商品
- function 的規格（輸入、輸出和功能）是由我們定義的。因此，在執行 function 之前應該要事先思考過這個參數的 data type


## 函式的定義
- 需要回傳時用return:
 - return 只能回傳單一的值，它可以回傳一個整數 int 、一個浮點數 float 、一個串列 list 、…等等，他可以回傳許多不同型態的物件，但是都只能回傳一個
 - 一次回傳多個值時，將這些值包成一個元組 tuple 再將之回傳


## 函式的呼叫
- 不要回傳:函式名稱(參數值1,參數值2,…)
- 需要回傳:變數=函式名稱(參數值1,參數值2,…)
 - 等號右邊要先做完，利用函式名稱與參數來呼叫函式，最後函式回傳值給變數，變數就紀錄函式呼叫後的回傳值。

```alias
def area(x,y):
          return x*y
a = int(input('請輸入長度？'))
b = int(input('請輸入寬度？'))
ans = area(a, b)
print('長方形面積為', ans)

```
解說:

1.函式area的定義，輸入參數x與y，回傳x乘以y的結果

2.於螢幕輸出「請輸入長度？」，經由函式input輸入字串，再由函式int將字串轉換成整數指定給變數a。

3.於螢幕輸出「請輸入寬度？」，經由函式input輸入字串，再由函式int將字串轉換成整數指定給變數b。

4.呼叫area函式，使用a與b為參數，將函式回傳值儲存入變數ans

5.使用函式print顯示字串「長方形面積為」串接變數ans在螢幕上


## 參數與引數差異
- 參數(Parameter)日文翻成「假引數」。參數是我們在函式定義中所列出的變數。是方法簽章(方法的宣告),用來說明函數當被呼叫時必須接受到什麼型態,數量的資料,函式參數提供「具名的local儲存空間」供函式使用。
- 引數(Argument) 引數是當我們呼叫函式時傳遞給它的值。是用於引發函式, 呼叫時放在括號中的東西
- **引數=值, 參數=變數**
![](https://i.imgur.com/GaEBVHH.png)

## 遞迴函式
[遞迴函式](https://www.itread01.com/content/1544350710.html)
- 遞迴是指函式在定義中呼叫函式自身的方式,自己呼叫自己，需要有終止的條件，若沒有終止的條件就會形成無窮遞迴。

- 遞迴有兩個關鍵特徵:

鏈條：計算過程存在鏈條，例1中的鏈條是n! = n(n-1)！

基例：存在一個或多個不需要再次遞迴的基例，例1的基例是1! = 1

```alias
def fact(n):
    if n == 0:
        return 1  # 基例
    else:
        rturn n*fact(n-1)  # 鏈條
```
>
>1.遞迴本身是個函式，需要通過函式定義方式描述
>
>2.在函式內部，採用分支語句對輸入引數進行判斷，針對基例和鏈條分別編寫對應程式碼

## iterator、iterable、generator
[ iterator、iterable、generator]([http://changlt.blogspot.com/2017/05/pythoniteratoriterablegenerator.html](http://changlt.blogspot.com/2017/05/pythoniteratoriterablegenerator.html))
- **iterable**：可迭代物，通常是一個容器、iterable實作__iter__方法回傳一個參考到此容器內部的iterator  
  
- **iterator**：迭代器, 為序列或容器型態提供一相同的介面讓客戶端可遍歷(iterate over)容器內的元素，iterator實作了__next__與__iter__方法，方別供next與iter函式呼叫，每個iterator同時也**是**一個iterable  
  
- **generator**：產生器，是由包含yield敘述的函式或產生器表達式(簡稱genexp)所產生，支援所有iterator的操作以及額外的send方法，客戶端可透過send方法與generator溝通、影響其內部狀態

iterable指的就是容器本身，將iterable傳進iter函式可以得到一個iterator  
iterator的操作非常簡單，透過next函式可以不斷取出下一個元素，抵達尾端時會丟出StopIteration意外  
在Python中iterator是個一次性的物件，不能回頭，若想要重新遍歷容器就必須再藉由iter函式產生新的iterator


## Built-in Functions 常用函式
[Built-in Functions](https://docs.python.org/3/library/functions.html)

### int 只取整數
傳回數值參數 x 的整數部份，小數部份直接捨去

### round 四捨五入
傳回與數值參數 x 最接近的整數(四捨五入)，若要設定精確度為小數幾位，可以加上選擇性參數 precision
```alias
>print(type(int(3.7)))
>
>3
>
>print(type(round(3.7)))
>
>4
```
### eval
   - eval 函數可以讓輸出的值有彈性( 根據預設狀態顯示 浮點數或是整數)
   - eval 函數可以強制執行()內的所有

>例如:print(eval(input()))
>
>2+3
>
>5

   - eval 函數雖然方便，但是要注意安全性，可以將字符串轉成表達式並執行，就可以利用執行系統命令，刪除文件等操作。

### abs
  - 絕對值, abs(-5.3) 會傳回5.3

### ord 
   - ord() 函数是 chr() 函数（对于8位的ASCII字符串）或 unichr() 函数（对于Unicode对象）的配对函数，它以一个字符（长度为1的字符串）作为参数，返回对应的 ASCII 数值，或者 Unicode 数值
   - [ascii碼](http://kevin.hwai.edu.tw/~kevin/material/JAVA/Sample2016/ASCII.htm)

### map

[map用法](https://e8859487.pixnet.net/blog/post/392947555-python-%E5%9F%BA%E7%A4%8E%E7%B3%BB%E5%88%97--map%28%29-%E7%94%A8%E6%B3%95%E8%A7%A3%E8%AA%AA](https://e8859487.pixnet.net/blog/post/392947555-python-%E5%9F%BA%E7%A4%8E%E7%B3%BB%E5%88%97--map%28%29-%E7%94%A8%E6%B3%95%E8%A7%A3%E8%AA%AA)
   [map函數](https://www.jb51.net/article/128315.htm)
   - 是定義一個function。接著用這個function來對一個iterable (可迭代物，通常是一個容器)內每一個元素做處理
```alias
# 將字串list裡面的每一個元素都轉型成整數(int)
`>>> listA` `=` `[``'1'``,``'2'``,``'3'``]`

`>>>` `print` `map``(``int``,listA)`

`[``1``,` `2``,` `3``]`
```
   - 利用map()函數，可以把一個 list 轉換為另一個 list，只需要傳入轉換函數。
```alias
假设用户输入的英文名字不规范，没有按照首字母大写，后续字母小写的规则，请利用map()函数，把一个list（包含若干不规范的英文名字）变成一个包含规范英文名字的list：
输入：['adam', 'LISA', 'barT']
输出：['Adam', 'Lisa', 'Bart']
def format_name(s):
 s1=s[0:1].upper()+s[1:].lower();
 return s1;
print map(format_name, ['adam', 'LISA', 'barT'])
```
- 使用map()函數可以實現將其他類型的數轉換成list
```alias
`*``*``*``將元組轉換成``list``*``*``*`

`>>>` `map``(``int``, (``1``,``2``,``3``))`

`[``1``,` `2``,` `3``]`

`*``*``*``將字符串轉換成``list``*``*``*`

`>>>` `map``(``int``,` `'1234'``)`

`[``1``,` `2``,` `3``,` `4``]`

`*``*``*``提取字典的key，並將結果存放在一個``list``中``*``*``*`

`>>>` `map``(``int``, {``1``:``2``,``2``:``3``,``3``:``4``})`

`[``1``,` `2``,` `3``]`

`*``*``*``字符串轉換成元組，並將結果以列表的形式返回``*``*``*`

`>>>` `map``(``tuple``,` `'agdf'``)`

`[(``'a'``,), (``'g'``,), (``'d'``,), (``'f'``,)]`

`#將小寫轉成大寫`

`def` `u_to_l (s):`

`return` `s.upper()`

`print` `map``(u_to_l,``'asdfd'``)`
```
### replace
replace() 方法把字符串中的 old（旧字符串） 替换成 new(新字符串)，如果指定第三个参数max，则替换不超过 max 次。
> str.replace(old,  new[, max])
> 

### split
   - str.split(str="", num=string.count(str)). 
   - str -- 分隔符，默认为所有的空字符，包括空格、换行(\n)、制表符(\t)等。  
   - num -- 分割次数。**默认为 -1, 即分隔所有**

```alias
str = "Line1-abcdef \nLine2-abc \nLine4-abcd";
print str.split( );       # 以空格为分隔符，包含 \n
print str.split(' ', 1 ); # 以空格为分隔符，分隔成两个

輸出為:
['Line1-abcdef', 'Line2-abc', 'Line4-abcd']
['Line1-abcdef', '\nLine2-abc \nLine4-abcd']
```
### sep
print()裡放多個字串，預設會使用空白串成一行，如果使用「sep」關鍵參數來變更分隔符號
```alias
`print``(``'Good'``,` `'Bad'``,` `'Ugly'``)`

`## Output:`

`# Good Bad Ugly`

`print``(``'Good'``,` `'Bad'``,` `'Ugly'``, sep` `=` `'/'``)`

`## Output:`

`# Good/Bad/Ugly`
```

## 開啟以及關閉檔案
[講義]([https://docs.google.com/presentation/d/1ecjyoTNTYlwqeiv7LfHAkcTR1woVQykB/edit#](https://docs.google.com/presentation/d/1ecjyoTNTYlwqeiv7LfHAkcTR1woVQykB/edit#))
**開啟檔案後，將檔案關閉才能確保檔案存檔(串流概念)**


### open(file, mode)
>  fileObject = open('C:\\temp\\test.txt', 'r') →使用逸脫序列 \\
這個敘述亦可寫成如下：
>   fileObject = open(r'C:\temp\test.txt ', 'r') →不用逸脫序列 \\

#### mode用法:
- 'r'	唯讀模式（預設）
- **'w'	寫入模式（覆寫）,會先清空檔案內容**
- **'x'	**寫入,檔案不存在時才建立新檔並開啟為寫入模式,如檔案已存在會引發Error 保護檔案用的避免錯用w讓檔案清空**
- 'a'	寫入模式（續寫）
- 'b'	二進位模式
- 't'	文字模式（預設）
- '+'	更新磁碟檔案
- 'U'	通用新行模式

#### 三種讀取方式:
-  使用read() 方法從檔案讀取資料,返回字串型態
- readline() 方法讀取資料，一次讀取一行，返回字串型態
- readline**s**() 方法讀取資料，讀取整個檔案所有行，**儲存在一個列表(list)變數中，每行作為一個元素**

### with ...as
結束存取檔案後，必須呼叫close() 方法關閉檔案物件, 使用with ...as可防呆(一旦程式執行的動作離開區塊，就會**自動關閉**檔案物件)


# 流程控制-條件選擇
[流程控制及條件選擇](https://drive.google.com/file/d/1VK_QzBOgVHCOrPFhsjZoEFEY-SllFovl/view).
- 盡量維持在2層
- 基本判斷
 - 除以2餘數等於0,表示偶數
 - 除以2餘數等於1,表示奇數

- 條件判斷時,做出小範圍交集的資料
- 巢狀分析時,先挑大範圍, 再加2號條件做判斷


# 流程控制-迴圈
[流程控制-迴圈](https://drive.google.com/file/d/10UK28ocKjuAwZIaGhQ64PnYRZ8dYa2ji/view)

## for-loop
for-loop 比較適用在「已知迴圈數」

![for語法圖](for迴圈.jpg)


## while-loop
 while-loop 則適用在「無法預知迴圈數」的問題上,例如:年貨裝堅果

## break & continue
- break: 迴圈內檢查其他條件,如符合就強制離開迴圈
- continue: 用此再迴圈內跳過後面的敘述直接返為迴圈開頭
![](https://miro.medium.com/max/844/1*HGmI9ELOvq13Np2tu2aKVw.png)
continue 敘述會讓程式跳出最靠近的這層迴圈，不再向下執行之後的敘述，然後繼續執行下一步的迴圈運作。
因此它的目的是為了讓程式不執行迴圈結構內的某些敘述而已。

## 巢狀迴圈
- 巢狀迴圈其實很像時鐘。當秒針從0轉到59的時候，分針才會加1，然後秒針又從0開始。也就是說，當秒針轉一圈，分針才加1。用巢狀迴圈來比喻，秒針就是內層迴圈，分針就是外層迴圈。當內層迴圈執行一輪之後，外層迴圈才會進到下一項。



# Python的資料儲存容器: 數組(tuple)、串列(list)、字典(dict)與集合(set)

[tuple-串列-字典-集合](https://sites.google.com/site/zsgititit/home/python-cheng-shi-she-ji/python-zi-liao-chu-cun-rong-qituple-chuan-lie-zi-dian-ji-he)
- Python的資料儲存容器: 可以分為tuple、串列(list)、字典(dict)與集合(set)四種
- 生成式(comprehension)與產生器(generator): 生成式可以依照規則產生資料，接著將資料儲存在串列、字典與集合內。

> 「[運算式  for  元素  in  可迭代的物件]」
>
> #使用「[ ]」表示為串列，可迭代的物件可以是tuple、串列、字串、字典、…與函式range等

> [運算式  for  元素  in  可迭代的物件  if 條件判斷]」
>
> #加入判斷式

```alias
產生一個串列，該串列元素為1到10的所有奇數數字，使用生成式可以寫成以下程式。

[x for x in range(1,11) if x%2 == 1]

```

## 串列(list)
[ List（串列）官方](https://docs.python.org/zh-tw/3/tutorial/datastructures.html#nested-list-comprehensions)
[串列講義](https://classroom.google.com/u/0/c/NDg0MjYxMjEyMjNa/m/NDg2MDMwMTc1NDFa/details?hl=zh-TW)
[串列的基本用法](https://medium.com/ccclub/ccclub-python-for-beginners-tutorial-c15425c12009)
- 是Python中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推
- 串列是有順序性的
- 串列数据项不需要具有相同的类型
- 串列為可修改的序列資料
- 使用list函式可以將資料轉換成串列，並可以使用[::]取出串列的一部分

```alias
li = [1,2,3,4,5]
li[-2::-1]
回傳
[4, 3, 2, 1]
```
```alias
li1 = list([1,2,3])
li2 = [1,2,3]
print(li1)
print(li2)
回傳
[1, 2, 3]
[1, 2, 3]
```
```alias
li = [1,2,3,4,[5,6,7,8]]
li[4][2]
回傳
7
```
```alias
for x in [1, 2, 3]: print x, #迭代
回傳
1 2 3
```

### List的新增修改:
#### 新增方法: 
- append method: 使用 append 這個方法( method )來將新的元素增加到 list 的最後
- insert method: 指定所增加物件的位置
- extend method: 一次想加入很多個值、或是想將某個 list 中的元素加到另一個 list 的時候

#### 移除方法:
- remove: 想要移除一個 list 中的元素
- pop: 只是想要移除這個 list 的最後一個元素的話,pop method 對於想要把 list 當作特定資料結構使用來說非常方便 (例如 stack 跟 queue)。


### 搭配用的函式
- sort 是应用在 list 上的方法直接做排序 
- sorted 可以对所有可迭代的对象进行排序操作。内建函数 sorted 方法返回的是一个新的 list
- index() 函数用于从列表中找出某个值第一个匹配项的索引位置
- **Iterate遍歷,指的是按照某種規則，不重複地一一將元素取出來使用**


## 數組(tuple)
- **是種較為安全的數列**(唯讀不可變更資料結構的數列)
- 亦稱元組、序對，指的是由一連串資料組成、有順序且不可改變內容(immutable) 的序列
- tuple 的前後以小括號「( ) 」標示，裡面的逗號隔開，資料的型態可以不同
> h = (2, [3,4], (10,11,12))






## 集合(set)
[真子集](https://www.itsfun.com.tw/%E7%9C%9F%E5%AD%90%E9%9B%86/wiki-399614-448393)
[集合之间的基本关系:子集与真子集](https://www.bilibili.com/video/av35880182/)
- Set 是一個無序的集合類型。它可以遍歷，修改，**沒有重複的元素**。支持數學集合的一些操作，例如交集，並集，差集，補集。
   - 子集就是一個集合中的全部元素是另一個集合中的元素，有可能與另一個集合相等
  - 真子集proper subset(別稱:真包含)就是一個集合中的元素全部是另一個集合中的元素，但不存在相等 (如果集合A是集合B的子集，並且集合B中至少有一個元素不屬于A，那麽集合A叫做集合B的真子集(proper subset))
  - **子集合,超集合必須要全數相同(與交集連集概念不同)**

> s1 <= s2 # s1 是 s2 的子集
>
> s1 < s2 # s1 是 s2 的真子集

```alias
# & 交集
>>> {1,2,4} & {1,2,3} # 两个集合中相同的元素
{1,2} 

# ^ 差集
>>> {1,2,4} ^ {1,2,3} # 两个集合中不同的元素
{3,4}

# | 合集
>>> {1,2,4} | {1,2,3} # 合并集合并消重
{1, 2, 3, 4}

# <= 子集
>>> {1,2} <= {1,2} # 第一个集合的 **所有元素** 都出现在第二个集合中
True

# < 真子集 
>>> {1,2} < {1,2,3} # 第二个集合包含第一个集合的所有元素，还有别的
True
```
- set和dict類似，也是一組key的集合，但不存儲value。由於key不能重複，所以，在set中，沒有重複的key。
- 要創建一個set，需要提供一個list作為輸入集合
- [Python 集合類型 Set 函數](https://kknews.cc/zh-tw/code/xqkbg2g.html)
 - Set新增移除: s.add(e), s.remove(e) 


## 字典(dict)
[python中的dict和set的用法]https://kknews.cc/zh-tw/news/m29zo56.html)
[Dict資料組](https://sites.google.com/site/ezpythoncolorcourse/dict)
- 使用鍵-值（key-value）存儲，具有極快的查找速度。我們不需要知道餐點放在哪一個位置，只要說出餐點名稱，就可以取得想要的餐點。我們把這種方式稱為key和value的對應。
- 和set一樣無順序性(無索引值),以key來取字典的值(list,tuple是以索引值位置[]存取元素)
- key 必須是不可變的資料型態,如數字、字串string(因為dict根據key來計算value的存儲位置，如果每次計算相同的key得出的結果不同，那dict內部就完全混亂了)
- **item= key+ value**
- 由於字典中的鍵:值對沒有順序之分，因此，字典不支援連接運算子 (+)、重複運算子 (*)、比較運算子(>、>=、<、<= ) 、索引運算子 ([ ])、片段運算子 ([start:end]) 或其它與順序相關的運算。

# 半結構式檔案處理
(講義)[[https://drive.google.com/drive/folders/1CduaHuHoLplHxKODixOTrnbchjwE5UnU](https://drive.google.com/drive/folders/1CduaHuHoLplHxKODixOTrnbchjwE5UnU)]

## CSV檔案
###  讀取
1.帶有欄標題的串列
2.轉為字典, 再轉串列
-  csv.reader(csvfile)
- **為了讓資料中包含的換行字元可以正確被解析，請加入 newline=''  參數，建議在讀取 csv 檔案時都固定加入這個參數。**
- delimiter 指定分隔字元

### 寫入
- element.writerows() - 可一次寫入二維表格

## JSON 格式
[  Python3 json數據解析]([https://www.runoob.com/python3/python3-json.html](https://www.runoob.com/python3/python3-json.html))
[讀寫json檔案]([https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/366237/](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/366237/))
- json: 用於字串和python資料型別間進行轉換 
- json.dump**s**() - 將Dict資料轉換為**字串**
   - **python字典轉為JSON對象**
   -  對數據進行編碼
 -  json.load**s**() – 將字串轉換為**Dict型態**
     - **將JASON對象轉python字典**
     - 對數據進行解碼
     
- json.dump() - 將資料寫入json檔
- json.load() - **如果只有一筆,則將json檔讀取成Dict，若為多筆Dict，則  讀取成List(裡面每個元素為一個字典)**

## XML
- XML對程式語言有意義的地方是提供節點(自定義的tag)
- XML是可擴展標記語言（Extensible Markup Language）的縮寫，其中的 標記（markup）是關鍵部分。您可以創建內容，然後使用限定標記標記它，從而使每個單詞、短語或塊成為可識別、可分類的信息。  
- 每個 Element 有以下的特性
  -  Tag : 用<和>包圍的部分,為start.tag 和end.tag
  -   Element : 被tag包圍的部分,如teacher,可當成一個node也有子節點
  - Attribute: 在tag中可能存在的name/value,如下圖的 name="陳彼得" 一般表示屬性
  - text: 內容

### 利用ElementTree解析XML
- 解析XML檔案
```alias
import xml.etree.ElementTree as ET # 匯入套件

tree = ET.parse('country_data.xml') # 解析先獲得根結果 
root = tree.getroot() 
print(root.tag, root.attrib)
```
- 解析XML字串
```alias
xml_str = ET.tostring(root)
print (xml_str)

root = ET.fromstring(xml_str)
print (root.tag, root.attrib)
```
### 根據tag找資料
- element.iter() :找符合所有的tag
- element.find() : 找第一層元素中第一個符合的tag
- element.findall() :找第一層子元素中符合的tag


# 解題
## 邏輯
- 先懂題目意思,搞懂要輸出的格式
- 拆解結構,分層寫程式
>[308解題](https://www.youtube.com/watch?v=XDj-SJAmyE8)
>
>例如: 308,有2層迴圈:先做內圈(每個數字,先文字轉為整數後的加總),再做外圈(次數的加總)
>
>ps. 寫完後mark起來再按tab可以全部往後一階


- 答案對了再調整輸出格式的寫法

## 要訣
   - 位置先寫,再寫格式format
   - 型別放在數字後:
   - 條件成立後執行的動作才要縮排 

>.4f

   - math. tan

- 函式類解題順序: 定義函式> 條件判斷> 賦值> 呼叫函式
- **找最大值及最小值的方法:　用遍歷or Range的方式找**
- **set用{}把迴圈包起來做集合,但字典(結構不同,由key value組成)和數組(因為無法建立元素在內)無法使用**






# TQC解題型態
Python證照

2. 第1類：基本程式設計
2.1
基本程式設計重點說明
2.2
102. 浮點數格式化輸出
2.3
104. 圓形面積計算
2.4
106. 公里英哩換算
2.5
108. 座標距離計算
2.6
110. 正n邊形面積計算
3. 第2類：選擇敘述
3.1
202. 倍數判斷
3.2
204. 算術運算
3.3
206. 等級判斷
3.4
208. 十進位換算
3.5
210. 三角形判斷
4. 第3類：迴圈敘述
4.1
302. 迴圈偶數連加
4.2
304. 迴圈倍數總和
4.3
306. 迴圈階乘計算
4.4
308. 迴圈位數加總
4.5
310. 迴圈公式計算
5. 第4類：進階控制流程
5.1
401. 最小值
5.2
402. 不定數迴圈-最小值
5.3
403. 倍數總和計算
5.4
404. 數字反轉判斷
5.5
405. 不定數迴圈-分數等級
5.6
406. 不定數迴圈-BMI計算
5.7
407. 不定數迴圈-閏年判斷
5.8
408. 奇偶數個數計算
5.9
409. 得票數計算
5.10
410. 繪製等腰三角形
6. 第5類：函式(Function)
6.1
501. 訊息顯示
6.2
502. 乘積
6.3
503. 連加計算
6.4
504. 次方計算
6.5
505. 依參數格式化輸出
6.6
506. 一元二次方程式
6.7
507. 質數
6.8
508. 最大公因數
6.9
509. 最簡分數
6.10
510. 費氏數列
7. 第6類：串列(List)的運作(一維、二維以及多維)
7.1
第6類重點提示
7.2
601. 偶數索引值加總
7.3
602. 撲克牌總和
7.4
603. 數字排序
7.5
604. 眾數
7.6
605. 成績計算
7.7
606. 二維串列行列數
7.8
607. 成績計算
7.9
608. 最大最小值索引
7.10
609. 矩陣相加
7.11
610. 平均溫度
8. 第7類：數組（Tuple）、集合（Set）以及詞典（Dictionary）
8.1
第7類重點提示
8.2
701. 串列數組轉換
8.3
702. 數組合併排序
8.4
703. 數組條件判斷
8.5
704. 集合條件判斷
8.6
705. 子集合與超集合
8.7
706. 全字母句
8.8
707. 共同科目
8.9
708. 詞典合併
8.10
709. 詞典排序
8.11
710. 詞典搜尋
9. 第8類：字串(String)的運作
9.1
第8類重點提示
9.2
801. 字串索引
9.3
802. 字元對應
9.4
803. 倒數三個詞
9.5
804. 大寫轉換
9.6
805. 字串輸出
9.7
806. 字元次數計算
9.8
807. 字串加總
9.9
808. 社會安全碼
9.10
809. 密碼規則
9.11
810. 最大值與最小值之差
10. 第9類：檔案與異常處理
10.1
第9類重點提示
10.2
901. 成績資料
10.3
902. 資料加總
10.4
903. 成績資料
10.5
904. 成資料計算
10.6
905. 字串資料刪除
10.7
906. 字串資料取代
10.8
907. 詳細資料顯示
10.9
908. 單字次數計算
10.10
909. 聯絡人資料
10.11
910. 學生基本資料




=============================================================

## **Markdown基本使用測試**

[Markdown基本使用](https://docs.microsoft.com/zh-tw/contribute/how-to-write-use-markdown)

![圖片](C:\Users\bck10\Desktop\JAVA課程\圖1_Java SE.jpg)



| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |


```alias
...
your code goes in here
...
```
[!NOTE]


