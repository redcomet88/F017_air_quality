# F017 vue+flask全国空气质量大数据系统、带大屏+管理端+爬虫

> 完整项目收费，可联系QQ: 81040295 微信: mmdsj186011 注明从git来的，谢谢！
也可以关注我的B站： 麦麦大数据 https://space.bilibili.com/1583208775
> 
up主B站账号： **麦麦大数据**
关注B站，有好处！
编号:  F017
## 视频

[video(video-2gpxRePV-1758067963143)(type-bilibili)(url-https://player.bilibili.com/player.html?aid=113461577125230)(image-https://i-blog.csdnimg.cn/img_convert/0610415c718be8a284ffb1c6684597f1.jpeg)(title-vue+flask实时vue+flask全国空气质量大数据系统、带大屏+管理端+爬虫)]

## 1 系统简介
系统简介：本系统是一个基于Vue+Flask构建的空气质量大数据可视化与管理平台，核心功能聚焦于空气质量数据的采集、展示、分析和用户管理。系统通过爬取阿里云市场的实时空气质量数据，并进行清洗与存储，为用户提供全面的空气质量监测服务。主要模块包括：数据大屏可视化，通过动态图表和地图展示空气质量指数（AQI）、污染物浓度（如PM2.5、PM10、SO2等）的实时和历史趋势，支持多维度筛选和交互式分析；管理端模块，允许管理员管理空气质量数据（如数据导入、更新和删除）和用户信息（包括用户注册、登录、权限设置和个人资料修改），确保数据安全性和系统可维护性。系统旨在帮助用户直观了解空气质量状况，并为决策提供数据支持。
## 2 功能设计
该系统采用B/S（浏览器/服务器）架构。用户通过浏览器访问Vue前端界面，该前端使用HTML、CSS、JavaScript以及Vue.js框架（包括Vuex用于状态管理、Vue Router用于路由导航）和Echarts等可视化库构建，以实现响应式数据大屏和交互式图表。前端通过RESTful API与Flask后端进行数据交互，Flask后端负责业务逻辑处理、数据预测（如基于历史数据的简单趋势分析）和用户认证，并使用SQLAlchemy（或类似ORM工具）与MySQL数据库进行持久化数据存储。此外，系统包含一个独立的爬虫模块，专门从阿里云市场API抓取空气质量数据，经过数据清洗后导入MySQL数据库，为可视化和管理功能提供数据基础。整体设计确保了系统的可扩展性、数据实时性和用户友好性。
### 2.1系统架构图
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/39c8cc9b45a7499daecf3a50f5f4d16d.png)
### 2.2 功能模块图
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/70a1ed4da6ff4b01801c5a0ad693596a.png)
## 3 功能展示
### 3.1 前台： 数据大屏
空气质量数据大屏具备了多种实用的分析功能。首先，通过**地图展示了全国各地的空气质量状况**，使用**颜色深浅**直观地反映了各地区的污染程度，这有助于用户快速识别空气质量较差的城市。此外，还提供了**PM2.5的排名**、**主要污染物比例**以及历史空气质量变化趋势等信息，使得用户能够全面了解当前的空气质量状况及其变化趋势。这种数据的可视化展示，不仅增强了用户的理解能力，还能够引导公众关注空气污染问题。
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/47a9fef4641a4d27b4c88f51dc567cf4.png)


