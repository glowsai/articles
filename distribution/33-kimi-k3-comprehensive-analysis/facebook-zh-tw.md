# Facebook 貼文（zh-TW）— Kimi K3 全面解析：2.8 萬億參數與百萬上下文

來源：`articles/posts/blog/zh-TW/33.kimi-k3-comprehensive-analysis.mdx`
定位：給台灣 AI 開發者與基礎設施團隊的技術解讀。

Kimi K3 不只是「更大的聊天模型」：

🔹 2.8 萬億總參數、1040 億激活參數
🔹 原生圖片輸入，官方服務也提供影片輸入
🔹 1,048,576 token 上下文
🔹 896 個路由專家，每個 token 選擇 16 個
🔹 Kimi Delta Attention、Attention Residuals、Stable LatentMoE

真正的門檻在部署：MoE 能降低每 token 計算量，但完整權重仍要分布在多張 GPU；百萬上下文還會受到 KV Cache、預填充、併發和網路互聯影響。

官方評測涵蓋程式設計、工具調用、網路研究、文件視覺理解和桌面操作，但 benchmark 是模型方公布的結果，不能直接當成你的工作負載保證。

實務上可以先用 API 評估，再用較小 GPU 驗證 RAG、資料處理和 Agent 工作流，需求確定後才規劃 H100、H200 或 B200 多節點集群。開放權重也不代表商業授權沒有條件，正式部署前要讀完整 license。

完整繁中解析：
https://glows.ai/article/kimi_k3_comprehensive_analysis_zh_tw

#KimiK3 #大模型 #AI基礎設施 #GPU #GlowsAI
