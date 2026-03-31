# -25BAI11304-College-Path-Finder
## Campus Placement Predictor

A Python command-line tool that takes your subject marks, calculates your GPA, and predicts your shortlisting probability across top campus recruiters — using an AI-inspired heuristic search approach.



## What It Does

1. Accepts marks for **5 subjects** (out of 100)
2. Computes your **GPA** on a 10-point scale
3. Filters companies you are **eligible** for based on their minimum GPA cutoff
4. Calculates a **shortlisting probability (%)** for each eligible company using a custom heuristic formula
5. Ranks results from **highest to lowest probability** — mimicking Best-First Search from AI



##  Supported Companies

| Company     | Min GPA | Difficulty |
|-------------|---------|------------|
| TCS         | 6.0     | Low        |
| Infosys     | 6.5     | Low        |
| Wipro       | 7.0     | Medium     |
| Cognizant   | 7.0     | Medium     |
| Accenture   | 7.5     | Medium     |
| Amazon      | 8.5     | High       |



##  Requirements

- Python 3.x (no external libraries needed)

Check your Python version:
```bash
python --version
```



##  How to Run

**1. Clone the repository**
```bash
git clone https://github.com/your-username/campus-placement-predictor.git
cd campus-placement-predictor
```

**2. Run the script**
```bash
python placement_predictor.py
```

**3. Enter your marks when prompted**
```
Enter marks of 5 subjects:
Subject 1: 82
Subject 2: 78
Subject 3: 85
Subject 4: 80
Subject 5: 76
```

---

##  Sample Output

```
 Your GPA: 8.02

--- Predicted Shortlisting ---
TCS: 90% chance
Infosys: 80% chance
Wipro: 60% chance
Cognizant: 60% chance
Accenture: 31% chance
```

> Amazon is not shown because the student's GPA (8.02) does not meet the 8.5 minimum cutoff.



##  How the Probability Formula Works

```
P = max(0, min(100, (GPA - MinGPA) × 20 - (Difficulty × 10) + 50))
```

| Component              | Role                                                   |
|------------------------|--------------------------------------------------------|
| `(GPA - MinGPA) × 20`  | Rewards how far above the cutoff your GPA is           |
| `- (Difficulty × 10)`  | Penalises harder/more selective companies              |
| `+ 50`                 | Base offset so meeting the cutoff gives a fair baseline|
| `max(0, min(100, ...))`| Clamps result to a valid 0–100% range                  |



##  Project Structure

```
campus-placement-predictor/
│
├── placement_predictor.py   # Main program file
└── README.md                # This file
```



##  Planned Improvements

- Load company data from a CSV file
- Factor in backlogs, certifications, and projects
- Add a web/GUI interface using Tkinter or Flask
- Train on real placement data for ML-based predictions



##  Author

Pratham Kumar Yadav (25BAI11304)  
B.Tech — Computer Science & Engineering  
VIT Bhopal University

---

## License

This project is submitted for academic purposes at VIT Bhopal University.  
Feel free to fork and extend for personal or educational use.
