# 四.集合框架
## 1. String类：字符串(重点)

```
1. 创建字符串对象
     (1)String()：无参构造。
         举例：
             String s = new String();
             s = "hello";
             sop(s);
     (2)String(byte[] bys)：传一个字节数组作为参数。
         举例：
             byte[] bys = {97,98,99,100,101};
             String s = new String(bys);
             sop(s);
     (3)String(byte[] bys,int index,int length)：把字节数组的一部分转换成一个字符串。 
         举例：
             byte[] bys = {97,98,99,100,101};
             String s = new String(bys,1,2);
             sop(s);
     (4)String(char[] chs)：传一个字符数组作为参数。
         举例：
             char[] chs = {'a','b','c','d','e'};
             String s = new String(chs);
             sop(s);
     (5)String(char[] chs,int index,int length)：把字符数组的一部分转换成一个字符串。
         举例：
             char[] chs = {'a','b','c','d','e'};
             String s = new String(chs,1,2);
             sop(s);	
     (6)String(String str)：把一个字符串传递过来作为参数。
         举例：
             char[] chs = {'a','b','c','d','e'};
             String ss = new String(s);
             sop(ss);
     (7)直接把字符串常量赋值给字符串引用对象。(最常用)
         举例：
             String s = "hello";
             sop(s);
2. 面试题
     (1)请问String s = new String("hello");创建了几个对象。
         答：两个。一个"hello"字符串对象，在方法区的常量池；一个s对象，在栈内存。

     (2)请写出下面的结果
         String s1 = new String("abc");
         Strign s2 = new String("abc");
         String s3 = "abc";
         String s4 = "abc";

         sop(s1==s2);  //false
         sop(s1==s3);  //false
         sop(s3==s4);  //true
		 
     (3)字符串对象一旦被创建就不能被改变。
         指的是字符串常量值不改变。
4. 字符串中各种功能的方法
     (1)判断
         boolean equals(Object anObject)：判断两个字符串的内容是否相同，复写了Object的方法。
         boolean equalsIgnoreCase(String anotherString)：判断两个字符串的内容是否相同，不区分大小写。
         boolean contains(String s)：判断一个字符串中是否包含另一个字符串。
          注意：判断字符串是否包含特殊字符.直接表示为str.contains(".")。
         boolean endsWith(String suffix)：测试此字符串是否以指定的后缀结束。
         boolean startsWith(String suffix)：测试此字符串是否以指定的前缀开始。
         boolean isEmpty()：测试字符串是否为空。
     (2)获取
         int length()：返回此字符串的长度。
         char charAt(int index)：返回指定索引处的 char值。
         int indexOf(int ch)：返回指定字符在此字符串中第一次出现处的索引。
         int indexOf(int ch, int fromIndex)：返回在此字符串中第一次出现指定字符处的索引，从指定的索引开始搜索。 
         int indexOf(String str)：返回指定子字符串在此字符串中第一次出现处的索引。 
         int indexOf(String str, int fromIndex)：返回指定子字符串在此字符串中第一次出现处的索引，从指定的索引开始。 
         int lastIndexOf(int ch)：返回指定字符在此字符串中最后一次出现处的索引。 
         int lastIndexOf(int ch, int fromIndex)：返回指定字符在此字符串中最后一次出现处的索引,从指定的索引处开始进行反向搜索。 
         int lastIndexOf(String str)：返回指定子字符串在此字符串中最右边出现处的索引。 
         int lastIndexOf(String str, int fromIndex)：返回指定子字符串在此字符串中最后一次出现处的索引，从指定的索引开始反向搜索。 
         String substring(int beginIndex) (注意：该方法substring的String是小写！)：返回一个新的字符串，它是此字符串的一个子字符串。 
         String substring(int beginIndex, int endIndex) (注意该方法的String是小写！)：返回一个新字符串，它是此字符串的一个子字符串,包含头不包含尾。 
     (3)转换
         byte[] getBytes()：(很常用！)从字符串到字节数组的方法。
         void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)：将字符从此字符串复制到目标字符数组。
         char[] toCharArray()：(很常用！)从字符串到字符数组的方法。
         static String copyValueOf(char[] data)：返回指定数组中表示该字符序列的 String。 
         static String copyValueOf(char[] data, int offset, int count)：返回指定数组中表示该字符序列的 String。
         static String valueOf(数据类型):把该数据类型的数据转换成字符串。
         String toLowerCase()：把字符串转换成小写。
         String toUpperCase()：把字符串转换成大写。
         String concat(String str)：将指定字符串连接到此字符串的结尾。
     (4)替换
         String replace(char oldChar, char newChar)：用新字符替换旧字符(替换所有)。
         String replace(String target, String replacement)：用新的子串换旧串。
     (5)分割
         String[] split(String regex)：根据指定的字符串把一个字符串分割成一个字符串数组。
     (6)去空格	
         String trim()：去除字符串的前后空格。
     (7)比较
         int compareTo(String anotherString)：按字典顺序比较两个字符串。 
         int compareToIgnoreCase(String str)：按字典顺序比较两个字符串，不考虑大小写。 

```

## 2. StringBuffer

```
1. 字符串的缓冲区，是一个容器。
2. 它和String的区别
     它是缓冲区可变长度的。
3. 构造方法
     StringBuffer()：构造一个其中不带字符的字符串缓冲区，初始容量为 16 个字符。
     StringBuffer(int num)：构造一个不带字符，但具有指定初始容量的字符串缓冲区。
     StringBuffer(String str)：构造一个字符串缓冲区，并将其内容初始化为指定的字符串内容。
4. 常用方法
     (1)增加数据
         append()：添加各种类型的数据。
         insert()：在容器指定位置插入各种类型的数据。
     (2)删除数据
         deleteCharAt()：删除指定位置的字符。
         delete()：还可以用于清空StringBuffer的缓冲区。
     (3)替换
         replace()
     (4)获取 
         charAt() 
     (5)长度和容量
         length()：元素的个数。
         capacity()：元素的理论值。
     (6)获取元素的位置
         indexOf()
         lastIndexOf()
     (7)截取
         substring(int start)
         substring(int start,int end)
     (8)反转
         reverse
5. 字符串和StringBuffer的转换
     (1)String-->StringBuffer通过构造
         如：StringBuffer sb = new StringBuffer(String str)
     (2)StringBuffer--String通过toString()方法 
         如：StringBuffer sb = new StringBuffer();
             sb.toString();
```


## 3. StringBuilder

```
和StringBuffer的功能是一样的，但是有区别：
  1. StringBuffer(JDK1.0)是线程安全的。
  2. StringBuilder(JDK1.5)不保证线程安全。
一般来说，我们写的程序都是单线程的，所以，用StringBuilder，效率高。
```

## 4. 基本数据类型的对象包装类

```
1. 用途
     将基本数据类型封装成对象的好处在于可以在对象中定义更多的功能操作该数据。
     常用的操作之一：用于基本数据类型与字符串之间的转换。
2. 基本数据类型和对象类型的对应
     byte        Byte
     short	 Short 
     int         Integer
     long        Long
     float       Float
     double      Double
     boolean     Boolean
     char        Character
3. 构造方法
     static int MAX_VALUE 值为 2^31-1 的常量，它表示int类型能够表示的最大值。
     static int MIN_VALUE  值为 -2^31 的常量，它表示int类型能够表示的最小值。
     static Class<Integer> TYPE 表示基本类型int的Class 实例。
     Integer(int value) 构造一个新分配的Integer对象，它表示指定的int值。
     Inreger(String s)
     注意：s必须是纯数字的字符串。否则会有异常NumberFormatException。
4. 几个常用的方法
     Integer.toBinaryString()：以二进制无符号整数形式返回一个整数参数的字符串。
     Integer.toOctalString()：以八进制无符号整数形式返回一个整数参数的字符串。
     Integer.toHexString()：以十六进制无符号整数形式返回一个整数参数的字符串。
     static int Integer.parseInt(String s)：将字符串参数作为有符号的十进制整数进行解析,字符串必须是int型范围内的数字字符串。
     static int Integer.parseInt(String s,int basic)：使用第二个参数指定的基数,将字符串参数解析为有符号的整数。字符串必须是int型范围内的数字字符串。
     short shortValue()：以short类型返回该Integer的值。          
     int intValue()：以int类型返回该Integer的值。
     static Integer valueOf(int num)：返回一个表示指定的 int 值的 Integer 实例。
     static Integer valueOf(String s)：返回保存指定的String的值的Integer对象。           
     static Integer valueOf(String s, int radix)：返回一个Integer对象，该对象中保存了用第二个参数提供的基数进行。解析时从指定的String中提取的值。 

5. 类型转换
     (1)int --> Integer
          int num = 20;
          a:Integer i = new Integer(num);
          b:Integer i = Integer.valueOf(num);
     (2)Integer --> int
          Integer i = new Integer(20);
          a:int num = i.intValue();
     (3)int --> String
          int num = 20;
          a:String s = String.valueOf(num);
          b:String s = ""+num;
          c:String s = Integer.toString(num);
     (4)String --> int
          String s = "20";
          a:int num = Integer.parseInt(s);
          b:Integer i = new Integer(s);
            或者：Integer i = Integer.valueOf(s);
                  int num = i.intValue();
```

## 5. 集合框架

```
1. 为什么出现集合类？
     面向对象对事物的体现都是以对象的形式，为了方便对多个对象的操作，就对对象进行存储。
     //集合就是存储对象最常用的一种方式。
2. 数组和集合都是容器，两者有何不同？
     (1)数组长度固定，而集合长度是可变的。	
     (2)数组值可以存储对象，还可以存储基本数据类型;而集合只能存储对象。	
     (3)数组存储数据类型是固定的，而集合存储的数据类型不固定。		
3. 集合类的特点
     (1)集合只能存储对象。
     (2)集合的长度是可变的。
     (3)集合可以存储不同类型的对象。
```
## 6. 集合类框架分类(重要！！！要分清几种容器间的区别)
```
1. Collection：顶层接口
     (1)List：集合
         元素是有序的(元素带角标索引)，可以有重复元素,可以有null元素。
        a:ArrayList
          数据结构：数组。
          特点：
              ①查询速度快(因为带角标)，但是增删速度稍慢。(因为当元素多时，增删一个元素则所有元素的角标都得改变)
              ②线程不同步。
              ③默认长度是10，当超过长度时，按50%延长集合长度。				
        b:LinkedList
          数据结构：链表(即后面一个元素记录前一个)。
          特点：
              ①查询速度慢。(因为每个元素只知道前面一个元素)
              ②增删速度快。(因为元素再多，增删一个，只要让其前后的元素重新相连即可)
              ③线程不同步。					
        c:Vector
           数据结构：数组。
           特点：
               ①查询和增删速度都很慢。
               ②线程同步。
               ③默认长度是10，当超过长度时,按100%延长集合长度。
      注意：
          ①Vector功能跟ArrayList功能一模一样，已被ArrayList替代。
          ②对于List集合，无论是add、contains、还是remove方法，判断元素是否相同，都是通过复写equals方法来判断！
        
         一般情况下，使用哪种List接口下的实现类呢？
           ①如果要求增删快，考虑使用LinkedList。
           ②如果要求查询快，考虑使用ArrayList。
           ③如果要求线程安全，考虑使用Vector。
     (2)Set：集合
         元素唯一。可以有null元素。
        a:HashSet
          数据结构：哈希表。
          特点：
              ①存取速度快。
              ②元素唯一。
              ③线程不同步。
          保证性元素唯一的原理:
              先判断元素的hashCode值是否相同，再判断两元素的equals方法是否为true(往HashSet里面存的自定义元素要复写hashCode和equals方法， 以保证元素的唯一性！)
        b:TreeSet
          数据结构：二叉树。
          特点：
              ①元素有序。
              ②线程不同步。
           保证元素唯一性的依据：compareTo()方法return 0。
      注意：
          ①HashSet
             为了保证元素的唯一性，我们通常在往HashSet集合里面存储元素时，在定义对象的类中通常复写hashCode和equals方法。
           HashSet是如何保证元素唯一性的呢？
    	     如果两元素的hashCode值不同，则不会调用equals方法。
     	     如果两元素的hashCode值相同，则继续判断equals是否返回true。
          ②TreeSet
             TreeSet要求往里面存的元素具备比较性，否则会报错。
             TreeSet排序的第一种方式：让元素自身具备比较性。
             定义对象类，实现Compareble接口,复写compareTo方法，此方式是元素的自然顺序。		      
2. Map：顶层接口
     存储方式：键值对,键唯一。
     Set集合底层使用了Map集合(Set和Map很相似)。
   注意：
       Map集合没有迭代器，要取出元素必须先将Map集合转换成Set集合才能遍历元素。
     (1)HashTable
         数据结构：哈希表。
         特点：
             ①键和值都不能为null。
             ②效率低。
             ③线程同步。
         保证键的唯一性：用作键的对象必须实现hashCode和equals方法。		
     (2)HashMap
         数据结构：哈希表。
         特点：
             ①键和值可以为null。
             ②效率高。
             ③线程不同步。
         保证元素唯一性:先判断元素的hashCode值是否相同，再判断两元素的equals方法是否为true。(往HashSet里面存的自定义元素要复写hashCode和equals方法，以保证元素的唯一性！)
     (3)TreeMap
         数据结构：二叉树。
         特点：
             ①键和值可以为null。
             ②线程不同步。
3. Iterator：迭代器
      Iterator模式是用于遍历集合类的标准访问方法。它可以把访问逻辑从不同类型的集合类中抽象出来，从而避免向客户端暴露集合的内部结构
      迭代器取代了Enumeration(枚举)。
     (1)迭代器和枚举的区别
		①迭代器允许调用者利用定义良好的语义在迭代期间从迭代器所指向的collection移除元素。
		②方法名称得到了改进，简化书写。
```

## 7. Map集合和Collection集合的区别？

```
1. Map中存储是键值对。Collection中存储是单个元素。
2. Map的存储使用的put方法。Collection存储使用的是add方法。 
3. Map集合没有迭代器，Map的取出，是将Map转成Set，再使用迭代器取出。Collection取出，使用就是迭代器。
选择方式：
  1. 如果对象很多，必须使用集合存储。
  2. 如果元素存在着映射关系，可以优先考虑使用Map存储或者用数组。
  3. 如果没有映射关系，可以使用Collection存储。
```

## 8. 迭代器：Iterator(Map集合没有迭代器)

```
1. 迭代器就是取出集合元素的方式
2. 获取迭代器的方法
     Iterator<E> iterator()：返回在此 collection的元素上进行迭代的迭代器。 
     Iterator<E> iterator()：返回在此 set 中的元素上进行迭代的迭代器。      
3. 迭代器方法
     boolean hasNext()：如果仍有元素可以迭代,则返回 true。
     E next()：返回迭代的下一个元素。       
     void remove()：从迭代器指向的collection中移除迭代器返回的最后一个元素（可选操作）。
```



## 9. 堆栈和队列

```
堆栈：先进后出，比如：穿衣服。
队列：先进先出，比如：排队打饭。
```

## 10. 集合类各种容器的使用注意细节

```
1. 迭代器
     (1)迭代器的next方法是自动向下取元素，要避免出现NoSuchElementException。也就是在迭代循环中调用一次next方法一次就要hasNext判断一次。
        比如：语句sop(it.next()+"..."+it.next())会发生上述异常。
     (2)迭代器的next方法返回值类型是Object，所以要记得类型转换,应用泛型后就不用强转。
2. List集合
     (1)List集合元素带角标，所以元素有序。
     (2)List集合可以含重复元素，也可以含null。  
     (3)List集合有迭代器Iterator，还有一个特有迭代器列表ListIterator。
     (4)List集合中判断元素是否相同都是用equals方法，无论contains、remove都依赖equals方法。
3. Set集合
     (1)Set接口里元素是唯一的，可以包含null。
     (2)Set集合只有一种取出方式，就是迭代器Iterator。
     (3)HashSet
        ①数据结构：哈希表。元素是无序的，唯一的。
        ②线程不同步。
     (4)TreeSet
        ①数据结构：二叉树。元素是有序的，唯一的。
        ②线程不同步。
        ③TreeSet集合要求往集合里存放的元素自身具备比较性，否则会报错。
4. Map集合
     (1)Hashtable
         哈希表结构，线程安全的，键和值不能为null。
     (2)HashMap
         哈希表结构，线程不安全的，键和值可以为null。
     (3)LinkedHashMap
         链表和哈希表，线程不安全。
     (4)TreeMap
         二叉树，线程不安全的。
```

## 12. 面试题（集合框架）

