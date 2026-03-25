# Ctrl-F-
#
🏗️ 系統架構
本專案採用三層解耦架構：
 * 感知層 (Vision): YOLO-World + OpenCV。
 * 記憶層 (Memory): SQLite (軌跡) + ChromaDB (特徵) + Shapely (幾何判定)。
 * 整合層 (Integration): FastAPI (後端) + Streamlit (前端 UI)。
🛠️ 安裝與環境設定
1. 硬體需求
 * GPU: NVIDIA RTX 30 系列以上 (推薦 RTX 5070 Ti 以達到最佳效能)。
 * RAM: 16GB 以上 (推薦 64GB 以優化向量資料庫讀取)。
2. 環境安裝
# 建議使用虛擬環境
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 安裝支援 CUDA 的 PyTorch
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu121

# 安裝其餘依賴項
pip install -r requirements.txt

🚀 快速啟動
 * 設定區域範圍：
   編輯 config/areas.json 定義房間內的標記區域座標。
 * 啟動後端 API：
   uvicorn api.main:app --reload

 * 啟動前端介面：
   streamlit run ui/app.py

📅 開發進度 (Roadmap)
 * [x] 專案架構建立 (Copilot Workspace)
 * [x] YOLO-World 偵測模組開發
 * [ ] 空間區域判定邏輯 (PIP)
 * [ ] 雙軌資料庫聯動測試
 * [ ] 最終系統整合與 UI 優化
👥 團隊分工
 * 成員 A (Vision): 模型封裝、1080p 推論優化、硬體效能監控。
 * 成員 B (Memory): SQLite/ChromaDB 架構設計、空間幾何判定演算法。
 * 成員 C (Integration): FastAPI 路由設計、Streamlit 介面開發、系統整合。

