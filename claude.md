# Secret Santa Project Context

## Project Overview
Python-based Secret Santa pairing and email notification system. Generates gift exchange pairings based on constraints (no self-gifting, no reciprocal pairs, no roommates) and automatically emails participants.

**Purpose**: Automate Secret Santa/Secret Valentine event management for groups, ensuring fair pairings and automated notifications.

## Tech Stack

### Language & Runtime
- **Python**: Core language (version not specified, likely Python 3)

### Key Dependencies
- CSV processing: Built-in `csv` module
- Email sending: SMTP library (in `sendemail.py`)
- Random pairing: Built-in `random` module

### Data Format
- **CSV files**: Input participant data and output pairings

## Build & Deployment

### Running the Scripts
```bash
# 1. Generate pairings (safe to run multiple times)
python pairing.py

# 2. Send emails (WARNING: sends emails to all participants!)
python sendemail.py
```

### Input Format
- `list.csv`: Participant data with columns:
  - Timestamp (ignored)
  - Full name
  - Room number
  - Email address

### Output Format
- `pairs.csv`: Generated pairings with giver and receiver columns

## Project Conventions

### Pairing Rules
1. No self-gifting
2. No reciprocal pairs (A→B and B→A)
3. No roommate pairings
4. No giving to roommate's household member
5. Everyone gets exactly one gift

### Algorithm Approach
- Shuffle-and-check method (optimized for coding time, not efficiency)
- Reshuffles until all constraints are satisfied

### Safety Practices
- **IMPORTANT**: `sendemail.py` sends emails immediately upon running
- Always verify `pairs.csv` before running `sendemail.py`
- Test email configuration with small group first

## Key Files
- `pairing.py`: Pairing generation logic
- `sendemail.py`: Email sending script
- `list.csv`: Participant input data
- `pairs.csv`: Generated pairings output
- `README.md`: Project documentation
- `COPYING.txt`: License file
