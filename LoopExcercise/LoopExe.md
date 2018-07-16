# Loop_Exercise



1. 解方程组：x+y+z=10, 2x+y+3z=20, 3x-y-z=-2.



2. ![img](file:///C:\Users\Rekol\AppData\Roaming\feiq\RichOle\3568823959.bmp) 

思路:

- 理解条件: 三种鸡的数目和三类钱都得是100;

```java 


public static void main(String[] args) {
   getNum();
   }

public static void getNum() {

    int x, y, z;

    for (x = 0; x <= 20; x++) {

        for (y = 0; y <= 33; y++) {

            for (z = 0; z <= 100; z += 3) {

                if (5 * x + 3 * y + z / 3 == 100 && x + y + z == 100) {

                    System.out.println("公鸡的数量：" + x + "\n" + "母鸡的数量：" + y + "\n" + "小鸡的数量：" + z + "\n");

                }

            }

        }

    }

}

```



3. 编写一个java程序,求:13 - 23 + 33 - 43 +...+ 973 - 983 + 993 -1003的值.

   1. [LoopExeDemo01](G:\AllTheExercise\Magic\basic-code\day04-code\src\cn\itcast\day04\LoopExercise)

   多种写法.但核心都是计数器.不同条件.

