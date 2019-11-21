
## 实验四 字符串

## 一、实验目的

掌握字符串String及其方法的使用

掌握异常处理的结构

## 二、实验要求

* 利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能函数，并运行，
  达到如下功能
    *  每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”
    *  允许提供输入参数，统计古诗中某个字或词出现的次数
    *  考虑操作中可能出现的异常，在程序中涉及异常处理程序

## 三、实验过程

    1、将《长恨歌》古诗定义成字符串类型
    
    2、定义数组char[]，将字符串中内容放到数组中
    
    3、构造一个字符缓冲区（StringBuffer）
    
    4、for循环,初始化i=0
    
       //数组下标从0开始，为了不让0参加循环，i+1
       
       1）当(i+1)%7==0&&(i+1)%2==1（i为7的倍数的奇数）是，加“，”
       
          当(i+1)%14==0&&(i+1)%2==0（i为14的倍数的偶数）时，加“。”
          
    5、定义cs（ ，“”），计算某个字或词出现的次数
    
    6、添加cs方法
    
    7、异常处理try{}catch（exception e）{}

## 四、核心代码

```javascript
  //异常处理
    	try{
		char[] chars = ss.toCharArray();//定义数组
		StringBuffer s = new StringBuffer();
		
		for (int i =0; i <chars.length; i++) {
			//在被选元素的结尾插入符号
			s.append(chars[i]);
		
			if ((i+1)%7==0&&(i+1)%2==1||(i+1)%14==0&&(i+1)%2==0) {
				//i%7等于0并且i为奇数时，在结尾加，
				if((i+1)%7==0&&(i+1)%2==1)
					s.append(",");
				
				//i%14等于0并且i为偶数时，在结尾加。
				else
					s.append("。\n");
			}
			}
		System.out.println(s.toString());
		}
		//异常处理
		catch(Exception   e){
			System.out.print("发生异常:"+e.toString());
			e.printStackTrace();
		}
		
		//计算字符串中关键字出现的次数
				countString(ss,"回眸");
		
	}

	private static void countString(String ss, String string) {
		// TODO Auto-generated method stub
		int count=0;
		while(ss.indexOf(string)!=-1){//查找字串中指定字符首次出现的位置
			//返回一个新字符串，它是此字符串的一个子字符串。
			ss = ss.substring(ss.indexOf(string)+1,ss.length());    
            count++;
		}
		System.out.println(string+" 出现的次数为:"+count+"次");
	}
```
## 五、运行结果

汉皇重色思倾国,御宇多年求不得。

杨家有女初长成,养在深闺人未识。

天生丽质难自弃,一朝选在君王侧。

回眸一笑百媚生,六宫粉黛无颜色。

春寒赐浴华清池,温泉水滑洗凝脂。

侍儿扶起娇无力,始是新承恩泽时。

云鬓花颜金步摇,芙蓉帐暖度春宵。

春宵苦短日高起,从此君王不早朝。

承欢侍宴无闲暇,春从春游夜专夜。

后宫佳丽三千人,三千宠爱在一身。

金屋妆成娇侍夜,玉楼宴罢醉和春。

姊妹弟兄皆列土,可怜光彩生门户。

遂令天下父母心,不重生男重生女。

骊宫高处入青云,仙乐风飘处处闻。

缓歌慢舞凝丝竹,尽日君王看不足。

渔阳鼙鼓动地来,惊破霓裳羽衣曲。

九重城阙烟尘生,千乘万骑西南行。

翠华摇摇行复止,西出都门百余里。

六军不发无奈何,宛转蛾眉马前死。

花钿委地无人收,翠翘金雀玉搔头。

君王掩面救不得,回看血泪相和流。
 
回眸 出现的次数为:1次

## 六、编程感想

本次实验中，数组的下标是从0开始，循环过程是也从0开始，所以就导致了0
参与循环运算，并符合了条件而输出了结果，这一最终要呈现的效果就有了出
入，思考了很久也没有找到解决办法，最后多亏了老师的指点，帮助我解决了
这个问题。在这个过程中，更加知道了自己的不足，加强自己的理解能力及学
习思考的能力。通过本次的实验，更加掌握了对字符串的使用以及循环程序的
使用。


