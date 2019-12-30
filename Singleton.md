## Singleton

8种写法，只有2种是perfect的，但工作中不一定要用perfect的。  

### 1. 最简单版
类加载到内存里，就实例化一个instance，JVM保证线程安全。  
*因为JVM保证每个class只会load到内存一次。static变量是在class load到内存之后马上就初始化的。  
简单实用，推荐使用！多数情况已经够用了。  
唯一缺点：不管用到与否，load class时就完成实例化。但是你不用它干嘛load它。  
```java
public class Mgr01 {
  private static final Mgr01 INSTANCE = new Mgr01();

  private Mgr01() {};
  
  public static Mgr01 getInstance() {
    return INSTANCE;
  }
  
  public void m() {
    System.out.println("m");
  }
}
    
```


### 3. Lazy Loading 
啥时候用啥时候初始化，有thread safe的问题。  



