

# 2016年全国研究生移动终端应用设计创新大赛

#[派送助手]设计文档

## 1.1选题背景

国家邮政局发布了2015年邮政行业发展统计公报，数据显示2015年全年业务总量突破5000亿元，业务收入突破4000亿元，快递业务量突破200亿件。

电商的蓬勃发展使得目前很大一部分的物流包裹均来源于线上电商订单。在中国，该比例超过了60%。这些包裹在配送的最后环节，是由快递员将包裹从网点送到消费者手中。另一方面，随着互联网逐渐向线下渗透，涌现出了越来越多的同城包裹配送需求，如外卖订单或鲜花蛋糕等等同城订单。这两类包裹的配送是目前中国最后一公里配送中最典型的场景。

 通过对十个快递员进行访问，发现快递员在派送过程中遇到如下难题。

 高峰期时，快递员一天平均派送100多快件，工作时间超13小时。快递员的一天始于分拣快递，分拣是最重要的一步。快递员分拣出自己需要派送的快件，将快件按区域进行简单分类。在派送的过程中，快递员通常按照自己的喜好选择快件进行先后派送。由于需要派送的快件过多，快递员通常会因为疏忽而导致错派，漏派，降低派送效率。并且快递员通常所走路线的总路程和最优规划路线的总路程差距很大。快递员遇到不熟悉地点时，需要查看地图或者问路人，因此导致派送时间增加。快递员到达目的地楼下后再拨打客户电话通知取件，需要等待客户来取件，等待的平均时间超过5分钟。

本项目基于以上实际情况，开发出一款Android App——&quot;派送助手&quot;。本APP集合快件管理，路线规划，一键导航和智能呼叫功能，能够帮助快递员提高派送效率。首先将快件的地址和电话信息添加到&quot;派送助手&quot;，点击&quot;开始派送&quot;。后台算法将会计算最优路线，确定快件的派送次序，快递员依照提示依次派送。快递员遇到不熟悉路线时，点击&quot;导航&quot;可以获取当前位置到目的地的导航路线。当快递员将要到达目的地时，手机会智能识别并提前拨叫用户。节省快递员等待客户取件的时间。

 本项目基于Android平台，结合百度地图SDK，利用腾讯云服务器作为后台服务器。通过优化快件信息输入方式，快速添加快件信息。本项目基于快递员实际派送场景，解决了快递员在派送过程中的难题，提高快递员的派送效率。

## 1.2项目意义

 根据从业者报告的数据，截至2016年初，全国社会化电商物流从业人员达到203.3万人。此前《快递服务&quot;十二五&quot;规划》显示，截至2010年快递从业人员达到60万以上，5年间从业人员上涨约3.4倍。在203万人中，一线人员，主要包括站点快递员、站点仓库操作人员、基层管理人员，共163.6万人。其中快递员占98万人。据统计，包括快递员在内的站点工作人员中，有五成人员的工资水平在2001至6000元，少数能达到7000元以上。报告称，站点从业者每天平均工作时长主要集中在8至12小时，电商促销旺季甚至日工作时长超过13小时。快递员行业存在劳动强度大，工作辛苦，工资不高，不被尊重等现象。本项目可以帮助庞大的快递员行业提升派送效率。

本项目基于快递员实际派送情况，致力于解决派送过程中的问题，提高派送效率，增加快递员的收入，减轻工作负担。提高派送效率的同时也缩短了快件到达客户手中的时间，提升了网购，O2O服务的用户体验。本项目在实际生活中具有应用价值。

# 二、可行性分析和目标群体

## 2.1        可行性分析

快递员在实际派送过程中存在以下问题：通过在分拣时查看快递单来大概获知今天要走的路线，没有进行合理的路线规划，这会使派送时间增加；由于快件过多，快递员不知道先送哪个后送哪个；同一地点有多个快件时容易漏送，折返浪费时间；遇到不熟悉地址时，不知怎么走；到达后通知客户取件，等待客户时间长；这些问题都制约着快递员的派送效率。

