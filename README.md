# 🍽️ Table Occupancy AI & Staff Scheduler

An end-to-end Computer Vision and Operations Research pipeline that transforms raw video feeds (e.g., iPhone stream) into real-time restaurant table analytics and automated staff shift schedules.

---

## 🌟 Key Features

- 📹 **Flexible Video Ingestion**: Connects seamlessly to RTSP/HTTP video streams from smartphones or IP cameras.
- 🎯 **Polygon ROI Table Tracking**: Defines custom table boundaries using `Shapely` polygons for spatial awareness.
- 🧠 **YOLO Object Detection**: Tracks patrons, glasses, plates, and cutlery using YOLOv8/v11 models.
- ⏱️ **Finite State Machine (FSM)**: Manages table lifecycles and tracks exact durations for:
  - `FREE` $\rightarrow$ Table is empty and available.
  - `WAITING_SERVICE` $\rightarrow$ Customers seated, awaiting orders/service.
  - `SERVED` $\rightarrow$ Customers actively dining.
  - `FINISHED` $\rightarrow$ Meal completed, awaiting bill or cleanup.
- 📊 **Database Logging**: Persists state transition events and temporal metrics in SQLite.
- 🗓️ **Shift Optimization (MILP)**: Uses Mixed-Integer Linear Programming (`PuLP`) to generate optimal weekly waiter staffing schedules based on historical peak loads and wait times.

---

## 🏗️ System Architecture

To do

## 🛠️ Tech Stack

- **Language**: Python 3.10+
- **Computer Vision**: OpenCV, Ultralytics YOLOv8/v11, Shapely
- **Data Analytics**: Pandas, NumPy
- **Optimization**: PuLP (Mixed-Integer Linear Programming)
- **Database**: SQLite

---

## 🚀 Quick Start

### 1. Clone & Setup Environment

```bash
git clone [https://github.com/YOUR_USERNAME/table-occupancy-ai.git](https://github.com/YOUR_USERNAME/table-occupancy-ai.git)
cd table-occupancy-ai

python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt