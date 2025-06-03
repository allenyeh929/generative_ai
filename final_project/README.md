## 期末專案
專案名稱： 基於檢索增強生成（RAG）的電腦圖學專家聊天機器人

開發平台： Google Colab

開發工具： Python, LangChain, FAISS, Hugging Face Transformers, Gradio

### 一、專案背景與動機
隨著生成式 AI 技術的發展，許多語言模型如 ChatGPT 等在開放知識回答上表現良好，但在特定領域（如電腦圖學）常會出現知識不完整、生成錯誤或幻覺（hallucination）問題。為了解決這個問題，本專案導入了 Retrieval-Augmented Generation (RAG) 架構，讓聊天機器人能根據我們提供的「電腦圖學知識資料庫」回答問題，提升正確率與可信度。

### 二、專案目標
本專案的目標是：
1. 建立一個能夠針對電腦圖學知識做問答的聊天機器人。
2. 使用 LangChain 架構整合文件檢索與語言模型回應。
3. 使用 Hugging Face 的免費嵌入與文字生成模型（Flan-T5）實作。
4. 提供 Gradio 前端，讓使用者可以自然地輸入問題並獲得具知識根據的回答。

### 三、技術架構與流程
![image](https://github.com/user-attachments/assets/518dffdd-07a5-46db-acf0-de95cfcd7e36)

#### 技術流程說明：
1. 知識資料載入：
  * 讀取一份以 .txt 編寫的電腦圖學資料，包含 rasterization、ray tracing、graphics pipeline、OpenGL、BVH 等核心主題。
2. 文字分段與向量轉換：
  * 使用 CharacterTextSplitter 將資料切成 chunk（每段約 300 字），並使用 sentence-transformers 模型進行嵌入（embedding）。
3. 向量資料庫建立：
  * 使用 FAISS 建立高效檢索索引，便於之後從知識庫中找出與問題最相關的段落。
4. 檢索增強生成（RAG）流程：
  * 使用 LangChain 的 RetrievalQA 模組，設定自訂 Prompt Template，將「檢索到的知識段落」+「使用者問題」一起丟給文字生成模型（Flan-T5），產出最終回答。
5. 互動式界面：
  * 使用 Gradio 建立前端界面，使用者可輸入問題並即時看到專業回應與備註說明。

### 四、實際測試與展示
![image](https://github.com/user-attachments/assets/c00f7c1e-7cc5-407a-911a-96cd0a5be83a)

### 五、優點與限制
* 優點
  * 回答內容具有「文件根據」，不會亂猜
  * 完全基於 Hugging Face 模型，免費、可離線運行
  * 架構模組化，容易擴充資料集與前端

* 限制
  * 使用的 Flan-T5 為輕量模型，表達能力有限
  * 若知識庫沒有包含答案，回覆可能模糊
  * 檢索段落未顯示原始出處（可改進）

### 六、未來方向
* 支援多檔案上傳（如 PDF, HTML）
* 回答中加入「引用段落來源」顯示
* 改用更強 Hugging Face 模型（如 Mistral、LLaMA3）
* 支援中文介面與中文知識庫
* 模型回應加強邏輯說明與圖解輔助

### 七、結論
本專案成功整合 RAG 架構，結合文字嵌入、向量檢索與生成模型，打造出一個針對「電腦圖學領域」具回答能力的 AI 聊天機器人。透過 Prompt Engineering 讓模型回答更具風格與專業性，成果具備可視化、可擴充與教育應用潛力。
