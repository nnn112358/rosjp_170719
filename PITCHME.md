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

##こんな課題を解決するシミュレータを作成した。「
（本日の本題）  

---

simulator(仮)
![robot_video](robot_slam_video.mp4)

---

<font size="6">アルゴリズム<br>
Lidarとodometoryに誤差を付与。</font>
![robot](Lidar_cal2.png)

---

<font size="6">アルゴリズム<br>
Lidarとodometoryに誤差を付与。</font>
![robot3](Lidar_cal3.png)

---

![robot100](Lidar_cal4.png)

---

![RESULT](RESULT.png)
<font size="5">cartographerでLidar・Odometoryのパラメータを振りながら試してみた<br>


</font>

---

Future works
・シミュレータのバイナリ化と公開。
・parameter Self-tuning。
![Future](Future.png)

---

![thanks](thanks.gif)


---


