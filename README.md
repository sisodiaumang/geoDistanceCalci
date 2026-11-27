# Geographic Distance & Travel Time Calculator

A lightweight Python CLI tool and helper module that computes the geodesic distance (in kilometers) between two latitude/longitude coordinates and estimates travel time from an average speed.

## Features

- **Accurate Geodesic Distance:** Uses `geopy.distance.geodesic` (WGS-84 ellipsoid model) rather than flat-earth approximations.
- **Travel Time Estimation:** Calculates estimated travel duration in hours from your specified average speed (`km/h`).
- **Input Validation:** Validates latitude (`-90` to `90`), longitude (`-180` to `180`), numeric parsing, and positive speed values.
- **Unit Tested:** Includes a `pytest` suite covering distance calculation, interactive CLI flows, and invalid input handling.

## Project Structure

```text
.
├── geographic_distance.py       # Core distance/time calculation and interactive CLI
├── test_geographic_distance.py  # Pytest unit tests
├── requirements.txt             # Python dependencies
├── runtime.txt                  # Target Python runtime version
└── README.md
```

## Prerequisites

- Python 3.11+ (target runtime in `runtime.txt`: `python-3.12.7`)

## Setup

1. Clone this repository and enter the project directory:

   ```bash
   git clone https://github.com/sisodiaumang/geoDistanceCalci.git
   cd geoDistanceCalci
   ```

2. Create and activate a virtual environment:

   - **Windows (PowerShell):**

     ```powershell
     python -m venv venv
     .\venv\Scripts\Activate.ps1
     ```

   - **macOS / Linux:**

     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```

3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Interactive CLI

Run the script:

```bash
python geographic_distance.py
```

Example session:

```text
Enter the latitude and longitude of the first location (lat1, lon1) Example: 40.7128, -74.006: 52.5200, 13.4050
Enter the latitude and longitude of the second location (lat2, lon2) Example: 37.7749, -122.4194: 48.8566, 2.3522
Enter the average speed in km/h Example: 60: 80
Distance between the two coordinates: 879.70 kilometers
Estimated travel time: 11.00 hours
```

### As a Python Module

```python
from geographic_distance import calculate_distance_and_time

distance_km, hours = calculate_distance_and_time((40.7128, -74.006), (37.7749, -122.4194), 80)
print(f"{distance_km:.2f} km, {hours:.2f} hours")
```

## Running Tests

```bash
pytest -v
```

## Dependencies

Defined in [requirements.txt](requirements.txt):

- `geopy==2.4.1`
- `pytest==8.3.3`

## Acknowledgments

Originally adapted from [All-In-One-Python-Projects](https://github.com/king04aman/All-In-One-Python-Projects).
