# SHIIELD - AI Based Industrial Fire Detection / Classification

### Smart India Hackathon 2026 - Team Devignite

Problem Statement ID: SIH26162
Theme: Disaster Management
Category: Software

SHIIELD is an AI driven idea to detect thermal anomalies and classify their probable source, using NASA FIRMS, OpenStreetMap (OSM), satellite images, history of observations and machine learning.

We intend to provide assistance in identifying potential industrial fire locations, and differentiate between persistent sources of heat and incidents of fire.
---

## Problem Statement

The problem with satellite fire observation systems is that while these can identify the location of a thermal anomaly,
determining what the source of that fire might be is a more complex proposition.

Industrial installations, factories, power plants, mines, gas flares or any number of other industrial installations can be sources of intense heat.

SHIIELD aims to use a combination of satellite observations, infrastructure mapping data, land cover analysis, historical observations and AI to provide a context for a given thermal event.
---

## Our Proposed Solution

SHIIELD aims to use a combination of satellite data, geographical and land use information as well as machine learning to provide a classification for observed thermal anomalies.

## How it Works

1. Thermal Hotspot Detection - NASA FIRMS provides satellite based fire observations
2. Infrastructure mapping - OpenStreetMap identifies potential industrial infrastructure in the area of an observed fire

3. Satellite analysis - Sentinel-2 and Landsat 8/9 provide additional data about land use and thermal signatures for further analysis
4. Historical analysis - Past observations are used to determine if there is a known pattern of thermal activity

5. AI/ML Classification - Random Forest and XGBoost tree based classifiers classify observations based on available data
6. Monitoring dashboard - A dashboard provides a map based view of observed events and their potential sources
---
## Features

- Satellite monitored fire detection (NASA FIRMS)
- Industrial infrastructure detection using OpenStreetMap
- AI/ML classification of thermal anomaly sources (Random Forest, XGBoost)
- Map based interactive dashboard (Leaflet)

- Historical event analysis and comparison
- Prioritization of events using classification confidence
- Cloud based deployment (Docker, AWS)
---
## Tech Stack
| Component | Technologies Used |
| Frontend | React |
| Backend | Python, FastAPI |
| Geospatial DB | PostgreSQL, PostGIS |
| Database ORM | SQLModel |
| Maps / Dashboard | Leaflet |
| ML Models | Random Forest, XGBoost |
| ML Serialization | Joblib / Pickle |
| Data Pipelines | HTTP clients, satellite and geospatial data sources |
| Containerization | Docker |
| Cloud Platform | AWS |
---

## Sources of Data
### 1. NASA FIRMS
https://firms.modaps.eosdis.nasa.gov/
Provides satellite observations of fire activity.
### 2. OpenStreetMap (OSM)
https://www.openstreetmap.org/
Provides mapping data to determine industrial infrastructure and geographical features.
### 3. Copernicus Sentinel-2
https://dataspace.copernicus.eu/
Provides satellite imagery for land use analysis.
### 4. USGS Landsat 8/9
https://earthexplorer.usgs.gov/
Provides satellite imagery for land use analysis and thermal analysis.
Note: All data sources have different spatial resolution, revisit time and other characteristics, and are applicable to different types of events.
---
## ML Approach
SHIIELD proposes the use of a machine learning based approach to classify observations into categories.
### Possible ML Models
1. Random Forest
2. XGBoost
Features:
1. Location of thermal anomaly and characteristics of the detection method used
2. Recurrence of similar thermal anomalies
3. Distance from known industrial infrastructure
4. Land use characteristics of the area
5. Additional satellite observations of the area
Output:

