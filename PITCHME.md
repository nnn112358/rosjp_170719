###ROS Japan UG #11 LT大会　17/07/19 
#シミュレーションでSLAMを試す
nnn112358

---

###ROSを使うきっかけ   
 →スゴイOpenSourceのSLAMが色々使える、試してみたい。  
 　例えば、  
  gmapping・cartographer・hectorslam・Autoware・・・    

---
<div style="text-align: left;">

ROS Wiki読んだりして、SLAMを動かせる用になってきた。
  
1.シミュレーション環境が重い。使いづらい。難しい。。。ツライ。  
&nbsp;&nbsp;&nbsp;    ⇔ROS標準だとGazebo。
2.SLAMのパラメータ調整が難しい。  
&nbsp;&nbsp;&nbsp;  　⇔パラメータが一杯。どれがどう効いているのか、よくわからない。  
3.センサが高い。  
&nbsp;&nbsp;&nbsp;  　⇔値段高い方が性能良さそう(Lidarだったら、視野角・距離・距離精度)だがどれくらい違う？？  
</div>

---


そこで、、、
　こんなの課題を解決する
　Simulatorを作成した。色々、試してみる。


---


・LidarのKinematic OnlyなSimulation、軽い。
・Lidarのパラメータを任意に設定できる。測定誤差(正規分布）を指定可。
・Odometoryの誤差を設定できる。測定誤差(正規分布）を指定可。
・動的障害物を設定可。

---


アルゴリズム
 ・Lidarを線分で表現。壁・障害物を矩形で設定
　・線分と線分との交点をもとめる・
　・交点とロボットとの距離からLidarをシミュレーションする。
　・Lidar・オドメトリには正規分布に従って誤差をのせる。

---

試してみた結果
評価関数
　ロボット位置の真値とSLAM(cartographer)のx-y 距離

　線
　cartographerはLoopCloserが入っているので、

---

