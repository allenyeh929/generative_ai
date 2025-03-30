### 詢問問題
幫我用python生成出GIF，內容為模擬太陽系的運動軌跡

### ChatGPT 4o
![image](https://github.com/allenyeh929/generative_ai/blob/main/HW4/solar_system.gif)

### Claude 3.7 Sonnet
![image](https://github.com/allenyeh929/generative_ai/blob/main/HW4/solar_system2.gif)

### 結論
兩個模型其實生成出來的結果蠻相近的，但其中還是有一些差異:

1.ChatGPT 所生成出來的太陽系裡的每一個行星的大小都一致，但 Claude 是根據真實的行星大小所生成的。

2.兩者在顯示時都只有 4 個行星(不包含太陽)，但看程式碼會發現 ChatGPT 確實只定義了 4 個行星，但其實 Claude 定義了 8 個行星，但可能是 colab 的顯示問題導致只顯示出 4 個。

3.兩者相比起來 Claude 對提示詞的理解及宇宙的規則略勝一籌。