```
如果你想将一组对象按一定顺序存取，在不考虑并发访问的情况下会使用__C__ , 反之则会使用__A__；
如果你想存储一组无序但唯一的对象，你会使用__B__； 
如果你想按关键字对对象进行存取，在不考虑并发访问的情况下会使用__D__ ,反之则会使用__E__。
A. Vector
B. HashSet
C. ArrayList
D. HashMap
E. Hashtable
```

## 13. 泛型

```
1. 为什么会出现泛型？
     (1)因为集合存放的数据类型不固定，故往集合里面存放元素时，存在安全隐患。
     (如果在定义集合时，可以想定义数组一样指定数据类型，那么就可以解决该类安全问题)
     (2)JDK1.5后出现了泛型，用于解决集合框架的安全问题。
     (3)泛型是一个类型安全机制。
2. 泛型定义格式
     通过<>来定义要操作的引用数据类型。
      比如：ArrayList<String> al = new ArrayList<String>;
3. 泛型的好处
     (1)将运行时期出现的ClassCastException(类型转换异常)问题转移到编译时期。
     (2)避免了强制转换的麻烦。
4. 泛型的形式
     (1)泛型类：即自定义泛型类。
        A：当类中要操作的引用数据类型不确定时，早期定义Object来完成扩展，现在定义泛型来完成。
        B：局限性，泛型类定义的泛型，在整个类中有效，如果该泛型类的方法被调用，当泛型类的对象明确要操作的类型后，所有要操作的类型就被固定。
     (2)泛型方法：泛型放在返回值前面，修饰符的后面。
        A:为了避免泛型类的局限性，让不同方法可以操作不同的类型，而且类型还不确定，则可以将泛型定义在方法上。
        B:特殊之处，静态方法不可以访问类上定义的泛型。
        如果静态方法操作的应用数据类型不确定，可以将泛型定义在静态方法上。
     (3)泛型接口
        当泛型定义在接口上时，则子类中要指定实现接口类型，同时还可以子类也可以定义为泛型类。
5. 泛型的高级应用：？通配符
     (1)当指定两种泛型的集合，则迭代时也要定义两种泛型的迭代器，有点麻烦，此时可通过将迭代器的泛型改为？
       如：Iterator<?> it=al.iterator();
     (2)两种泛型限定
         向上限定： ? extends E;   E可以接收E类型或者E的子类。
         向下限定： ?   super E;   E可以接收E类型或者E的父类。
```

## 14. 高级for循环

```
1. 高级for循环，只用于集合和数组的遍历，集合只能用Collection不能用Map集合。
   只有把Map集合转化成Set集合，才能用for循环。
2. 格式
     for(数据类型 变量名:被遍历的集合(Collection)或者数组){
         
     }
3. 局限性
     (1)必须要有遍历的目标。
     (2)对集合或者数组进行遍历时，只能获取集合元素，不能对集合元素进行操作。
     (3)迭代器除了遍历，还可以进行remove操作集合中的元素。
     (4)列表迭代器还可以在遍历过程中进行增删改查的操作。
4. 传统for循环和高级for循环的区别
     (1)高级for循环有一个局限性，就是必须要有遍历的目标(集合或者数组)。
     (2)遍历数组时建议使用传统for循环，因为可以定义角标，比如打印100次helloworld时用传统for循环方便。
```

## 15. 可变参数

```
1. 数组的可变参数
     格式：
         int... arr
2. 方法的可变参数
     格式：
         public static void show(String str，int... arr){
             
         }
     注意：可变参数一定要放在参数列表的最后面。
```

## 16. 静态导入

