# 深入理解Java虚拟机 JVM高级特性和最佳实践
## 目录

+ 走进Java
+ Java内存区域与内存溢出异常
+ 垃圾收集与内存分配策略
+ 虚拟机性能监控与故障处理工具
+ 调优案例分析与实战
+ [类文件结构](https://github.com/AcesDream/apebook/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/%E7%AC%AC6%E7%AB%A0%20%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84/1.%E6%A6%82%E8%BF%B0%E5%92%8C%E6%97%A0%E5%85%B3%E6%80%A7%E5%9F%BA%E7%9F%B3.md)
    + 6.1 [概述](https://github.com/AcesDream/apebook/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/%E7%AC%AC6%E7%AB%A0%20%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84/1.%E6%A6%82%E8%BF%B0%E5%92%8C%E6%97%A0%E5%85%B3%E6%80%A7%E5%9F%BA%E7%9F%B3.md)
    + 6.2 [无关性的基石](https://github.com/AcesDream/apebook/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/%E7%AC%AC6%E7%AB%A0%20%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84/1.%E6%A6%82%E8%BF%B0%E5%92%8C%E6%97%A0%E5%85%B3%E6%80%A7%E5%9F%BA%E7%9F%B3.md)
	+ 6.3 [class类文件的结构](https://github.com/AcesDream/apebook/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/%E7%AC%AC6%E7%AB%A0%20%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84/2.%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84.md)
		+ 6.3.1 [魔数与版本号](https://github.com/AcesDream/apebook/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/%E7%AC%AC6%E7%AB%A0%20%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84/3.%E9%AD%94%E6%95%B0%E4%B8%8E%E7%89%88%E6%9C%AC%E5%8F%B7.md)
		+ 6.3.2 [常量池](https://github.com/AcesDream/apebook/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/%E7%AC%AC6%E7%AB%A0%20%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84/4.%E5%B8%B8%E9%87%8F%E6%B1%A0.md)
		+ 6.3.3 [访问标志](https://github.com/AcesDream/apebook/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/%E7%AC%AC6%E7%AB%A0%20%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84/5.%E8%AE%BF%E9%97%AE%E6%A0%87%E8%AF%86%E3%80%81%E7%B1%BB%E7%B4%A2%E5%BC%95%E3%80%81%E7%88%B6%E7%B1%BB%E7%B4%A2%E5%BC%95%E5%92%8C%E6%8E%A5%E5%8F%A3%E7%B4%A2%E5%BC%95%E9%9B%86%E5%90%88.md)
		+ 6.3.4 [类索引、父类索引和接口索引集合](https://github.com/AcesDream/apebook/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/%E7%AC%AC6%E7%AB%A0%20%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84/5.%E8%AE%BF%E9%97%AE%E6%A0%87%E8%AF%86%E3%80%81%E7%B1%BB%E7%B4%A2%E5%BC%95%E3%80%81%E7%88%B6%E7%B1%BB%E7%B4%A2%E5%BC%95%E5%92%8C%E6%8E%A5%E5%8F%A3%E7%B4%A2%E5%BC%95%E9%9B%86%E5%90%88.md)
		+ 6.3.5 [字段表集合](https://github.com/AcesDream/apebook/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/%E7%AC%AC6%E7%AB%A0%20%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84/6.%E5%AD%97%E6%AE%B5%E8%A1%A8%E9%9B%86%E5%90%88%E5%92%8C%E6%96%B9%E6%B3%95%E8%A1%A8%E9%9B%86%E5%90%88.md)
		+ 6.3.6 [方法表集合](https://github.com/AcesDream/apebook/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/%E7%AC%AC6%E7%AB%A0%20%E7%B1%BB%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84/6.%E5%AD%97%E6%AE%B5%E8%A1%A8%E9%9B%86%E5%90%88%E5%92%8C%E6%96%B9%E6%B3%95%E8%A1%A8%E9%9B%86%E5%90%88.md)
		+ 6.3.7 [属性表集合]
