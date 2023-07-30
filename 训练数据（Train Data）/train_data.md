# 训练数据汇总
## 汇总

| 模型 | 底座 | 参数量 | 数据构成 | 机构 |
| --- | ---- | ---- | ----- | ----- |
| 模型 | 底座 | 参数量 | 数据构成 | 机构 |
| 模型 | 底座 | 参数量 | 数据构成 | 机构 |

## falcon系列

### falcon
底座模型  
模型地址: https://huggingface.co/tiiuae/falcon-7b  


### falcon_instruct
SFT模型  
模型地址: https://huggingface.co/tiiuae/falcon-7b-instruct  

训练数据组成(来自huggingface上的模型介绍):  
|Data source|	Fraction|	Tokens|	Description|
| --- | ---- | ---- | ----- |
|Bai ze|	65%|	164M|	chat|
|GPT4All|	25%|	62M| instruct|
|GPTeacher|	5%|	11M|	instruct|
|RefinedWeb-English|	5%|	13M|	massive web crawl|

Bai Ze: https://github.com/project-baize/baize-chatbot  
数据样例1:  
```{"topic": "Parsing json directly using input stream", "input": "The conversation between human and AI assistant.\n[|Human|] Can you tell me more about parsing JSON directly using input stream?\n[|AI|] Sure! JSON stands for JavaScript Object Notation, and it's a commonly used format for exchanging data in web applications. When you parse JSON directly using an input stream, you can process large JSON files without having to load the entire file into memory. This can be useful when working with big data.\n[|Human|] That sounds interesting. Can you show me an example of how to parse JSON using an input stream in code?\n[|AI|] Sure thing. Here's an example code snippet in Java:\n\nJsonReader jsonReader = new JsonReader(new InputStreamReader(new FileInputStream(\"example.json\"), \"UTF-8\"));\n\njsonReader.beginArray();\nwhile (jsonReader.hasNext()) {\n    jsonReader.beginObject();\n    while (jsonReader.hasNext()) {\n        String name = jsonReader.nextName();\n        if (name.equals(\"id\")) {\n            int id = jsonReader.nextInt();\n        } else if (name.equals(\"name\")) {\n            String name = jsonReader.nextString();\n        } else if (name.equals(\"email\")) {\n            String email = jsonReader.nextString();\n        } else {\n            jsonReader.skipValue();\n        }\n    }\n    jsonReader.endObject();\n}\njsonReader.endArray();\n[|Human|] "}```  
数据样例2:  
``` {"topic": "What are the three primary colors?", "input": "The conversation between human and AI assistant.\n[|Human|] What are the three primary colors?\n[|AI|] The three primary colors are red, blue, and yellow.\n[|Human|] "}```

Chat4All: https://huggingface.co/datasets/nomic-ai/gpt4all-j-prompt-generations  

GPTeacher:  https://github.com/teknium1/GPTeacher  

RefinedWeb-English: https://huggingface.co/datasets/tiiuae/falcon-refinedweb  

### falcon_sft_top_1
SFT模型  

### falcon_sft_mix
SFT模型  

## llama系列
