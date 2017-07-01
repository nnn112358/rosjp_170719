###ROS Japan UG #11 LT大会　17/07/19 
#シミュレーションでSLAMを試す
nnn112358

---

###ROSを使うきっかけ   
 →スゴイOpenSourceのSLAMが色々使える、試してみたい。  
 　例えば、  
  gmapping・cartographer・hectorslam・Autoware・・・    

---

ROS Wiki読んで、だんだんSLAMを動かせる用になってきた。  
<div style="text-align: left;">
1.シミュレーション環境が重い。使いづらい。難しい。。。ツライ。  
&nbsp;&nbsp;&nbsp;    ⇔ROSではGazebo[汎用的な力学シミュレータ]  
2.SLAMがいっぱいある   
&nbsp;&nbsp;&nbsp;  　⇔どれが良いのか？   
3.SLAMのパラメータ調整が難しい。  
&nbsp;&nbsp;&nbsp;  　⇔パラメータが一杯。どれがどう効いているのか、よくわからない。    
</div>

---

<div style="text-align: left;">
4.SLAMにとってのストレス条件を知りたい。
&nbsp;&nbsp; ストレス条件とは？  
&nbsp;&nbsp;&nbsp; ・センサの制約(視野角・距離・距離精度)    
&nbsp;&nbsp;&nbsp; ・オドメトリの誤差(滑り、タイヤ径、Encoder・Counterの精度)  
&nbsp;&nbsp;&nbsp; ・人が一杯(邪魔)  
  
---

そこで、、、    

---

こんな課題を解決するシミュレータを作成した。
（本日の本題）  

---
亀の何か(仮)

・Lidarセンサ想定したKinematic OnlyなSimulation、(たぶん)軽い。  
・Lidarのパラメータを任意に設定できる。測定誤差(ガウスノイズ）を指定可。  
・Odometoryの誤差を設定できる。測定誤差(ガウスノイズ）を指定可。  
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





---


