# chestnut
  
## 题目2 低资产客户提升预测

### 术语
- AUM：个人金融资产

### 提供数据
*连续三个月月底时点的*
资产
- 个人定期存款账户信息 IDV_TD
- 个人活期存款账户信息 IDV_DPSA
- 贷款账户信息 LOAN
- 国债账户信息 BOND
- 基金账户信息 FUND
- 贵金属账户信息 PREC_METAl
- 代理保险账户信息 AGET_INSR
- 第三方存管账户信息 THR_PTY_CSTD
客户
- 个人客户基本信息 IDV_CUST_BASIC
交易
- 交易信息 TR_DC
其他
- 汇率表 BASE_EXCG
- 客户标记 CUST_RESULT

### 数据清洗
客户表及客户标记表，count=38256，估计为全部客户数量
交易表count=3390450，据CUST_NO去重后count=36041
各资产表count依次为
	- 个人定期存款账户信息 IDV_TD   3449/30989 
	- 个人活期存款账户信息 IDV_DPSA   38217/262572
	- 贷款账户信息 LOAN   3905/23978
	- 国债账户信息 BOND   231/1510
	- 基金账户信息 FUND   4704/68377
	- 贵金属账户信息 PREC_METAl   3021/10611
	- 代理保险账户信息 AGET_INSR   2532/12045
	- 第三方存管账户信息 THR_PTY_CSTD   6427/28977
具体信息见内网平台上的dataPreview.

### 数据表分类
大致分三类：资产、负债、交易。资产分存款和其他。
- 资产（存款）：对应IDV_TD、IDV_DPSA
- 资产（其他）：BOND、FUND、PREC_METAL、AGET_INSR、THR_PTY_CSTD
- 负债（贷款）：LOAN
- 交易：TR_DC

### 数据清洗和特征提取
目前想到比较简单的思路是，对各个表余额字段分别求和、其他有意义的字段求count（如账户数量/保单数量求count、贵金属品种/险种/基金产品类型求distinct count）。得到一个比较简单的以客户为维度的，每位客户一条的数据。


## Reference
仅作学习整理
### 5th place solution
    @Reference/5th
    Tanzania Challenge移动金融潜在客户预测比赛第五名方案
- [Github链接](https://github.com/galileoSolution/5th-place-solution-Mobile-Money-and-Financial-Inclusion-in-Tanzania-Challenge)
- [How I cracked a Data Science Hackathon](https://medium.com/analytics-vidhya/5th-place-solution-mobile-money-and-financial-inclusion-in-tanzania-challenge-16e43e4d18f8)

### data_process
    @Reference/data_process
    提供数据处理的若干种方法
[Github链接](https://github.com/martin-1992/data_process)

### Rong360
	@Reference/Rong360
	智慧中国杯全国大数据创新应用大赛

[Github链接](https://github.com/hczheng/Rong360)
有两个文件比较大就没上传
- [利用Python进行数据分析.pdf](https://github.com/hczheng/Rong360/blob/master/参考资料/利用Python进行数据分析.pdf)
- 20170119_D.model


### Books:
- [面向机器学习的特征工程](http://fe4ml.apachecn.org/#/)

### Articles：
- [Kaggle入门，看这一篇就够了](https://zhuanlan.zhihu.com/p/25686876?utm_source=wechat_session&utm_medium=social&utm_oi=46841664110592&from=groupmessage&isappinstalled=0)
- [用户贷款风险预测初赛实战总结](https://www.jianshu.com/p/aba5685c580a)
- [一文弄懂AdaBoost、提升树、残差树、GDBT](https://zhuanlan.zhihu.com/p/59751960?utm_source=wechat_session&utm_medium=social&utm_oi=46841664110592&from=groupmessage&isappinstalled=0)
- [【干货】Kaggle实战记录——回归篇之房价预测](https://zhuanlan.zhihu.com/p/69714954?utm_source=wechat_session&utm_medium=social&utm_oi=46841664110592&from=groupmessage&isappinstalled=0)
- [xgboost原理？ -知乎](https://www.zhihu.com/question/58883125/answer/206813653?utm_source=wechat_session&utm_medium=social&utm_oi=46841664110592)
- [干货|横扫Kaggle的XGBoost原理与实战](https://zhuanlan.zhihu.com/p/51682968?utm_source=wechat_session&utm_medium=social&utm_oi=682316278648279040)
- [xgboost原理](Reference/xgboost原理.jpg)





