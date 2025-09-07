# **Climate and HealthRisk : 天氣與健康風險**

## **專題介紹**
本專案探討多個美國城市各種天氣相關變數對健康風險指標的影響，首先透過EDA來找出與健康風險指標相關的變數，然後利用機器學習的方法來進行預測，最後進行模型的比較與解釋。

---

## **資料介紹**

### **資料來源**
本專題的資料是來自於[Kaggle](https://www.kaggle.com/datasets/abdullah0a/urban-air-quality-and-health-impact-dataset/data)，包含1000筆數據以及46個天氣相關變數。

### **變數介紹**
總共將所有變數分為10大類 : 目標變數(健康風險指標)、天氣變數、降水、風、溫度、太陽、時間、地點、雪、其他。

---

## **研究方法** 

### **探索式資料分析(EDA)**
1. 處理缺失值  
2. 目標變數分析  
3. 各項變數與目標變數關聯分析
4. 相關係數熱力圖

### **特徵工程**
1. 新變數風速比率(最大風速/平均風速)
2. 對城市做Target encoding 
3. 二元變數處理(是否為週末0，1）

### **模型應用**
1. 模型前處理 : 
   - 將資料分為90%訓練集、10%測試集
   - 刪除相關性較低的兩個變數
   
2. 模型比較 :  
   - 利用pycaret建立模型，從訓練集再拆分出10%驗證集，且資料有經過標準化
   - 比較SVM、random Forest、KNN等8個模型的結果  
   - 最終SVM、Random Forest兩模型相對其他結果較好   

3. 模型解釋 : 
利用SHAP圖對SVM、Random Forest兩模型進行解釋。

---

## **結語**
1. 最終兩模型中，露點溫度為最重要的變數，可以多關注這個變數與健康風險的關係。    
2. 分析過程可以發現某一個州健康風險分數相對高，未來可以加入產業、地形等等變數。 
3. 最終Random Forest整體指標都稍微好於SVM，所以最終會以RF為最後選擇。

---

## **工具**
-  Python（pandas、numpy、matplotlib、seaborn）
-  機器學習（PyCaret、Random Forest、SVM）
-  數據預處理（Target Encoding、特徵選擇）
-  模型解釋性（SHAP）

---

## **參考資料**
- [資料來源](https://www.kaggle.com/datasets/abdullah0a/urban-air-quality-and-health-impact-dataset/data)
- [風險分數介紹](https://www.alberta.ca/about-the-air-quality-health-index)
- [熱指數介紹](https://www.weather.gov/ama/heatindex)
- [紫外線指數](https://www.cwa.gov.tw/Data/knowledge/announce/service13.pdf)

---  

## **結構**
Climate-and-HealthRisk    
│── README.md  
│── HealthRisk_main.pdf # 書面報告  
│── HealthRisk_code.ipynb # 程式碼  
│── HealthRisk_reort.pdf  # 簡報  
