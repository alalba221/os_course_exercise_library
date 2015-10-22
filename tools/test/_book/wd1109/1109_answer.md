知识点：实验环境准备实验。
出处：网络
难度：1
在汽车行驶过程中,司机活动与售票员活动之间的同步关系为:售票员关车门后, 向司机发开车信号,司机接到开车信号后启动车辆,在汽车正常行驶过程中售票员售
票,到站时司机停车,售票员在车停后开门让乘客上下车。因此,司机启动车辆的动作 必须与售票员关车门的动作取得同步;售票员开车门的动作也必须与司机停车取得同
步。应设置两个信号量:S1 、S2 ;
S1表示是否允许司机启动汽车(其初值为0 )
S2表示是否允许售票员开门(其初值为0 )
    ```
    var S1,S2 : semaphore ;
      S1=0;S2=0;
    cobegin
    Procedure driver             Procedure Conductor
    begin                        begin
     while  TRUE                  while TRUE
     begin                        begin
       P(S1);                       关车门;
       Start;                       V(s1);
       Driving;                     售票;
       Stop;                        P(s2);
       V(S2);                       开车门;
     end                            上下乘客;
    end                           end
    coend
    ```
    