---
### 3.2  后台系统：登录 & 注册
登录注册做的是一个可以切换的登录注册界面，点击去登录后者去注册可以切换，背景是一个视频，循环播放。
登录需要验证用户名和密码是否正确，如果**不正确会有错误提示**。
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/8529f9af4ae3493aa69ef61c2083183b.png)
注册需要**验证用户名是否存在**，如果错误会有提示。
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/f270465a41c0420faa41815551d4ef0e.png)
### 3.2 后台系统：空气质量管理
主页的布局采用了左侧是菜单，右侧是操作面板的布局方法，右侧的上方还有用户的头像和退出按钮，如果是新注册用户，没有头像，这边则不显示，需要在个人设置中上传了头像之后就会显示。
空气质量管理部分可以管理从爬虫爬取的质量数据。
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/91d68f23667c4ee48022f2048e50cf6c.png)
支持通过输入关键词查询特定城市的空气质量的状况：
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/91b491b797ad4a658876f8c010ab968e.png)
也可以在后台新增数据：
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/9fdb8f021e294043b909494b7eb25c45.png)
### 3.3 后台系统：用户管理
支持对用户信息的增加、删除、修改和查询：
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/ec4a7f18d708480cbf4ee93e73e416f4.png)
### 3.4 后台系统：个人设置
个人设置方面包含了用户信息修改、密码修改功能。
用户信息修改中可以上传头像，完成用户的头像个性化设置，也可以修改用户其他信息。
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/66269cb57a234e4d9abcefdb7e2b2a72.png)

## 4程序代码
### 4.1 代码说明
代码介绍：本系统基于Python开发，实现了空气质量数据的可视化展示。系统从MySQL数据库中读取通过爬虫获取的空气质量数据，使用Pandas进行数据处理和分析，并利用Matplotlib和Seaborn库生成多种可视化图表，如折线图展示空气质量指数变化趋势、柱状图比较不同污染物浓度、热力图显示区域污染分布等。系统支持按时间范围、地区等条件筛选数据，提供直观的数据洞察，帮助用户了解空气质量状况及其变化规律
### 4.2 流程图
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/20129ac17df24feca99fde1d47afe77f.png)
### 4.3 代码实例
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import pymysql
from datetime import datetime

def fetch_air_quality_data(host, user, password, database, query):
    """
    从MySQL数据库获取空气质量数据
    """
    connection = pymysql.connect(
        host=host,
        user=user,
        password=password,
        database=database,
        charset='utf8mb4'
    )
    
    try:
        df = pd.read_sql(query, connection)
        return df
    finally:
        connection.close()

def preprocess_data(df):
    """
    数据预处理：处理缺失值、转换数据类型等
    """
    # 填充缺失值或删除缺失行
    df = df.dropna()
    
    # 确保日期列为datetime类型
    if 'date' in df.columns:
        df['date'] = pd.to_datetime(df['date'])
    
    return df

def visualize_air_quality(df, chart_type='line'):
    """
    根据选择的可视化类型生成图表
    """
    plt.figure(figsize=(12, 6))
    
    if chart_type == 'line':
        # 折线图：展示AQI随时间变化
        plt.plot(df['date'], df['aqi'], marker='o', linestyle='-')
        plt.title('空气质量指数(AQI)变化趋势')
        plt.xlabel('日期')
        plt.ylabel('AQI指数')
        plt.xticks(rotation=45)
        
    elif chart_type == 'bar':
        # 柱状图：比较不同污染物
        pollutants = ['pm25', 'pm10', 'so2', 'no2', 'co', 'o3']
        avg_values = df[pollutants].mean()
        plt.bar(avg_values.index, avg_values.values)
        plt.title('各污染物平均浓度比较')
        plt.xlabel('污染物类型')
        plt.ylabel('浓度值')
        
    elif chart_type == 'heatmap':
        # 热力图：显示污染物相关性
        correlation = df[['pm25', 'pm10', 'so2', 'no2', 'co', 'o3', 'aqi']].corr()
        sns.heatmap(correlation, annot=True, cmap='coolwarm')
        plt.title('空气质量指标相关性热力图')
    
    plt.tight_layout()
    plt.show()

# 主程序
if __name__ == "__main__":
    # 数据库配置
    db_config = {
        'host': 'localhost',
        'user': 'your_username',
        'password': 'your_password',
        'database': 'air_quality_db'
    }
    
    # SQL查询语句
    query = "SELECT * FROM air_quality WHERE date >= '2023-01-01'"
    
    # 获取数据
    df = fetch_air_quality_data(**db_config, query=query)
    
    # 数据预处理
    df = preprocess_data(df)
    
    # 生成可视化图表
    visualize_air_quality(df, chart_type='line')  # 可选择 'line', 'bar', 或 'heatmap'

```
