# 本次实验

本文使用广东政府的公交开源数据进行客流预测模型的训练和调优。首先清洗重复数据和错误数据，并对天气、时间等非客流量数据进行分级编码。并为了模型的鲁棒性将数据映射为标准正态分布，使用z-score标准化。接着训练多个不同角度的模型：考虑不同人群的出现需求，不同天气的出行需求，节假日与工作日的出行需求等训练不同的预测模型，用基于boosting的GBDT算法进行训练与融合，最终客流预测准确率达到97.3%，最后基于第一问提出的评价指标，将客流预测用于高峰平峰预测。

# 原博客目录说明

## source:
* CheckTrainData.py：查看原始数据
* DealTrainData.py：处理交易数据
* DealWeatherData.py：处理天气数据
* error.py：误差函数
* ExploreTrainData.py：交易数据探索绘图
* ExploreTrainWeather.py：交易数据关联天气数据探索绘图
* predict.py：预测20141225-20141231的客流
* TestDataResult.py：测试集生成
* TrainDataResult.py：训练集生成
* TrainModel.py：训练模型

## data:
由于大赛已经结束，咱们就把20141225-20141231的交易数据拿出来当作未知

* date_holiday.txt：日期节假日、工作日数据
* gd_line_desc.txt：比赛提供的公交线路信息数据
* gd_train_data.txt：比赛提供的原始交易数据
* gd_weather_report.txt：比赛提供的天气状况
* line6_passenger_hour_test.csv：20141225-20141231线路6的客流
* line11_passenger_hour_test.csv：20141225-20141231线路11的客流
* train_data.csv：去掉20141225-20141231的交易数据
* train_data_test.csv：20141225-20141231的交易数据，作为测试集

由于github对单个文件大小有限制，我把数据上传到了百度云盘
链接：https://pan.baidu.com/s/1vRsr_ur7fgtSz7GHzlALSw 密码：x1r4

## model:
存放训练好的模型

具体细节移步https://blog.csdn.net/u010606321/article/details/82501341
