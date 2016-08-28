1. 請用簡單的方式敘述以下每一行程式碼：

  ```ruby 
  a = 1 
  @a = 2
  @@a = 5
  user = User.new
  user.name
  user.name = "Joe"
  ```
  Answer:
  line1: 把1這個值assign給變數a
  Line2: 把2這個值assign給實例變數a
  Lin23: 把5這個值assign給類別變數a
  Lin24: New一個Class User的物件叫做user
  Line5: 顯示這個user物件的名稱
  Line6: 把Joe指定給user物件的名稱

2. 什麼是 module? 請寫一段程式碼說明一個 class 要如何使用一個 module 裡面的 method?

  ```ruby
  module Ability #define a module named Ability
    def fly #define a method called fly
      puts “I know how to fly”
    end
  end
  class Animal #define a class Animal
    attr_accessor :name
    def initialize(name)
      @name = name
  end
  end
  class Bird < Animal #define a class Bird which inherits Animal
    include Ability #include the module Ability
  end
  sparrow = Bird.new(“Sparrow”) #create a new object sparrow
  sparrow.fly #since the module was included, we are able to call method fly
  ```


3. 請說明 class variable 和 instance variable 之間的差別

  class variable 是指在class本身裡面所定義的變數，而instance variable則是物件被new的時候所定義的變數，因此instance variable可指物件綁定的資料，而class variable則是指該類別所綁定的資料。

4. 請說明 class method 和 instance method 之間的差別

  差別類似於class variable與instance variable的差異，class method是指class本身定義的方法，定義方法時務必使用self的語法才是指class本身，instance method則是當物件被new出來之後可使用的方法，語法差異就是不需要使用self來定義方法就是指instance method。

5. 如果今天我為一個叫 User 的 class 產生一個新物件的方式是:
  ```ruby
  User.new("Bob", "male", "Engineer")
  ```
請寫出 User class 的 initialize method

  ```ruby
  class User
    attr_accessor :name, :gender, :occupation
    def initialize(name, gender, occupation)
      @name = name
      @gender = gender
      @occupation = occupation
    end
  end
  ```


6. 在：
  A.  一個 class 裡，method 外面
  B.  一個 class 裡，instance method 裡
  self 分別是指向什麼?

  在class裡面，method外面，self指向class本身，與新增的物件無關且無法被新增的物件使用，在class裡，instance method裡self則是指物件本身，所以"self.變數名稱"會對應到物件的變數。

7. attr_accessor 的功能是什麼，它和 attr_reader、attr_writer 之間的差別是什麼？

  主要的差異在於attr_accessor包含了attr_reader加上attr_writer的功能，attr_reader只能使用getter method，attr_writer則是只能使用setter method。

8. 請說明 public 和 private method 之間的不同

  主要差異在於public method可以在class外面被使用呼叫，private method則是只能在class裡面被呼叫，無法在class外面被使用。

9. 請說明 Inheritance 和 Module 之間的差別，它們分別是用於哪些情況？ 請舉例說明

  首先Inheritance是指一個class是繼承於另一個class的，所以可以使用父類別所定義的方法以及實例變數，而Module則是只能定義方法，可以想像成工具箱，這個類別如果include這個module，則可以使用該module的所有方法。
  舉例的話可參考第二題答案，新增的sparrow物件是屬於class Bird，而Bird又是繼承於class Animal，而我在Bird這個class裡又include了Ability這個module，因此我可以呼叫此module裡面的方法fly。


10. 若今天有一個 class 有 include 一個 module，他的 parent class 和 sub class 是否可以使用該 module 裡的 method?

  parent class 無法，sub class可以。

11. 請間單說明什麼是 Relational Database，什麼是 SQL

  Database資料庫是指主機server儲存資料的統稱，表示方式會用table來表示，每一張table都會有欄位，每個欄位可能都代表不同的意義，relational database則是翻譯為關聯式資料庫，則是指當一群資料被適當的分配在資料表單裡面，而且資料可以被獲取及修改，且資料表單相互是有關聯性質的(指會互相影響)，而無需刻意去修正資料表單table本身的欄位。
  SQL(Structural Query Language)，是一種高階程式語言，簡單來說就是用來獲取及修改資料庫的資料的語言，如老師說明的crud，四大功能包含了create，read，update以及delete。
