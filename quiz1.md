1.	請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異

整數為0,1,888…等等的值，而浮點數則是像是3.14,0.001…等有小數點的數字，整數進行除法時，會得到結果為整數的答案，而浮點數則是會有小數點的結果。


2.	今天有兩個字串：
str1 = "Hallo Welt!" 
str2 = " NTU Rails 261!"
請說明以下兩個印出字串的方式的不同處：
puts str1 + str2
puts "#{str1}#{str2}"

兩個印出來的結果是一樣的，第一行是將兩個變數直接印出來，而第二行則是印出一個字串，在這個字串中有兩個變數str1跟str2。


3.	請解釋 array 和 hash 的不同處

array 跟 hash都是可以儲存值的用法，而除了基本的格式上的差異外，最主要的差別在於hash是使用一種置物箱和鑰匙的對應方式，一個key去assign一個值，而獲取值的方式就是要使用特定的鑰匙才有辦法獲得，而且沒有先後順序，array則沒有這種限制，array就是用ID 0~N 去對應陣列中的每一個值，且因為是0-N 所以是有先後順序的。


4.	請用一行程式碼從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值

arr.select{|x| x.class != String}


5.	請用一行程式碼把一個內容為整數 1 到 100 的陣列裡所有的值加上 2

arr.map {|x| x + 2}


6.	請寫出以下兩行程式碼迴傳的值，並解釋他們呼叫的方法差別為何：
[1, 2, 3, 3].uniq
[1, 2, 3, 3].uniq!

uniq 建立一個新的array並把重複的值刪除，uniq!則是將原本的array進行修正，如果有重複的就刪除，沒有重複就回傳nil。


7.	請列出兩種產出亂數的方法

1.使用rand function
rand(1..100) #一到一百的亂數隨便隨機一個

2.使用array的shuffle
Arr = [1,2,3,4,5,6]
Arr.sample 或是 Arr.shuffle.last 或是 Arr.shuffle.first #Array Arr 取一個值或是將array本身隨便排列之後取第一個或是最後一個的值。


8.	以下這段程式碼：
((1 > 3)&&(true == true))||(!!!false)
會執行出什麼結果？ 請試試不用 irb 算出結果

1> 3 (false), true == true (true) 進行AND &&會得到false, 後面的false的!=true, 再!會得到false, 再!會得到true， 最後用OR ||將false跟true會得到true。


9.	請問 binding.pry 是什麼？ 要如何使用它？

pry是一個debug用套件，使用
gem install pry #安裝pry
然後再.rb的檔案裡，最上面寫
require 'pry' #在此rb檔案裡使用pry
最後在你要斷點的地方插入
binding.pry #程式將執行到看到這一行就暫停，可檢查前面的程式碼是否有code錯。


10.	下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行
	var = 5

if var >= 5
  return "var is greater than or equal to 5"
else
  return "var is less than 5"
end

var =5
puts var>=5 ? "var is greater than or equal to 5" : "var is less than 5"


11.	請列出兩種不同的 hash 寫法

1. using the hash rocket style: 
Person = {
:name => "Bob",
:age => 17,
:occupation => "Engineer"
}

2. without the hash rocket simplified style: 
Person = {
name: "Bob",
age: 17,
occupation: "Engineer"
}