```
import static java.util.Arrays.* ：导入的是Arrays这个类中所有的静态方法。

1. 静态方法摘要
     static <T> boolean addAll(Collection<? super T> c, T... elements)：将所有指定元素添加到指定 collection 中。
     static <T> void fill(List<? super T> list, T obj)：使用指定元素替换指定列表中的所有元素。
     static <T> boolean replaceAll(List<T> list, T oldVal, T newVal)：使用另一个值替换列表中出现的所有某一指定值。 
     static void reverse(List<?> list)：反转指定列表中元素的顺序。 
     static <T> Comparator<T>  reverseOrder()：返回一个比较器，它强行逆转实现了Comparable 接口的对象 collection 的自然顺序。
     static <T> Comparator<T> reverseOrder(Comparator<T> cmp)：返回一个比较器，它强行逆转指定比较器的顺序。 
2. Collections类特牛的方法
     集合有一个共同的缺点，那就是线程不安全，被多线程操作时，容易出现问题，虽然可以自己加锁，但是麻烦。
     Collections提供特牛的方法，就是给它一个不同步的集合，它返回一个同步的安全的集合。
       static <T> Collection<T> synchronizedCollection(Collection<T> c)：返回指定 collection 支持的同步（线程安全的）collection。
       static <T> List<T>  synchronizedList(List<T> list)：返回指定列表支持的同步（线程安全的）列表。 
       static <K,V> Map<K,V> synchronizedMap(Map<K,V> m)：返回由指定映射支持的同步（线程安全的）映射。 
       static <T> Set<T> synchronizedSet(Set<T> s)：返回指定 set 支持的同步（线程安全的）set。 
       static <K,V> SortedMap<K,V> synchronizedSortedMap(SortedMap<K,V> m)：返回指定有序映射支持的同步（线程安全的）有序映射。 
       static <T> SortedSet<T>  synchronizedSortedSet(SortedSet<T> s)：返回指定有序 set 支持的同步（线程安全的）有序 set。
```

## 17. Arrays类
	
```
此类包含用来操作数组（比如排序和搜索）的各种方法。里面都是静态方法。

1. 静态方法摘要
     static <T> List<T> asList(T... a)：返回一个受指定数组支持的固定大小的列表。
    注意：
     (1)该方法将一个数组变成集合后，不可以使用集合的增删方法，因为数组的长度是固定的！
        如果增删，则发生UnsupportedOprationException。(不支持操作异常)
     (2)如果数组中的元素都是基本数据类型，则该数组变成集合时，会将该数组作为集合的一个元素出入集合。
     (3)如果数组中的元素都是对象，如String，那么数组变成集合后，数组中的元素就直接转成集合中的元素。
```

## 18. 数组变集合以及集合变数组的对比

```
1. 数组变集合
     方法：static <T> List<T> asList(T... a)：返回一个受指定数组支持的固定大小的列表。
     好处：可以使用集合的思想和方法操作数组中的元素，数组是一个对象，但是数组中的功能很少。
2. 集合变数组
     方法：Collction中的toArray方法。
     好处：可以限定对集合元素的操作，防止对集合的元素进行增删，因为数组长度是固定的。
```

## 19. Collections类和Arrays类的使用。(重点)

```
1. Collections
     (1)排序
     (2)二分查找
     (3)发转
2. Arrays
     (1)把数组变成字符串输出
     (2)排序
     (3)二分查找
```


## 20. Runtime
	
```
1. 每个 Java 应用程序都有一个 Runtime类实例，使应用程序能够与其运行的环境相连接。
2. 通过 getRuntime 方法获取当前运行时。 
3. 应用程序不能创建自己的 Runtime 类实例。
4. 该类没有构造函数，也就是它不能直接创建对象。
3. 该类是单例设计模式，保证在内存中只有一个对象。
4. 方法摘要
     Process exec(String command)：在单独的进程中执行指定的字符串命令。
     void gc()：运行垃圾回收器。
     static Runtime getRuntime()：返回与当前 Java 应用程序相关的运行时对象。
     void exit(int status)：通过启动虚拟机的关闭序列，终止当前正在运行的 Java 虚拟机。
```

## 21. Date

```
1. 构造方法
     Date()：分配Date对象并初始化此对象，表示分配它的时间（精确到毫秒）。
     Date(long date)：分配Date对象并初始化此对象，表示自标准基准时间以来的指定毫秒数。
     (标准基准时间：称为“历元(epoch)”，即1970年1月1日00:00:00GMT)
2. 方法摘要
     int compareTo(Date anotherDate)：比较两个日期的顺序。         
     boolean equals(Object obj)：比较两个日期的相等性。
```

## 22. Calendar
	
```
1. 直接子类： GregorianCalendar 
2. 构造方法
     protected  Calendar()：构造一个带有默认时区和语言环境的 Calendar。
     protected  Calendar(TimeZone zone, Locale aLocale)：构造一个带有指定时区和语言环境的 Calendar。         
3. 方法摘要
     static Calendar getInstance()：使用默认时区和语言环境获得一个日历。
```
