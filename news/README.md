# News 操作说明

## 仓库目录结构示例

```text
official-web-data/
├── news/
│   ├── dictionary.json  # 新闻索引文件
│   │
│   ├── 2025031701/      # 第一个新闻分类文件夹
│   │   ├── football.md  # 足球新闻
│   │   ├── city.md      # 城市新闻
│   │   ├── football.jpg # 足球新闻图片
│   │   └── city.png     # 城市新闻图片
│   │
│   └── 2025031702/      # 第二个新闻分类文件夹
│       ├── tech-news.md # 科技新闻
│       └── tech.jpg     # 科技新闻图片
```

## 操作步骤

```mermaid
flowchart TB
    Start([开始]) --> Step1[步骤1: 新建 news 文件夹]
    Step1 --> Step2[步骤2: 创建 dictionary.json 文件]
    Step2 --> Step3[步骤3: 创建新闻分类文件夹]
    Step3 --> Step4[步骤4: 上传新闻 markdown 文件]
    Step4 --> Step5[步骤5: 添加图片到 markdown]
    Step5 --> Step6[步骤6: 上传新闻对应的图片]
    Step6 --> Step7[步骤7: 编辑 dictionary.json]
    Step7 --> End([完成])
    
    subgraph "文件夹命名规范"
        FolderNaming["使用格式: 日期+序号<br>例如: 2025031701<br>(2025年03月17日第1个分类)"]
    end
    
    subgraph "Markdown文件命名规范"
        MDNaming["使用英文/数字命名<br>多个单词用连字符(-)<br>例如: football.md, sports-news.md"]
    end
    
    subgraph "图片引用规范"
        ImgRef["使用完整的网络路径<br>例如: 图片语法 https://raw.githubusercontent.com/xxx/1.png  <br>"]
    end
    
    subgraph "dictionary.json 格式与内容规范"
        JsonFormat["JSON格式示例:<br>[<br>  {<br>    'title': '新闻标题',<br>    'img': 'https://图片完整路径',<br>    'desc': '新闻摘要内容',<br>    'link': '文件夹/文件名'<br>  }<br>]<br><br>• 新闻列表按从上到下排序<br>• 严格符合JSON格式<br>• 建议通过json4u.cn/editor校验"]
    end
    
    subgraph "字段说明"
        FieldDesc["• title: 首页新闻标题<br>• img: 首页新闻配图(完整网络路径)<br>• desc: 新闻摘要<br>• link: 新闻文件路径/文件名(不带.md后缀)"]
    end
    
    Step3 -.-> FolderNaming
    Step4 -.-> MDNaming
    Step5 -.-> ImgRef
    Step7 -.-> JsonFormat
    Step7 -.-> FieldDesc
```



## dictionary.json-结构示例

```json
[
    {
        "title": "又一个千万人口大市诞生了",
        "img": "https://raw.githubusercontent.com/naughtyJun/book/refs/heads/main/250309/3.png",
        "desc": "3月19日，安徽省统计局发布数据，合肥市常住人口突破1000万，成为中国第18座常住人口破千万的城市。",
        "link": "250309/1" // 不需要带文件名的后缀 ".md"
    },
    {
        "title": "国足，被“抬进”世界杯？",
        "img": "https://raw.githubusercontent.com/naughtyJun/book/refs/heads/main/250309/1.webp",
        "desc": "在近日举行的国际足联理事会会议即将结束时，来自乌拉圭的理事会成员提出了一项建议：2030年世界杯扩军至64支球队参加。",
        "link": "250309/football" // 不需要带文件名的后缀 ".md"
    },
    {
        "title": "苏州再发楼市新政",
        "img": "https://raw.githubusercontent.com/naughtyJun/book/refs/heads/main/250307/2.jpeg",
        "desc": "3月10日，苏州官方发布消息，当地住建局和金融部门出台了“三低一宽”房贷政策，叠加人才房票政策，进一步降低购房门槛，助力青年人、新市民购房置业。上海易居房地产研究院",
        "link": "250309/city" // 不需要带文件名的后缀 ".md"
    }
]
```