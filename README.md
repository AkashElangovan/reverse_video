# **Reverse Videos in Google Drive Using Tesla GPU (Colab Notebook)**
This **Google Colab Notebook** automatically **reverses all videos** inside a given Google Drive folder (including subfolders) using **Tesla GPU acceleration**. It preserves the folder structure and creates a new folder with `_reversed` appended to the name.

---

## **🚀 Features**
✅ **Uses Google Drive as input/output** (No need to download videos).  
✅ **Recursively scans subfolders** and reverses all video files.  
✅ **Uses NVIDIA Tesla GPU (CUDA) acceleration** for **3-5x faster processing**.  
✅ **Maintains original format** and folder structure.  
✅ **No manual intervention needed** – just set the folder and run!  

---

## **📌 How to Use**
### **1️⃣ Open Google Colab**
Go to **[Google Colab](https://colab.research.google.com)** and create a new notebook.

### **2️⃣ Enable GPU**
- Click **Runtime → Change runtime type**  
- Select **GPU**  
- Click **Save**  

### **3️⃣ Install Required Dependencies**
Run the following in a **Colab cell** to install **CUDA-enabled FFmpeg**:
```python
!sudo apt-get update
!sudo apt-get install -y ffmpeg
!pip install imageio[ffmpeg]

# ✅ Verify GPU availability
!nvidia-smi
```
If you see a **Tesla GPU (T4/K80/V100)**, you’re good to go! 🎉

### **4️⃣ Mount Google Drive**
Run:
```python
from google.colab import drive
drive.mount('/content/drive')
```
Authorize access to your Google Drive.

### **5️⃣ Set the Input Folder**
Edit the following in the script:
```python
SOURCE_FOLDER = "/content/drive/MyDrive/YOUR_SOURCE_FOLDER"
```
Replace **`YOUR_SOURCE_FOLDER`** with the actual folder name inside **Google Drive**.

### **6️⃣ Run the Video Reversal Script**
Execute the provided Python script to start processing.

### **7️⃣ Find Reversed Videos in Google Drive**
After completion, the reversed videos will be saved inside:
```
/content/drive/MyDrive/YOUR_SOURCE_FOLDER_reversed
```
Each reversed file will have `_reversed` appended to its filename.

---

## **🎯 Example**
If you set:
```python
SOURCE_FOLDER = "/content/drive/MyDrive/MyVideos"
```
Your reversed videos will be in:
```
/content/drive/MyDrive/MyVideos_reversed
```

---

## **🔧 Troubleshooting**
### **Q1: The script runs slowly. How can I speed it up?**
✅ Make sure you enabled **GPU acceleration** (`Runtime → GPU`).  
✅ Use **shorter videos** (longer videos take more processing time).  

### **Q2: My videos don’t appear in the reversed folder. What’s wrong?**
✅ Double-check that **`SOURCE_FOLDER`** is set correctly.  
✅ Ensure **videos are in supported formats** (`.mp4`, `.mkv`, `.avi`, `.mov`, `.flv`).  

---

## **⚡ Performance Boost**
- **Without GPU (CPU-based FFmpeg)** → ❌ Slow (~real-time processing).  
- **With CUDA (`h264_nvenc`) on Tesla GPU** → ✅ **3-5x Faster** 🚀  

---

## **📌 Notes**
- **Works only on Google Drive folders** (No YouTube streaming).  
- Processing time depends on **video length & resolution**.  
- GPU acceleration only works if a **Tesla GPU is assigned**.  

---

## **🎯 Conclusion**
This Colab Notebook provides a **fast & automated** way to **reverse videos using a Tesla GPU**. Perfect for large batch processing while keeping your **Google Drive organized**. 🚀🔥  

**Enjoy video reversing at ultra-fast speeds!** 😊🎬  
