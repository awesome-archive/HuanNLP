# HuanNLP
self implement of NLP toolkit
个人实现NLP汉语自然语言处理组件，包括分词，词性标注，命名实体识别等. coding now....
# 使用简介
# 引入
import nlp
nlp = huannlp.HuanNLP('HMM') 
或者 nlp = huannlp.HuanNLP('CRF') 
text = "刘焕勇硕士毕业于北京语言大学，目前在中国科学院软件研究所工作"  
# 分词
words = huannlp.cut(text)  
HMM模式：['刘焕勇', '硕士', '毕业', '于', '北京', '语言', '大学', '，', '目前', '在', '中', '国', '科学', '院', '软', '件', '研究', '所', '工作']  
CRF模式：['刘焕勇', '硕士', '毕业于', '北京', '语言', '大学', '，', '目前', '在', '中国科学院', '软件', '研究', '所', '工作']  
# 词性标注
postags = huannlp.postag(text)  
HMM模式：['r', 'n', 'v', 'p', 'ns', 'n', 'n', 'w', 'nt', 'p', 'nd', 'n', 'n', 'n', 'a', 'n', 'v', 'u', 'n']  
CRF模式：['n', 'n', 'v', 'ns', 'n', 'n', 'w', 'nt', 'p', 'ni', 'n', 'v', 'u', 'n']  
词性对照表    
| 标记 | 词性 | 标记 | 词性 | 标记 | 词性 | 标记 | 词性 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| n | 普通名词 | nt | 时间名词 | nd | 方位名词 | nl | 处所名词 |
| nh | 人名 | nhf | 姓 | nhs | 名 | ns | 地名 |
| nn | 族名 | ni | 机构名 | nz | 其他专名 | v | 动词 |
| vd | 趋向动词 | vl | 联系动词 | vu | 能愿动词 | a |  形容词 |
| f | 区别词 | m | 数词 | q | 量词 | d | 副词 |
| r | 代词 | p | 介词 | c | 连词 | u | 助词 |
| e | 叹词 | o | 拟声词 | i | 习用语 | j | 缩略语 |
| h | 前接成分 | k | 后接成分 | g | 语素字 | x | 非语素字 |
| w | 标点符号 | ws | 非汉字字符串 | wu | 其他未知的符号 | -- | --- |    
# 命名实体识别  
ners = huannlp.ner(text)  
HMM模式：{'TIM': [], 'PER': ['刘焕勇'], 'LOC': [], 'ORG': []}   
CRF模式：{'LOC': [], 'TIM': ['目前'], 'PER': ['刘焕勇'], 'ORG': ['中国科学院', '北京语言大学']}   
实体标记对照表  

| 标记 | 实体类型 |
| --- | --- |
| LOC | 地名实体 |
| PER | 人名实体 |
| ORG | 机构实体 |
| TIM | 时间实体 |
