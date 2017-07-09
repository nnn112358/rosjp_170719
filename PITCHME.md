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
<font size="5">シミュレーションが重い/使いづらい→Gazebo <br></font>
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

##こんな課題を解決するシミュレータを作成した。
（本日の本題）  

---
[simulator(仮)](https://github.com/nnn112358/robotics_Lidar_sim2d)
![robot_video](robot_slam_video.mp4)

---

<font size="6">アルゴリズム<br>
Lidarとodometoryに誤差を付与。</font>
![robot](Lidar_cal2.png)

---
<div style="text-align: left;">

<font size="6">rqt_graph<br>
cmd_vei(twist)/move_onst(twist)をInput,Scan(LaserScan)/odom(odom)/tf(odom→base_link)をOutput
</font></div>
![robot3](Lidar_cal3.png)

---

<font size="6">rqt_graph<br>
SLAMの自己位置推定の軌跡と真値の軌跡を比較できる</font>
![robot100](Lidar_cal4.png)

---

<div style="text-align: left;">
![RESULT](slam_result.png)
<font size="5">gmapping/cartographerでLidar・Odometoryのパラメータ<br>
を振りながら、SLAMの自己位置推定と真値との差分を求めてみた。<br>


</font></div>

---
<div style="text-align: left;">
<font size="6">
・Originalのシミュレータを作成<br>
・実機レスでSensorとSLAMの性能評価ができる/(たぶん)動作軽い。<br>
・センサー誤差・移動物体といった、外乱をいれることができる。<br>
Future works<br>
・シミュレータのpackage化と公開。<br>
</font></div>
---

![thanks](thanks.gif)


---


