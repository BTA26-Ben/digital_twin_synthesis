# Smart Room Temperature Monitor

A Python simulation of a smart room temperature sensor using a **Kalman filter**
to recover true temperature from noisy, dropout-prone sensor readings.

## What it does
- Simulates 24 hours of room temperature physics (heating, occupancy, outdoor weather)
- Models a real thermometer with Gaussian noise and random dropout
- Applies a Kalman filter to estimate true temperature more accurately than the raw sensor
- Exports all 288 timesteps to Excel for MATLAB / ML analysis

## Results
| Method | RMSE |
|---|---|
| Raw sensor | ~0.46 °C |
| Kalman filter | ~0.46 °C (improves around dropout events) |

## Files
| File | Purpose |
|---|---|
| `sensor.py` | Thermometer simulation with noise and dropout |
| `kalman.py` | 1D Kalman filter |
| `simulation.py` | Room physics model + 24h runner + Excel export |
| `tests/test_all.py` | 28 unit and integration tests |

## How to run
```bash
pip install numpy pandas openpyxl pytest
python simulation.py
```

## Run tests
```bash
python -m pytest tests/ -v
```
```

4. Click **"Commit changes"**

---

## Step 4 — Upload the Excel results file (optional)

If you want to include the sample output:
1. **"Add file"** → **"Upload files"**
2. Drag in `smart_room_results.xlsx`
3. Commit message: `Add sample simulation output`
4. Click **"Commit changes"**

---

## What your repo will look like when done
```
smart-room-kalman/
├── README.md
├── requirements.txt
├── sensor.py
├── kalman.py
├── simulation.py
├── smart_room_results.xlsx
└── tests/
    └── test_all.py
