###ROS Japan UG #11 LT大会　17/07/19 
#シミュレーションでSLAMを試す
nnn112358

---

  ROSを始めたきっかけ   
 →オープンソースのSLAMを試したい。  
  gmapping・google cartographer・hectorslam・・・
  
![robot1](SLAM_image.png)


---
<div style="text-align: left;">
やり方を調べて、SLAMはとりあえず動いた。<br>
→色々、課題が出てくる。  
1. 実機なしで作り込みたい<br> 
   シミュレーションが重い/使いづらい→Gazebo <br>
 </div>
<img src="gazebo.png" alt="" >

---


<div style="text-align: left;">
####2.実世界の外乱をシミュレーションに入れたい。<br> 
&nbsp;&nbsp;&nbsp;・センサ誤差(Lidar視野角,計測精度/オドメトリ誤差)<br>
&nbsp;&nbsp;&nbsp;・人が一杯(邪魔)<br>
</div>
![around_person](around_person.gif)

---

そこで、、、    

---

##こんな課題を解決するシミュレータ！
（本日の本題）  

---

turtlesim Next(仮)
![robot_video](robot_slam_video.mp4)

---

アルゴリズム  
![robot](Lidar_cal2.png)

---
  
![robot3](Lidar_cal3.png)

---

![robot100](Lidar_cal4.png)

---

<font size="2">cartographerでLidar・Odometoryのパラメータを振りながら試してみる</font>

![RESULT](RESULT.png)

---

Future
・シミュレータのバイナリ化と配布。
・自動パラメータチューニング。
![Future](Future.png)

---

![thanks](thanks.gif)


---


