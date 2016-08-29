# README.md

#百度报告更新

1.获取所有用户的所有的百度账户信息

  + 获取所有账户平台信息
  + 获取 账户对用户名密码token

2.更新账户报告数据

参数－－－  账户信息  账户ID 以及开始时间和结束时间

3.根据设备 不同对  账户account  计划campaign 单元adgroup 关键词keyword 创意  以及  Location 和 Location_L2 表进行入库


performanceData = []string{"cost", "cpc", "click", "impression", "ctr", "cpm","position" ,"conversion"}
startDate 开始时间
endDate  结束时间
idOnly  选填;默认为 false 取值范围: true:只获取 id false:既获取 id 也获取字面
levelOfDetails  统计粒度 
Attributes  选填; 目前仅地域报告和搜索词报告使用了该 字段,若为 NULL 表示统计全部地域。 key:provid ; value:地域代码数组

format 选填,默认值为 2;
reportType  报告类型 必填; 2:账户报告 10:计划报告 11:单元报告 14:关键词报告(keywordid)报告 12:创意报告 15:配对报告 3:地域报告 6:搜索词报告
						 9:关键词报告(wordid) 5:二级地域报告 38:历史数据排名报告
statRange 统计范围
选填,默认值为 2; 2:账户范围
3:计划范围
5:单元范围
7:创意范围 11:关键词(keywordid)范围 6:关键词(wordid)范围
注意:统计范围不能细于当前的统计粒
度,例如统计粒度为计划,则统计范围
不能细到单元


unitOfTime 选填,默认值为 5 取值范围: 5:日报
4:周报
3:月报
1:年报
7:小时报 8:请求时间段汇总(endDate-StartDate)
device 搜索推广设备 选填,默认值为 0 取值范围: 0:全部搜索推广设备 1:仅计算机 2:仅移动
platform  选填,默认为 0 全部:0 内部流量:3 搜索合作流量:4
此字段仅账户、计划、单元、关键词、
创意五种基本类型报告支持

//通用 
UnitOfTime      5(日报)
IdOnly         true 
Format          2
Attributes:      nil,
startDate   > 20010917
endDate
Device 1,0

－－－－－账户报告
reportType       2
levelOfDetails 2
statRange 2
PerformanceData []string{"cost", "cpc", "click", "impression", "ctr", "cpm", "conversion"},
－－－－－计划报告
reportType       10
StatRange = 3 // 2,3
LevelOfDetails = 3
PerformanceData = []string{"cost", "cpc", "click", "impression", "ctr", "cpm", "conversion"}
－－－－－－单元报告
ReportType = 11
StatRange = 5 // 2,3,5
LevelOfDetails = 5
PerformanceData = []string{"cost", "cpc", "click", "impression", "ctr", "cpm", "conversion"}
－－－－－－关键词报告 keywordid
ReportType = 14
StatRange = 11 // 2,3,5,11
LevelOfDetails = 11
PerformanceData = []string{"cost", "cpc", "click", "impression", "ctr", "cpm", "position","conversion"}

－－－－－－创意报告

ReportType = 12
StatRange = 7 // 2,3,5,7
LevelOfDetails = 7
PerformanceData = []string{"cost", "cpc", "click", "impression", "ctr", "cpm", "position","conversion"}

－－－－－－关键词报告（wordid）
ReportType = 9
StatRange = 6 // 2,3,5,11
LevelOfDetails = 6
PerformanceData = []string{"cost", "cpc", "click", "impression", "ctr", "cpm", "position","conversion"}

－－－－－－－地域报告
ReportType = 3
LevelOfDetails = 5 // 2,3,5
StatRange = 5      // 2,3,5
PerformanceData = []string{"cost", "cpc", "click", "impression", "ctr", "cpm", "position","conversion"}

－－－－－－－搜索词报告
ReportType = 6
LevelOfDetails = 3       // 2,3
StatRange = 12 // 7,12  
PerformanceData = []string{"click", "impression"}

－－－－－－－配对报告
ReportType = 15	
StatRange = 11 //2,3,5,7,11
LevelOfDetails = 12
PerformanceData = []string{"cost", "cpc", "click", "impression", "ctr", "cpm"}

－－－－－－－蹊径报告
ReportType = 21
StatRange = 2
LevelOfDetails = 6
PerformanceData = []string{"cost", "cpc", "click", "impression", "ctr"}
－－－－－－二级地市
ReportType = 5
LevelOfDetails = 3
StatRange = 3
PerformanceData = []string{"cost", "cpc", "click", "impression", "ctr", "cpm", "position","conversion"}
－－－－－－历史排名
ReportType = 38
StatRange = 11 // 2,11
LevelOfDetails = 11
PerformanceData = []string{"rank1shows", "rank2shows", "rank3shows", "rank1to3shows", "rank1to3ratio",  "rank1to8shows", "rank1to8ratio","rank4to8shows"}

附注:移动设备不能请求 rank4to8shows 绩效数据


