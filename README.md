# SM3长度扩展攻击实验
## 基本实验思路：
1.对于给定的原始数据（待攻击数据），随机选择一段追加数据<br>
2.使用SM3原有的IV对原始数据进行hash，得到原始数据的hash值<br>
3.将原始数据的hash值分成八段，作为长度扩展攻击中的新IV<br>
4.按照填充规则将追加数据进行填充，然后将最后的64位数据长度修改为“原始数据+原始数据填充+追加数据”的总长度<br>
5.将第4步中得到的数据使用第3步中得到的新IV进行SM3-hash，即可得到长度扩展攻击结果<br>
6.若第5步中得到的结果与将“原始数据+原始数据填充+追加数据”进行SM3-hash得到的结果相同，则攻击成功<br>
## 实验结果展示：
![](https://github.com/dry9rape/SM3_lenth_expand_attack/raw/main/SM3长度扩展攻击结果.png) 
