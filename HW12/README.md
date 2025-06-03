## 作業內容 : 期末專案提案
### 專案名稱 : Retrieval-Augmented Generation 聊天機器人
執行平台： Google Colab

開發工具： Python、LangChain、OpenAI API、FAISS、Gradio
#### 一、專案動機與目標
隨著生成式 AI 的發展，傳統聊天機器人容易出現「幻覺（hallucination）」問題，導致回答與事實不符。Retrieval-Augmented Generation（RAG）是一種結合語言模型與知識檢索技術的方法，能使 AI 回答更準確、可信。本專案旨在實作一個能針對給定文件回答問題的 AI 聊天機器人。
#### 二、方法概述
1. 利用 LangChain 框架建構資料檢索流程。
2. 使用 FAISS 建立向量資料庫，儲存文件片段的語意向量。
3. 整合 OpenAI GPT 模型生成回答。
4. 搭配 Gradio 製作互動式聊天 UI，提供使用者提問與回答。
#### 三、預期成果
* 成功建構一個能回答特定文件內容問題的聊天機器人。
* 使用者可以透過簡單介面輸入問題，獲得符合內容的精準回答。
* 報告內容將包含技術說明、程式碼解析、成果截圖與展示影片連結。
