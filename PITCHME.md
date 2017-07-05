###ROS Japan UG #11 LT大会　17/07/19 
#シミュレーションでSLAMを試す
nnn112358

---

  ROSを使うきっかけ   
 →OpenSourceのSLAMを試してみたい。  
  gmapping・cartographer・hectorslam・Autoware・・・
  
![robot1](SLAM_image.png)


---

やり方を調べて、SLAMはとりあえず動いた。   
　→色々、課題が出てくる。  
<div style="text-align: left;">
1.シミュレーション環境が重い/使いづらい。  
&nbsp;&nbsp;&nbsp;    →ROSではGazebo[汎用的な力学シミュレータ]  　
2.SLAMのパラメータ調整が一杯/難しい。  
</div>

---

<div style="text-align: left;">
3.シミュレーションで動いても実世界で動かない。   
&nbsp;&nbsp;&nbsp;  　⇔実世界とシミュレーションの違い？   
&nbsp;&nbsp;&nbsp; ・センサの制約(視野角・距離・距離精度)    
&nbsp;&nbsp;&nbsp; ・オドメトリの誤差(滑り、タイヤ径、Encoder分解能)  
&nbsp;&nbsp;&nbsp; ・人が一杯(邪魔)  
</div>

---

そこで、、、    

---

##こんな課題を解決するシミュレータを作成した。
（本日の本題）  

---

turtlesim Next(仮)
![robot_video](robot_slam_video.mp4)

---

<div style="text-align: left;">

######・Lidarセンサ想定したKinematic OnlyなSimulation、(たぶん)軽い。  
######・Lidarのパラメータを任意に設定できる。
######・Odometoryの誤差を設定できる。
######・動的障害物を設定可。  

</div>

![robot](robot_sim.png)

---

アルゴリズム  
![robot](Lidar_cal2.png)

---

試してみた結果  
評価関数  
　ロボット位置の真値とSLAM(cartographer)のx-y 距離  

　線  
　cartographerはLoopCloserが入っているので、  

---





---