Depending on the features provided and the model used, SHIIELD will attempt to provide the following
1. Classification that the event belongs to (e.g. industrial fire, gas flare, hot steam etc.)
2. Contextual information about the location
3. Recurrence information (if any)
4. Confidence value for the classification
5. Further information that may help with the investigation
Note: Classifications are intended as potential sources of a fire, and do not constitute evidence.
---
## Architecture
```text
NASA FIRMS
|
v
Thermal Hotspots
|
v
Data Collection Layer
|
+------------------+
|         |
v         v
OpenStreetMap    Satellite Data
Sentinel-2
Landsat 8/9
|         |
+--------+---------+
|
v
Data Processing Layer
|
v
Feature Extraction and
Historical Analysis
|
v
AI/ML Classification
Random Forest / XGBoost
|
v
PostgreSQL + PostGIS
|
v
FastAPI Backend
|
v
React Dashboard
|
v
Interactive Map and
Thermal Event Insights
```
---
## Feasibility / Viability
SHIIELD aims to use freely available satellite observation sources and open technologies.
### Potential Challenges and Mitigation
| Challenge | Mitigation Strategy |
|---|---|
| False positive observations | Use multiple sources of information and confidence values |
| Observation of repeated thermal sources | Use historical observations |
| Rapid changes in intensity of gas flares | Analyze all available observations |
| Discriminate between hot steam and fire | Use contextual and multiple classification approaches |
| Incompleteness or delays in observations | Consider potential sources of error and missing data |
---
## Impact
SHIIELD aims to
- Provide better context for fire observations from satellites
- Help in investigation of potential fire incidents
- Reduce false positives using multiple sources of information
- Determine if an observed fire might be a recurring phenomenon
- Assist with disaster management and safety functions
- Provide an extensible and scalable solution
---
## Getting Started
The following instructions describe the intended approach to setup a development environment. These might change as the codebase evolves
### Prerequisites
1. Python
2. Node.js / npm
3. PostgreSQL
4. PostGIS (for PostgreSQL)
5. Git
6. Docker (optional for deployment)
### 1. Clone Repository
```bash
git clone
cd
```
Replace the placeholder with the actual repository URL and folder name.
### 2. Configuration Backend
Enter the backend directory, setup a Python virtual environment and install Python dependencies from the requirements.txt (available later).
```bash
python -m venv venv
```
Activate the environment (Linux/macOS):
```bash
source venv/bin/activate
```
Activate the environment (Windows):
```powershell
venv\Scripts\activate
```
Install dependencies:
```bash
pip install -r requirements.txt
```
Finally launch the FastAPI backend application (this command may vary):
```bash
uvicorn :app --reload
```
Replace `` with the actual module name of your FastAPI application.
### 3. Configuration Frontend
```bash
cd
npm install
npm run dev
```
Replace `` with the actual folder name of your React application.
### 4. Configuration Database
Create a PostgreSQL database and setup PostGIS (if needed):
```sql
CREATE DATABASE shiield_db;
```
```sql
CREATE EXTENSION IF NOT EXISTS postgis;
```
Setup environment variables and configure connections to data sources.
Security Note: Keep API keys, database passwords and other secrets in environment variables. Do not commit environment variables or configuration files to GitHub.
---
## R&D
This project involves research and exploration of the following areas:
- NASA FIRMS, MODIS, and VIIRS fire products
- OpenStreetMap infrastructure extraction
- Sentinel-2 land use / land cover classification
- Landsat thermal bands and surface temperature analysis
- Machine learning classification techniques
- Multi-source data fusion and geospatial system design
The actual accuracy and performance of the project will depend on the implementation and the data used for training and testing.
---
## References
1. NASA FIRMS - Fire Information for Resource Management System
https://firms.modaps.eosdis.nasa.gov/
2. OpenStreetMap - Open geospatial data
https://www.openstreetmap.org/
3. Copernicus Data Space Ecosystem - Sentinel satellite data
https://dataspace.copernicus.eu/
4. USGS EarthExplorer - Landsat satellite data
https://earthexplorer.usgs.gov/
5. Giglio, L. et al. (2016). Collection 6 MODIS active fire detection algorithm and fire products. Remote Sensing of Environment, 178, 31–41.
6. Bhattacharya, A. et al. (2022). Machine learning for wildfire detection using satellite imagery: A review. Remote Sensing Applications: Society and Environment, 26, 100754.
---
## Team
Team Name: Devignite
Project Name: SHIIELD
Event: Smart India Hackathon 2026
Problem Statement ID: SIH26162
Theme: Disaster Management
---
## Future Scope
- Additional satellite data sources
- Historical tracking of fire events
- Model validation and testing on actual data
- Anomaly detection and confidence scoring
- Alert system and notification system
- Role based access control
- Cloud deployment and performance optimization
---
## Project Status
SHIIELD is a work in progress - an AI based industrial fire detection and classification system. Features, technology stack, model performance and deployment will depend on the current state of implementation.
---

## License

License not specified. Add an open source license before publishing.
---

SHIIELD - Smarter Thermal Monitoring for Safer Industries. 🔥🛰️
