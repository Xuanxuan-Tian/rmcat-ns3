# rmcat-ns3
A comparison of rmcat protocol, namely NADA, GCC and SCReAM on ns3 platform. The version of ns is 3.26.   
The paper link https://arxiv.org/pdf/1809.00304.pdf   
The simulation code of NADA can get from https://github.com/cisco/ns3-rmcat  
In consideration that the author of NADA made an update to their code, I upload the code I used during writting of this paper. And I did test the performance of the newer code inplementation, but it seems the new version had introduce some bugs that the sender can get quite low throughput compared to the link capacity.  
For, I just release the SCReAM code modified from https://github.com/EricssonResearch/scream  

the code in screamex.cc sendApp->SetTraceFilePath("/you_path/trace_key.txt"),is no use in experiment, but it should be configured in right path. trace_key.txt is from https://github.com/EricssonResearch/scream/tree/master/traces  

the mytrace module is used for data collecion. And a file named "trace" should be created first under the  path of ns-allinone-3.26/ns-3.26/  

the razor project is a c version of GCC release at https://github.com/yuanrongxi/razor. And I make some minor modification to get it running on ns3.  

In simulation(razor-example/gcc_tcp.cc), a point to point channel was created. From the time of 20s to 100s, A reno TCP connection flows into the network. The first picture shows the kalman-gcc cannot complete fair bandiwdth share with tcp flow.  

![image](https://github.com/sonyangchang/rmcat-ns3/blob/master/razor-example/gcc_razor_0remb.png)
![image](https://github.com/sonyangchang/rmcat-ns3/blob/master/razor-example/gcc_razor_1remb.png)  

Its the success importation of razor project on ns3 encourages me to get the original GCC in webrtc running on ns3.  
To compile the webrtc code, first compile libevent, read the instruction under home-zsy-webrtc-ns3/webrtc/base/libevent.  
And  cmake .  under of home-zsy-webrtc-ns3/webrtc/ to get the dynamic library.  
If you quite interesting the code, and think the above instrcution is quite complex, you could email me for the VM during the experiment.  

