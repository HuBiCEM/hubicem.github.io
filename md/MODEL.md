# HuBiCEM: Hunar Bin Cost Evaluation Model

## 📌 Overview  
**HuBiCEM (Hunar Bin Cost Evaluation Model)** is an advanced **cost estimation framework** designed for **Agile software development**. Unlike traditional models such as **COCOMO**, HuBiCEM focuses on **individual developer performance** rather than relying on team-wide assessments. By leveraging **machine learning and regression-based predictions**, HuBiCEM provides **accurate cost and time estimations** for future sprints.

📌 **GitHub Repository**: [HuBiCEM Model](https://github.com/HuBiCEM/model)  
📜 **License**: See [LICENSE](LICENSE)  

---

## 🚀 Key Features  
✔ **Sprint-Based Developer Evaluation** – Tracks individual developer effort.  
✔ **Regression-Based Predictions** – Applies **Polynomial Regression** to forecast sprint effort.  
✔ **HuBi Table Generation** – Stores developer-specific efficiency trends.  
✔ **Real-World Validation** – Successfully tested on the **OpenAI Assistant Project**.  
✔ **More Accurate than COCOMO** – Closer to actual project cost and time.  

---

## 🛠 Installation  
Make sure you have **Python 3.7+** installed. Then install the required dependencies:

```bash
pip install pandas numpy scikit-learn
```

---

## 📊 How HuBiCEM Works  
### **Step 1: Training the Model**  
Train the HuBiCEM model using past sprint data to build developer-specific regression models.

```bash
python src/train.py
```
📌 **Input:** Sprint history CSV  
📌 **Output:** `trained.csv` (Developer-wise equations for future predictions)  

---

### **Step 2: Predicting Future Sprint Costs**  
After training, HuBiCEM can estimate **cost and effort** for upcoming sprints.

```bash
python src/predict.py
```
📌 **Input:** `trained.csv`  
📌 **Output:**  
- **`prediction.csv`** → Predicted time per developer per category  
- **`report.txt`** → Summary of estimated time & cost  

---

## 📄 Input Data Format  
HuBiCEM requires sprint performance data in CSV format.

### **📝 Training Data (`sprints.csv`)**
```
Sprint Number,Task,Category,Developer,Expected Time (Hours),Actual Time (Hours),Performance Comment
1,Database Schema Design,Database,Muhammad Umer,15,18,Delayed
1,Backend API Architecture,Backend,Abdullah Ahmad,18,22,Delayed
...
```
✅ **Columns:**  
- **Sprint Number** → Sprint number (e.g., `1, 2, 3...`)  
- **Task** → The assigned task.  
- **Category** → Task category (Frontend, Backend, AI/ML).  
- **Developer** → Developer assigned.  
- **Expected Time (Hours)** → Estimated completion time.  
- **Actual Time (Hours)** → Time taken.  
- **Performance Comment** → Performance feedback (`Good`, `Delayed`, etc.).  

---

## 📂 HuBiCEM File Structure  
```
HuBiCEM/
│── src/
│   ├── train.py          # Trains HuBiCEM Model
│   ├── predict.py        # Predicts time & cost using trained model
│
│── examples/
│   ├── example_train.csv # Sample sprint dataset
│   ├── example_output/   # Sample prediction results
│
│── LICENSE               # License file
│── README.md             # Documentation
```

---

## 🔍 Sample Predictions  
Once the model is trained, it can estimate **effort and cost** for upcoming sprints.

#### **📄 Output 1: `prediction.csv`**
```
#,Employee,Frontend,Backend,Database,AI/ML,Server
1,Abdullah Ahmad,12.4,14.1,9.5,15.2,11.0
2,Muhammad Umer,10.3,12.0,14.2,9.0,13.1
...
```

#### **📄 Output 2: `report.txt`**
```
🔹 Project Estimated Hours: 1450.75 hours
🔹 Estimated Duration: 3.2 months
🔹 Estimated Total Cost: $72,500.50
```

---

## 📜 License  
This project is licensed under the **HuBiCEM License**.  
- ✅ **Allowed:** Use for personal and commercial projects.  
- 🚫 **Not Allowed:** Republishing under another name.  

See **[LICENSE](LICENSE)** for details.  

---

## 👨‍💻 Contributors  
- **Abdullah Ahmad** ([@MAbdullahAhmad](https://github.com/MAbdullahAhmad))  
- **Abdullah Bajwa** ([@Abdullah007bajwa](https://github.com/Abdullah007bajwa))  

💡 **Contribute?** Feel free to **open an issue** or **submit a pull request!** 🚀  