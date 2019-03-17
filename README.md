# 飞鸟群控
PC电脑控制手机，请查看https://github.com/bandy101/flybirdremotecontroller





# simulate-touch（iOS按键精灵）

<img src="https://github.com/bandy101/simulate-touch/blob/master/IMG_0109.PNG" width="200px" /><img src="https://github.com/bandy101/simulate-touch/blob/master/IMG_0111.PNG" width="200px" /><img src="https://github.com/bandy101/simulate-touch/blob/master/IMG_0112.PNG" width="200px" />

基于iOS越狱系统已实现

1.按键精灵框架（TTouch）

2.手机控制控制手机

3.电脑控制手机

http://www.cnblogs.com/bandy/

企鹅号 6-2-4-3-0-0-7-5-6







# TTouch API 文档


###  1. 系统模块（sys）
1.1 毫秒级延迟
* 函数

      sys.msleep(float ms)
* 入参

      毫秒数，1000毫秒=1秒  
* 示例

      sys.msleep(1000)--延迟1000毫秒（1秒）
###  2. 触摸模块(touch)
2.1 按下手指(touch.down)
* 函数

      touch.down(int index,int x,int y)
* 入参

      index:第几个手指
      x:屏幕x坐标
      y:屏幕y坐标  
* 示例

      touch.down(1,100,200）-- 在屏幕(100,200)的位置按下手指
2.2 移动手指(touch.move)
* 函数

      touch.move(int index,int x,int y)
* 入参

      index:第几个手指
      x:屏幕x坐标
      y:屏幕y坐标  
* 示例

      touch.move(1,100,200）-- 手指1移动到(100,200)的位置
2.3 抬起手指(touch.up)
* 函数

            touch.up(int index,int x,int y)
* 入参

            index:第几个手指
            x:屏幕x坐标
            y:屏幕y坐标  
* 示例

            touch.up(1,100,200）-- 手指1在(100,200)的位置抬起
2.4 示例
* 点击

          touch.down(7,128,110)
          sys.msleep(16.71)
          touch.up(7,128,110)

* 滑动

          touch.down(8,709,869)
          sys.msleep(32.98)
          touch.move(8,686,871)
          sys.msleep(17.99)
          touch.move(8,671,872)
          sys.msleep(18.00)
          touch.move(8,657,874)
          sys.msleep(16.06)
          touch.move(8,645,874)
          sys.msleep(17.53)
          touch.move(8,633,875)
          sys.msleep(16.96)
          touch.move(8,612,876)
          sys.msleep(16.72)
          touch.move(8,588,877)
          sys.msleep(16.27)
          touch.move(8,561,878)
          sys.msleep(15.87)
          touch.move(8,527,880)
          sys.msleep(17.06)
          touch.move(8,500,884)
          sys.msleep(15.95)
          touch.move(8,464,889)
          sys.msleep(17.98)
          touch.move(8,438,893)
          sys.msleep(17.10)
          touch.move(8,404,900)
          sys.msleep(15.67)
          touch.move(8,378,905)
          sys.msleep(16.50)
          touch.move(8,349,912)
          sys.msleep(16.43)
          touch.move(8,325,918)
          sys.msleep(16.44)
          touch.move(8,302,924)
          sys.msleep(17.48)
          touch.move(8,281,931)
          sys.msleep(17.76)
          touch.move(8,258,941)
          sys.msleep(16.16)
          touch.move(8,226,957)
          sys.msleep(16.42)
          touch.move(8,184,983)
          sys.msleep(16.54)
          touch.move(8,152,1003)
          sys.msleep(16.04)
          touch.up(8,148,1007)

###  3. 按键模块（key）
3.1 按键按下
* 函数

      key.down(string keystr)
* 入参

      按键类型
      home：菜单键
      lock:锁屏键
      volup:音量+键
      voldown:音量-键
* 示例
3.2 按键抬起
* 函数

      key.up(string keystr)
* 入参

      按键类型
      home：菜单键
      lock:锁屏键
      volup:音量+键
      voldown:音量-键
* 示例

3.2 综合示例
* 按下菜单键

        key.down("home")
        sys.msleep(130.91)
        key.up("home")
* 截图

        key.down("home")
        sys.msleep(158.70)
        key.down("lock")
        sys.msleep(77.66)
        key.up("home")
        sys.msleep(124.04)
        key.up("lock")

###  4. 屏幕模块（screen）

4.1 屏幕找图(screen.find_image)
* 函数

      screen.find_image(string imagepath,int s,int x,int y,int w,int h)

      screen.find_image(string imagepath,int s)

      screen.find_image(string imagepath)
* 入参

      imagepath:需要查找的图片路径
      s:匹配相似度0-100，100为100%匹配，默认80
      x:查找屏幕范围x坐标
      y:查找屏幕范围y坐标
      w:查找范围宽
      h:查找范围高
* 返回
  （x,y）查找到的中心点坐标

* 示例

      x,y=screen.find_image("/usr/1.png")  --查找图片
      touch.down(1,x,y）-- 在屏幕(x,y)的位置按下手指
