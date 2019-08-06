# DM

## Task_1

数据切分方式 - 三七分，其中测试集30%，训练集70%，随机种子设置为2018

- 数据类型的分析

- 无关特征删除

- 数据类型转换

- 缺失值处理

### 数据类型分析

读取数据文件之后data.info()查看数据集的数据类型分布及特征。

初始数据中有float、int、object三种数据类型。

这意味着需转换或删除object类型的特性才能进行下一步的操作。

### 无关特征删除

对唯一特征删除：删除数据集中Unamed:0、custid、trade_no、bank_card_no、id_name、source reg_preference_for_trad、latest_query_time、loans_latest_time

（PS：这里看了其他人的处理方法，大都保留了reg_preference_for_trad这个特征。包括很多保留了latest_query_time、loans_latest_time。对于如何取舍特征值，特征值对于数据分析的重要性还不太理解。）

删除存在大量缺失值的特征：student_feature

在删除完无关特征之后data.info可以看到所有的object类型特征已被删除。

对无效行进行删除：缺失超过百分之三十的行被删除。

### 缺失值处理

使用平均值填充。data = data.fillna(data.mean())。

（PS：平均值填充、中位数填充等缺失值填充的方法区别在哪里？分别对应什么场景？对于一些特征，如时间、地区等应该怎样填充？）

