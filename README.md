# Hospital Data Monitoring & Archival System

![Hospital Monitor](https://img.shields.io/badge/Hospital-Data%20Monitoring-blue)
![Shell Script](https://img.shields.io/badge/Shell-Scripting-green)
![Python](https://img.shields.io/badge/Python-Simulation-yellow)

## 📋 Project Overview

An automated log management system designed for hospital environments that collects real-time patient health metrics and resource usage data, provides controlled log archiving with user selection, and generates analytical reports with device statistics and temporal patterns.

### 🎯 Project Objectives

- **Real-time Data Collection**: Monitor patient health metrics and resource usage
- **Automated Log Management**: Structured archival system with timestamping
- **Interactive Analysis**: Generate statistical reports from collected data
- **Shell Scripting Proficiency**: Demonstrate advanced Linux command-line skills

## 🏗️ System Architecture

### Directory Structure
```
hospital_data/
├── active_logs/
│   ├── heart_rate.log
│   ├── temperature.log
│   └── water_usage.log
├── heart_data_archive/
├── temperature_archive/
├── water_usage_archive/
└── reports/
    └── analysis_report.txt
```

### 🔧 Core Components

#### Python Simulators
- **heart_monitor.py** - Simulates 2 heart rate monitoring devices
- **temp_sensor.py** - Simulates 2 temperature sensors  
- **water_meter.py** - Simulates water usage monitoring

#### Shell Scripts
- **archive_logs.sh** - Interactive log archival system
- **analyze_logs.sh** - Intelligent data analysis and reporting

## 🚀 Getting Started

### Prerequisites
- Linux/Unix environment
- Python 3.x
- Bash shell
- Standard Unix utilities (awk, grep, sort, uniq, etc.)

### Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/Goketech/coding-lab-28.git
   cd coding-lab-28
   ```

2. **Create directory structure**
   ```bash
   mkdir -p hospital_data/{active_logs,heart_data_archive,temperature_archive,water_usage_archive,reports}
   ```

3. **Make scripts executable**
   ```bash
   chmod +x archive_logs.sh analyze_logs.sh
   ```

### 🏃‍♂️ Running the System

#### Start Data Collection
Run each simulator in separate terminals:

```bash
# Terminal 1
python3 heart_monitor.py start

# Terminal 2  
python3 temp_sensor.py start

# Terminal 3
python3 water_meter.py start
```

#### Verify Data Collection
```bash
tail -f hospital_data/active_logs/heart_rate.log
tail -f hospital_data/active_logs/temperature.log
tail -f hospital_data/active_logs/water_usage.log
```

## 📚 Usage Guide

### 🗃️ Log Archival (archive_logs.sh)

Interactive script that allows selective archival of active log files.

```bash
$ ./archive_logs.sh
```

**Features:**
- Menu-driven selection of log types
- Timestamp-based archive naming (YYYY-MM-DD_HH:MM:SS format)
- Automatic creation of new empty log files
- Comprehensive error handling

**Example Output:**
```
Select log to archive:
1) Heart Rate
2) Temperature  
3) Water Usage
Enter choice (1-3): 1

Archiving heart_rate.log...
Successfully archived to heart_data_archive/heart_rate_2024-06-18_15:22:10.log
New heart_rate.log created for continued monitoring.
```

### 📊 Data Analysis (analyze_logs.sh)

Intelligent analysis script that processes log data and generates statistical reports.

```bash
$ ./analyze_logs.sh
```

**Features:**
- Interactive log file selection
- Device occurrence counting
- Timestamp analysis (first/last entry tracking)
- Cumulative reporting to analysis_report.txt

**Analysis Output:**
- Total count per device
- First and last entry timestamps
- Statistical summaries
- Trend analysis

### 📈 Report Generation

All analysis results are automatically appended to `reports/analysis_report.txt` with timestamps for historical tracking.

## 🛠️ Technical Implementation

### Key Technologies & Commands

| Task | Essential Commands |
|------|-------------------|
| **Archival** | `date`, `mv`, `touch`, `select/case`, `test` |
| **Analysis** | `awk`, `grep`, `sort`, `uniq`, `head`, `tail` |
| **Reporting** | `echo`, `>>`, `date` |

### Error Handling

Both scripts include robust error handling for:
- Invalid user input validation
- Missing log file detection
- Archive directory accessibility
- File permission issues
- Data integrity checks

## 🎓 Learning Objectives

### 1. **Shell Scripting Proficiency**
- Interactive menu systems using `select/case`
- Advanced file operations and manipulation
- Input validation and error handling
- Process automation

### 2. **Log Management & Automation**
- Structured archival systems with timestamping
- Log rotation without service disruption
- Programmatic directory organization
- Data preservation strategies

### 3. **Data Analysis with CLI Tools**
- Text processing with `awk`, `grep`, `sort`, `uniq`
- Statistical analysis from log data
- Formatted report generation
- Cumulative data aggregation

## 📁 File Descriptions

| File | Purpose |
|------|---------|
| `heart_monitor.py` | Heart rate sensor simulation |
| `temp_sensor.py` | Temperature sensor simulation |
| `water_meter.py` | Water usage monitoring simulation |
| `archive_logs.sh` | Interactive log archival script |
| `analyze_logs.sh` | Data analysis and reporting script |
| `README.md` | Project documentation |

## 🔍 Monitoring & Maintenance

### Real-time Monitoring
```bash
# Monitor all active logs simultaneously
tail -f hospital_data/active_logs/*.log

# Check system status
ls -la hospital_data/active_logs/
```

### Archive Management
```bash
# View archived files
ls -la hospital_data/*/

# Check archive sizes
du -sh hospital_data/*_archive/
```

## 🤝 Contributing

This is a group-based educational project. Contributions are tracked through GitHub commits to assess individual member participation.

### Contribution Guidelines
- Each team member should contribute to different components
- Document all changes with clear commit messages
- Test thoroughly before pushing changes
- Follow coding standards for shell scripts and Python

## 📄 License

This project is created for educational purposes as part of a coding laboratory assignment.

## 👥 Team Members

**Annie Pierre Bwiza**

**Modupe Adegoke Akanni**

**Charles Were Angoye** 

**Gael Kamunuga Mparaye**

**Milliam Mukamukiza**

## 👥 Team Information

**Project Type**: Group Coding Lab  
**Weight**: 18% of final grade  
**Submission**: GitHub repository  
**Assessment**: Individual contributions via GitHub commit history

---

## 🆘 Troubleshooting

### Common Issues

**Simulators not generating data:**
- Ensure Python 3 is installed and accessible
- Check file permissions on the scripts
- Verify directory structure exists

**Archive script errors:**
- Confirm bash shell compatibility
- Check write permissions on archive directories
- Validate log file existence before archival

**Analysis script issues:**
- Ensure required Unix utilities are available
- Check log file formatting and structure
- Verify reports directory is writable

---

**Last Updated**: June 2025  
**Version**: 1.0.0