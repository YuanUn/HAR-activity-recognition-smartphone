Human Activity Recognition implementation instructions:

The acc-gyro folder contains the program to collect data. Data in this repository is collected by using the left hand to hold a cell phone and the sampling frequency is 50Hz. AtimeSs is the accelerometer data collector timestamp, and GtimeSs is the gyroscope data collector timestamp. Gender variable: 0 is Female and 1 is Male.

The algorithm is in code.ipynb. hhyHAR_6data.csv is the training dataset consisting of 4 activities: label 0 is jumping jacks, 1 is deep squat, 2 is 合掌跳 (closed palm jump) and 3 is high leg raise. The number of this data is comparatively small and the label distribution is imbalanced. Using LSTM, CNN, MLP, Random Forest, and Naive Bayes can achieve good classification performance. 

We use JavaScript to rewrite the MLP algorithms in the .js file to allow off-line real-time classification.





HAR实现系统说明文档(2020)：

acc-gyro文件夹是采集数据的小程序，为左手持手机，采样频率50Hz。AtimeSs是加速计采集数据时间戳，GtimeSs是陀螺仪采集数据时间戳。gender：女 0  男 1。

算法代码code.ipynb。hhyHAR_6data.csv是四种动作数据转换格式后整合成的训练集。其中动作标签：开合跳0，深蹲1，合掌跳2，高抬腿3。通过LSTM、CNN、MLP、随机森林、朴素贝叶斯等均可以实现较好分类效果。由于个人采集数据量较小且动作之间数据量不平衡，实时监测准确率稍有下降，但扩充数据集重新导入参数即可大幅度改良。

测试小程序文件夹是MLP算法JavaScript重写部署到小程序上后的测试小程序，可以离线识别，但语音播报需要联网接通云存储音频文件且有延迟。用电脑真机调试可以看console.log里的每秒识别信息、整体识别信息和每个动作的计数，需要保证网络正常否则真机调试传输传感器数据会堵塞导致无法进行整体识别、每秒采样受影响识别效果差。由于小程序内部计算量大，采样频率受到影响，但大体监测仍准确。若改用连接服务器则使用LSTM、CNN算法识别效果会更好。