本项目的解决方案：使用路径规划算法解决路线规划问题，缩短派送总路程；快递员按照App规划的派送顺序依次派送快件，因此派送不盲目；同一地点有多个快件时会提醒快递员，避免漏派；一键导航功能提供从当前位置到下一地点的导航路线；APP实时计算快递员与下一地点的距离，当距离小于一定距离时，APP自动拨打客户电话，提前通知客户取件，这样可以缩短等待用户取件时间。同时本项使用百度地图SDK提供的&quot;建议搜索地址&quot;功能实现快速录入地址电话信息到&quot;派送助手&quot;App。由于快递员一般负责一片区域的快递派送，经常会给老客户派送快递，本APP将会记录历史派送数据，当添加历史派送数据时，只需要添加电话，地址栏将自动被填充，这样可以缩短添加信息的时间。

通过本项目提供的解决方案可以很好解决快递员在实际派送过程中的问题，本项目符合快递员用户的需求，在实际应用中具有使用价值；

## 2.2 本项目的实现

本项目Android App 基于Android Studio进行开发，Android Studio 是一个Android开发环境，基于IntelliJ IDEA. 类似 Eclipse ADT，Android Studio 提供了集成的 Android 开发工具用于开发和调试。

本项目调用了百度地图Geocoding API，百度地图Geocoding API是为开发者免费提供的一套基于百度地图服务的应用接口，提供基本地图展现、搜索、定位、逆/地理编码、路线规划、LBS云存储与检索等功能。 Geocoding API 是一类简单的HTTP接口，用于提供从地址到经纬度坐标或者从经纬度坐标到地址的转换服务，用户可以使用C# 、C++、Java等开发语言发送HTTP请求且接收JSON、XML的返回数据。

Geocoding API包括地址解析和逆地址解析功能：

地理编码：即地址解析，由详细到街道的结构化地址得到百度经纬度信息，例如：&quot;北京市海淀区中关村南大街27号&quot;地址解析的结果是&quot;lng:116.31985,lat:39.959836&quot;。同时，地理编码也支持名胜古迹、标志性建筑名称直接解析返回百度经纬度，例如：&quot;百度大厦&quot;地址解析的结果是&quot;lng:116.30815,lat:40.056885&quot; ，通用的POI检索需求，建议使用Place API。

逆地理编码：即逆地址解析，由百度经纬度信息得到结构化地址信息，例如：&quot;lat:31.325152,lng:120.558957&quot;逆地址解析的结果是&quot;江苏省苏州市虎丘区塔园路318号&quot;。

通过百度地图API的路线规划功能，计算快件地址两两之间的实际距离，为路径规划算法做准备。通过使用百度地图API的定位功能实时确定快递员的位置的经纬度。通过调用百度地图API的导航功能实现从快递员当前位置到下一目的地的一键导航。

 本项目的路径规划算法实现：本项目的路径规划问题是典型的VRP（Vehicle Routing Problem）问题，通过对问题进行数学建模，决策函数是快递员总体派送路程最短，然后利用遗传算法求最优解。

算法具体的实施步骤如下：

S1、初始化，产生初始种群；

S2、个体评价，即计算种群中每个个体的适应度，并判断是否符合优化准则。若符合，则输出最佳个体及其代表的最优解或最满意解，停止，否则转S3;

