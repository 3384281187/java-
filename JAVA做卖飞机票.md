# JAVA做卖飞机票

要求：

用键盘输入机票价格，月份和头等舱或者经济舱

5月~10月为旺季头等舱打9折，经济舱打8.5折

11月~12月和1月~4月为淡季头等舱为7折，经济舱为6.5折

第一种做法

```java
package anli;
import java.util.Scanner;
//卖飞机票
public class fjp {
    public static void main(String[] args) {
        Scanner wl=new Scanner(System.in);
        double money= wl.nextDouble();//飞机票的价格
        int month=wl.nextInt();//月份
        boolean First_Economy= wl.nextBoolean();//true为头等舱，false为经济舱
        if(month>=5&&month<=10){//旺季
            if(First_Economy)//判断是头等舱还是经济舱
                money*=0.9;//头等舱*0.9
            else
                money*=0.85;//经济舱*0.85
        }
        else if((month>=11&&month<=12)||(month>=1&&month<=4)){//淡季
            if(First_Economy)//判断是头等舱还是经济舱
                money*=0.7;//头等舱*0.7
            else
                money *= 0.65;//经济舱*0.65
        }
        else
            System.out.println("请输入一个正确的月份");
        System.out.println("机票价格为"+money+"元");
        System.out.println("月份为"+month+"月份");
        if(First_Economy)
            System.out.println("头等仓");
        else
            System.out.println("经济仓");
    }
}

```

第二种做法

```java
package anli;
import java.util.Scanner;
//卖飞机票
public class fjp {
    public static void main(String[] args) {
        Scanner wl=new Scanner(System.in);
        double money= wl.nextDouble();//飞机票的价格
        int month=wl.nextInt();//月份
        boolean First_Economy= wl.nextBoolean();//true为头等舱，false为经济舱
        if(First_Economy)
            wl1(money,month);
        else
            wl2(money,month);
    }

    public static void wl1(double money1,int month1) {
        if(month1>=5&&month1<=10)//旺季
            money1*=0.9;//头等舱*0.9
        else if((month1>=11&&month1<=12)||(month1>=1&&month1<=4))//淡季
            money1*=0.7;//头等舱*0.7
        System.out.println("机票价格为"+money1+"元");
        System.out.println("月份为"+month1+"月份");
        System.out.println("头等舱");
    }
    public static void wl2(double money2,int month2){
        if(month2>=5&&month2<=10)//旺季
            money2*=0.85;//经济舱*0.7
        else if((month2>=11&&month2<=12)||(month2>=1&&month2<=4))//淡季
            money2*=0.65;//经济舱*0.65
        System.out.println("机票价格为"+money2+"元");
        System.out.println("月份为"+month2+"月份");
        System.out.println("经济舱");
    }
}

```

