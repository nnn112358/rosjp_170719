###ROS Japan UG #11 LT大会　17/07/19 
#シミュレーションでSLAMを試す
nnn112358

---

  ROS勉強するモチベーション  
 →オープンソースのSLAMを試したい。  
  gmapping・google cartographer・hectorslam・・・
  
![robot1](SLAM_image.png)


---
<div style="text-align: left;">
やり方を調べて、SLAMはとりあえず動いた。<br>
→色々、課題が出てくる。  
1. 実機なしで作り込みたい、試したい<br> 
<font size="5">シミュレーションが重い/使いづらい/ 怖い→Gazebo <br></font>
 </div>
<img src="gazebo.png" alt="" >

---

<div style="text-align: left;">
####2.実世界の外乱をシミュレーションに入れたい。<br> 
<font size="5">・センサ誤差(Lidar視野角,計測精度)/オドメトリ誤差(タイヤ滑り)<br>
・人が一杯(邪魔)</font>
</div>
![around_person](around_person.gif)

---

そこで、、、    

---

##こんな課題を解決するシミュレータを作成.
（本日の本題）  

---
[simulator(仮)](https://github.com/nnn112358/robotics_Lidar_sim2d)
![robot_video](robot_slam_video.mp4)
https://github.com/nnn112358/robotics_Lidar_sim2d		

---

<font size="6">アルゴリズム<br>
Lidarとodometoryに誤差を付与。</font>
![robot](Lidar_cal2.png)


---

<font size="6">rqt_graph<br>
SLAMの自己位置推定の軌跡と真値の軌跡を比較できる</font>
<img src="Lidar_cal4.png" alt="">


---
<div style="text-align: left;">
・まとめ<br>
<font size="6">
・Originalのシミュレータを作った<br>
・センサー誤差・移動物体といった、外乱をいれることができる。<br>
-Future work<br>
・シミュレータのpackage化と公開。<br>
</font></div>

---


----