S3、按照选择概率 ![](./) ![](data:image/*;base64,VkNMTVRGAQAxAAAAAAAAAAEAGwAAAAAAAAAAAAAAAAABAAAAAQAAAAEAAAABAAAAARkBAABzAQAADQAAAJYAAQACAAAACQCKAAEAQQAAAAMAOwAAAA8AVGltZXMgTmV3IFJvbWFuAACMAAAAkAAAAP//AAACAAUAAAAAAAIACQQAAAAAAAAAAAD/AwAAAAAAiAABAAIAAAABAIcAAQAFAAAA/////wCGAAEABAAAAAAAAABxAAIAHgAAALwAAAA3AQAAAQAAAHMAAAABAAEAAAD+AAAAAQBzAAACAQATAAAACQBYVEVYVF9FT0MAAAAAAAAAAIoAAQBBAAAAAwA7AAAADwBUaW1lcyBOZXcgUm9tYW4AAPAAAAD3AAAA//8AAAIABQAAAAAAAgAJBAAAAAAAAAAAAP8DAAAAAACIAAEAAgAAAAEAhwABAAUAAAD/////AIYAAQAEAAAAAAAAAHEAAgAeAAAAQgAAAPcAAAABAAAAcAAAAAEAAQAAALMBAAABAHAAAAIBABMAAAAJAFhURVhUX0VPQwAAAAAAAAAA)，执行选择算子，从当前种群中选择部分个体进入下一代种群；

S4、按照交叉概率 ![](./) ![](data:image/*;base64,VkNMTVRGAQAxAAAAAAAAAAEAGwAAAAAAAAAAAAAAAAABAAAAAQAAAAEAAAABAAAAAS0BAABzAQAADQAAAJYAAQACAAAACQCKAAEAQQAAAAMAOwAAAA8AVGltZXMgTmV3IFJvbWFuAACMAAAAkAAAAP//AAACAAUAAAAAAAIACQQAAAAAAAAAAAD/AwAAAAAAiAABAAIAAAABAIcAAQAFAAAA/////wCGAAEABAAAAAAAAABxAAIAHgAAALgAAAA3AQAAAQAAAGMAAAABAAEAAAD+AAAAAQBjAAACAQATAAAACQBYVEVYVF9FT0MAAAAAAAAAAIoAAQBBAAAAAwA7AAAADwBUaW1lcyBOZXcgUm9tYW4AAPAAAAD3AAAA//8AAAIABQAAAAAAAgAJBAAAAAAAAAAAAP8DAAAAAACIAAEAAgAAAAEAhwABAAUAAAD/////AIYAAQAEAAAAAAAAAHEAAgAeAAAAQgAAAPcAAAABAAAAcAAAAAEAAQAAALQBAAABAHAAAAIBABMAAAAJAFhURVhUX0VPQwAAAAAAAAAA)，执行交叉算子；

S5、按照变异概率 ![](./) ![](data:image/*;base64,VkNMTVRGAQAxAAAAAAAAAAEAGwAAAAAAAAAAAAAAAAABAAAAAQAAAAEAAAABAAAAAV8BAABzAQAADQAAAJYAAQACAAAACQCKAAEAQQAAAAMAOwAAAA8AVGltZXMgTmV3IFJvbWFuAAAAAAAAkAAAAP//AAACAAUAAAAAAAIACQQAAAAAAAAAAAD/AwAAAAAAiAABAAIAAAABAIcAAQAFAAAA/////wCGAAEABAAAAAAAAABxAAIAHgAAAL8AAAA3AQAAAQAAAG0AAAABAAEAAAAFAQAAAQBtAAACAQATAAAACQBYVEVYVF9FT0MAAAAAAAAAAIoAAQBBAAAAAwA7AAAADwBUaW1lcyBOZXcgUm9tYW4AAAAAAAD3AAAA//8AAAIABQAAAAAAAgAJBAAAAAAAAAAAAP8DAAAAAACIAAEAAgAAAAEAhwABAAUAAAD/////AIYAAQAEAAAAAAAAAHEAAgAeAAAARAAAAPcAAAABAAAAcAAAAAEAAQAAAMABAAABAHAAAAIBABMAAAAJAFhURVhUX0VPQwAAAAAAAAAA)，执行变异算子；

S6、由交叉和变异产生新一代的种群，转S2;

**实验结果**

| 实验名称 | 随机路线总路程 | 规划后总路程 | 优化比例 |
| --- | --- | --- | --- |
| 实验1 | 10.3km | 8.7km | 16% |
| 实验2 | 23.4km | 18.9km | 19% |
| 实验3 | 40.6km | 31.4km | 23% |
| 实验4 | 80.5km | 61.3km | 24% |

 目前算法对于上百个点的规划不是问题，满足快递员一次派送的需求。通过算法规划的最优路线跟随机选取的路线进行比较，路径规划算法能缩短20%左右的路程。
 通过以上分析，本项目具有可行性。本项目已经完成了前面提到的所有功能，能够进行实际应用。

## 2.2        目标群体

 本项目——&quot;派送助手&quot;App主要的使用群体为快递员行业，通过背景分析、项目意义和可行性分析可知&quot;派送助手&quot;满足快递员的迫切需求，能够提高快递员的派送效率，对快递员来说具有使用价值。

 对于兴起的O2O服务，特别是外卖配送，也有使用价值。由于外卖派送时间比较集中，外卖员需要在饭点尽快将外卖送往客户手中，同时也要求能尽量多的派送，外卖派送员同样有和快递员一样的问题，所以，本项目的目标群体中也有O2O服务提供商。

# 三、作品功能和原型设计

## 3.1        总体功能结构

总体功能结构框图如下所示：

## 3.2        具体功能模块设计

 主页功能设计：主界面采用简洁化设计，顶端中间为应用名称，右边为添加按钮，点击后可选择添加方式，现在只支持手动添加，系统添加作为测试用。地端为开始派送按钮。中间为快件信息，每条信息包括电话和地址。

 手动添加功能设计：在手动添加界面要求输入电话和地址，输入好后点击顶端右边确认按钮。如需取消，点击顶端左边返回按钮。地址输入框采用百度地图建议搜索地址功能，输入大概地址信息，下列列表将会显示具体地址选项，点击正确选项便可完成添加，同时采用百度地图实时显示添加地址的地图信息。这样可以帮助用户快速完成添加。

 派送指导功能设计：派送界面顶端显示的是当前位置距离下一个派送地点之间的实时距离。底端分别为导航按钮和下一地点按钮。点击导航按钮，将可以获得从当前位置到下一地点的导航。点击下一地点按钮，表示完成派送当前快件，进行派送下一个快件；界面中间显示的是按规划路线依次显示相应快件的地址信息。

## 3.3        界面设计

### 3.3.1 主页界面

### 3.3.2 手动添加界面

### 3.3.3 加载界面

### 3.3.4 开始派送界面

### 3.3.5 导航界面

# 四、作品实现、特色和难点

## 4.1        作品实现

 本项目Android App 基于Android Studio进行开发，Android Studio 是一个Android开发环境，基于IntelliJ IDEA. 类似 Eclipse ADT，Android Studio 提供了集成的 Android 开发工具用于开发和调试。

本项目调用了百度地图API，百度地图API是为开发者免费提供的一套基于百度地图服务的应用接口，提供基本地图展现、搜索、定位、逆/地理编码、路线规划、LBS云存储与检索等功能。 Geocoding API 是一类简单的HTTP接口，用于提供从地址到经纬度坐标或者从经纬度坐标到地址的转换服务，用户可以使用C# 、C++、Java等开发语言发送HTTP请求且接收JSON、XML的返回数据。

Geocoding API包括地址解析和逆地址解析功能：

地理编码：即地址解析，由详细到街道的结构化地址得到百度经纬度信息，例如：&quot;北京市海淀区中关村南大街27号&quot;地址解析的结果是&quot;lng:116.31985,lat:39.959836&quot;。同时，地理编码也支持名胜古迹、标志性建筑名称直接解析返回百度经纬度，例如：&quot;百度大厦&quot;地址解析的结果是&quot;lng:116.30815,lat:40.056885&quot; ，通用的POI检索需求，建议使用Place API。

逆地理编码：即逆地址解析，由百度经纬度信息得到结构化地址信息，例如：&quot;lat:31.325152,lng:120.558957&quot;逆地址解析的结果是&quot;江苏省苏州市虎丘区塔园路318号&quot;。

通过百度地图API的路线规划功能，计算快件地址两两之间的实际距离，为路径规划算法做准备。通过使用百度地图API的定位功能实时确定快递员的位置的经纬度。通过调用百度地图API的导航功能实现从快递员当前位置到下一目的地的一键导航。

 本项目的路径规划算法实现：本项目的路径规划问题是典型的VRP（Vehicle Routing Problem）问题，通过对问题进行数学建模，决策函数是快递员总体派送路程最短，然后利用遗传算法求最优解。

算法具体的实施步骤如下：

S1、初始化，产生初始种群；

S2、个体评价，即计算种群中每个个体的适应度，并判断是否符合优化准则。若符合，则输出最佳个体及其代表的最优解或最满意解，停止，否则转S3;

S3、按照选择概率 ![](./) ![](data:image/*;base64,VkNMTVRGAQAxAAAAAAAAAAEAGwAAAAAAAAAAAAAAAAABAAAAAQAAAAEAAAABAAAAARkBAABzAQAADQAAAJYAAQACAAAACQCKAAEAQQAAAAMAOwAAAA8AVGltZXMgTmV3IFJvbWFuAACMAAAAkAAAAP//AAACAAUAAAAAAAIACQQAAAAAAAAAAAD/AwAAAAAAiAABAAIAAAABAIcAAQAFAAAA/////wCGAAEABAAAAAAAAABxAAIAHgAAALwAAAA3AQAAAQAAAHMAAAABAAEAAAD+AAAAAQBzAAACAQATAAAACQBYVEVYVF9FT0MAAAAAAAAAAIoAAQBBAAAAAwA7AAAADwBUaW1lcyBOZXcgUm9tYW4AAPAAAAD3AAAA//8AAAIABQAAAAAAAgAJBAAAAAAAAAAAAP8DAAAAAACIAAEAAgAAAAEAhwABAAUAAAD/////AIYAAQAEAAAAAAAAAHEAAgAeAAAAQgAAAPcAAAABAAAAcAAAAAEAAQAAALMBAAABAHAAAAIBABMAAAAJAFhURVhUX0VPQwAAAAAAAAAA)，执行选择算子，从当前种群中选择部分个体进入下一代种群；

S4、按照交叉概率 ![](./) ![](data:image/*;base64,VkNMTVRGAQAxAAAAAAAAAAEAGwAAAAAAAAAAAAAAAAABAAAAAQAAAAEAAAABAAAAAS0BAABzAQAADQAAAJYAAQACAAAACQCKAAEAQQAAAAMAOwAAAA8AVGltZXMgTmV3IFJvbWFuAACMAAAAkAAAAP//AAACAAUAAAAAAAIACQQAAAAAAAAAAAD/AwAAAAAAiAABAAIAAAABAIcAAQAFAAAA/////wCGAAEABAAAAAAAAABxAAIAHgAAALgAAAA3AQAAAQAAAGMAAAABAAEAAAD+AAAAAQBjAAACAQATAAAACQBYVEVYVF9FT0MAAAAAAAAAAIoAAQBBAAAAAwA7AAAADwBUaW1lcyBOZXcgUm9tYW4AAPAAAAD3AAAA//8AAAIABQAAAAAAAgAJBAAAAAAAAAAAAP8DAAAAAACIAAEAAgAAAAEAhwABAAUAAAD/////AIYAAQAEAAAAAAAAAHEAAgAeAAAAQgAAAPcAAAABAAAAcAAAAAEAAQAAALQBAAABAHAAAAIBABMAAAAJAFhURVhUX0VPQwAAAAAAAAAA)，执行交叉算子；

S5、按照变异概率 ![](./) ![](data:image/*;base64,VkNMTVRGAQAxAAAAAAAAAAEAGwAAAAAAAAAAAAAAAAABAAAAAQAAAAEAAAABAAAAAV8BAABzAQAADQAAAJYAAQACAAAACQCKAAEAQQAAAAMAOwAAAA8AVGltZXMgTmV3IFJvbWFuAAAAAAAAkAAAAP//AAACAAUAAAAAAAIACQQAAAAAAAAAAAD/AwAAAAAAiAABAAIAAAABAIcAAQAFAAAA/////wCGAAEABAAAAAAAAABxAAIAHgAAAL8AAAA3AQAAAQAAAG0AAAABAAEAAAAFAQAAAQBtAAACAQATAAAACQBYVEVYVF9FT0MAAAAAAAAAAIoAAQBBAAAAAwA7AAAADwBUaW1lcyBOZXcgUm9tYW4AAAAAAAD3AAAA//8AAAIABQAAAAAAAgAJBAAAAAAAAAAAAP8DAAAAAACIAAEAAgAAAAEAhwABAAUAAAD/////AIYAAQAEAAAAAAAAAHEAAgAeAAAARAAAAPcAAAABAAAAcAAAAAEAAQAAAMABAAABAHAAAAIBABMAAAAJAFhURVhUX0VPQwAAAAAAAAAA)，执行变异算子；

S6、由交叉和变异产生新一代的种群，转S2;

实验结果：

| 实验名称 | 随机路线总路程 | 规划后总路程 | 优化比例 |
| --- | --- | --- | --- |
| 实验1 | 10.3km | 8.7km | 16% |
| 实验2 | 23.4km | 18.9km | 19% |
| 实验3 | 40.6km | 31.4km | 23% |
| 实验4 | 80.5km | 61.3km | 24% |

 目前算法对于上百个点的规划不是问题，满足快递员一次派送的需求。通过算法规划的最优路线跟随机选取的路线进行比较，路径规划算法能缩短20%左右的路程。

 本项目后台服务器：后台服务器采用了腾讯云服务器，腾讯云有着深厚的基础架构，并且有着多年对海量互联网服务的经验，不管是社交、游戏还是其他领域，都有多年的成熟产品来提供产品服务。腾讯在云端完成重要部署，为开发者及企业提供云服务、云数据、云运营等整体一站式服务方案。

## 4.2        特色分析

 本项目对快递员进行采访，通过采访了解快递员的日常，知道了快递派送中存在如下问题：

 快递员分拣出自己需要派送的快件，将快件按区域进行简单分类。在派送的过程中，快递员通常按照自己的喜好选择快件进行先后派送。由于需要派送的快件过多，快递员通常会因为疏忽而导致错派，漏派，降低派送效率。并且快递员通常所走路线的总路程和最优规划路线的总路程差距很大。快递员遇到不熟悉地点时，需要查看地图或者问路人，因此导致派送时间增加。快递员到达目的地楼下后再拨打客户电话通知取件，需要等待客户来取件，等待的平均时间超过5分钟。

## 本项目特色如下：

 1、优化路径规划算法。本项目通过对派送路径问题进行分析、研究和建模，通过利用改进遗传算法进行路径规划，使派送总路程缩短，减少了派送时间。

 2、获取行驶路线和时间。本项目通过调用百度地图API，实现地理编码，得到两两地点之间的实际行驶路线距离和行驶时间，为路径规划算法做好准备。

3、智能呼号。本项目通过调用百度地图API定位功能，实现实时定位快递员位置。通过API实现计算快递员与目的地之间的距离，当距离小于指定距离时，手机将自动拨打用户电话，提前通知用户取件。

4、本APP调用了百度地图API，为本项目提供经纬度计算、定位、导航服务、两地点之间的路线规划等功能，保证了本项目的基础功能实现，同时为客户添加了其他丰富的服务。

本APP的后台采用了腾讯云服务器，可以轻松购买自定义配置的机型，在几分钟内获取到新服务器，并根据需要使用镜像进行快速的扩容。跟本地服务器相比，云服务器具有成本低、安全性高、免维护、可定制的优势。

## 4.3        难点和解决方案

 **难点1：**地点之间距离无法得知，GPS定位不精确

 **解决方案：**通过注册成为百度地图开发者，申请调用百度地图API，学习使用API提供的路线规划功能，此功能可以帮用户规划好两个地点之间的最佳路线，提供距离信息。使用百度地图定位SDK进行定位，借助GPS、基站、Wi-Fi和传感器信息，实现高精度的综合网络定位服务，成功率高达99.5%。同时可以给用户提供导航功能。

**难点2：**路径规划问题

 **解决方案：**首先调用百度地图API，将地点的地址信息转化成经纬度信息。然后调用百度地图API的驾车路线规划功能，计算出两两地点之间的距离和路线。然后通过对问题进行数学建模，使用遗传算法得到最优结果。

 **难点3：**进行路径规划计算需要提供大量计算能力和硬件资源，手机客户端不能快速完成计算。
 **解决方案：**将路线规划计算部署到腾讯云服务器，可以快速完成计算，手机客户端通过socket跟服务器进行通信，将地点之间的距离信息传给服务器，服务器计算后返回给客户端，从而实现快速完成路线规划。
