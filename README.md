# Kaggle_Titanic

Kaggle - Titanic - Machine Learning from Disaster

這是由Kaggle所舉辦的機器學習練習賽，提供訓練資料，參賽者回傳預測結果，將顯示正確率及排名。

規則如下：
使用kaggle所提供的train.csv作為訓練資料
預測test.csv資料中乘客最後是否存活
將結果輸出為乘客ID、是否存活兩項資料並回傳

訓練方式：
資料預處理
姓名特徵中包含Ms, Mr, Dr 等稱謂，將其分割出來並捨去姓名作為特徵使用
房號特徵捨去後面數字，只保留第一碼英文，遺漏值皆設為新的值'X'
年齡特徵遺漏值放入平均年齡
登船港口遺漏值設最多人登船的港口
將影響較小特徵捨去，包含乘客ID,家人數量,姓名
性別、登船港口、傳票等級、稱謂、房號做Label Encoding

訓練模型：
使用GridSearchCV找出最佳超參數
使用cross_val_score測試模型準確率 # 比較模型差異，此次4種皆上傳測試
找到最佳超參數後帶入模型，即可預測test資料

測試其他模型：
此次使用SVC, RandomForest, XGBoost, KNN 四種模型
重複進行2.流程訓練模型並比較準確率

預測test結果：
四種模型分別對test進行預測
使用CalibratedClassifierCV將兩個以上模型的結果合併，產生新的模型並預測結果

