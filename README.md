## 批量获取圣经经文
### 运行环境
* 本地版(Python3)：
  * 直接运行
    * 将要查找的经文出处输入到 bible_input.txt 中，关闭txt文件
    * 运行 get_passages.py
    * 经文自动生成（写入）到同目录下的 bible_output.txt
  * 作为模块调用
    > from get_passages import get_passages   
    > get_passages("出处") # 不同出处用半角分号“**;**”分隔，如：创1:3-5,6;太2:1         
    > #返回list，结构为: [{"Origin": 原始输入, "BookName": 书卷名, "CV": 章节, "contents": [经文内容:list], "Error": 错误信息},{...}...]

### 符号说明
*   **:**　(冒号)：区分章和节。如：创1:2→创世记1章2节
*   **,**　(逗号)：X章(节) **和** X章(节)。如：创1:2,4→创世记1章第2节，4节(**不包含**第3节)
*   **-**　(连接符)：X章(节) **到** X章(节)。如：创1:2-4→创世记1章第2节到4节(**包含**第3节)

### 输入例
* 例1→　创世记1:2-3,6,9-10
* 例2→　1:30-2:3
* 例3→　3:3
* 例4→　箴言1:32-2:5
* 例5→　诗1,3-4

### 经文出处填法
* 书卷名：简称或全称均可
* **一个出处一行**，同章不同节，可以归纳到一行。如：例1
* 后一个的出处的书卷名如果跟前行一样，可以省略。如：例2，例3
* 跨章查询。如：例4
* 整章查询。同书卷不同章，可以归纳到一行。如：例5

### 注意事项&经文校对志愿者募集
* 使用圣经版本：新标点和合本(神版)。本程序使用的本文里，**标点符号有错误**；文字里，“**像**”经常错为“**象**”，其他文字错误暂时没有发现。
