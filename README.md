# ERA5-Land Data Downloader

This repository contains a Python-based tool designed to efficiently download ERA5-Land reanalysis data from the Climate Data Store (CDS) using the CDS API. The script, `Era_Downld_enhanced-V3.ipynb`, offers enhanced features such as concurrent downloading, robust error handling, and detailed logging, making it a reliable and efficient solution for managing large-scale climate data downloads.

## Features

- **Concurrent Downloading**: The script uses Python's `concurrent.futures` to handle multiple download tasks in parallel, significantly reducing the total download time.
- **Robust Error Handling**: Implements a retry mechanism with logging to handle download failures due to network issues or server errors.
- **Customizable**: Users can specify the time period (year, month, day, hour) for which data is required, as well as the geographic area and the variables of interest.
- **Detailed Logging**: Logs each download attempt, including successes and failures, allowing users to track the progress and troubleshoot issues.

## Prerequisites

Before running the script, ensure you have the following installed:

- **Python 3.x**
- **cdsapi library**: This library is required to interact with the CDS API.
  ```bash
  pip install cdsapi
Setting Up the .cdsapirc File
To authenticate with the CDS API, you need to create a .cdsapirc file in your home directory. This file should contain your API credentials, which can be obtained from the CDS website.

Steps to Create the .cdsapirc File:
Register or Log In to Your CDS Account:

Go to the CDS login page.
If you don't have an account, create one.
Get Your API Key:

After logging in, visit the API key page.
Copy the API key provided.
Create the .cdsapirc File:

In your home directory, create a file named .cdsapirc and paste the following:
plaintext
Copiar código
url: https://cds.climate.copernicus.eu/api/v2
key: <UID>:<API_KEY>
Replace <UID> and <API_KEY> with the values provided by the CDS.
Usage Instructions
1. Clone the Repository
First, clone the repository to your local machine:

bash
Copiar código
git clone https://github.com/JuanCrls17/ERA5-Land-Data-Downloader.git
cd ERA5-Land-Data-Downloader
2. Customize the Script
Before running the script, you may want to customize the time period and geographic area for which you wish to download data. Open the script and adjust the following variables as needed:

years: List of years you want to download data for (e.g., [2008]).
months: List of months you want to download data for (e.g., [1]).
area: Geographic bounding box defined as [north, west, south, east].
variables: List of variables to be downloaded (e.g., ['10m_u_component_of_wind', '2m_temperature']).
3. Run the Script
Once customized, you can run the script:

bash
Copiar código
python Era_Downld_enhanced-V3.ipynb
4. Monitor the Logs
The script generates two log files:

last_download.txt: Logs the last successfully downloaded file.
all_logs.txt: Logs all download attempts, including errors.
These logs are essential for tracking the download process and diagnosing any issues.

Example Configuration
Below is an example configuration that you might use within the script:

python
Copiar código
years = [2008]
months = [1]
days = range(1, 32)
hours = range(24)

area = [-10, -77, -12, -75]  # Specify the geographic area
variables = [
    '10m_u_component_of_wind', '10m_v_component_of_wind', '2m_dewpoint_temperature',
    '2m_temperature', 'surface_pressure', 'surface_solar_radiation_downwards',
    'surface_thermal_radiation_downwards', 'total_precipitation',
]
Important Notes
API Rate Limits: The CDS API has usage limits. Excessive requests or continuous retries may result in temporary blocking of your IP. Always monitor your API usage.
Keep Your Environment Up to Date: Regularly update your Python environment and the cdsapi library to avoid potential issues with API requests.
External Resources
For more detailed information about the ERA5-Land reanalysis data and the Climate Data Store, visit the following links:

CDS API Documentation
ERA5-Land Overview
License
This project is licensed under the MIT License. See the LICENSE file for details.

Contributing
Contributions are welcome! If you have suggestions or improvements, feel free to submit a pull request or open an issue.

Acknowledgments
ECMWF: For providing the ERA5-Land reanalysis dataset.
Copernicus Climate Change Service: For their support and data services.
markdown
Copiar código

### Explanation of Each Section:

1. **Features**: Lists the key capabilities of your script, emphasizing its advanced functionality.
2. **Prerequisites**: Details the necessary software dependencies.
3. **Setting Up the `.cdsapirc` File**: Guides users on how to authenticate with the CDS API.
4. **Usage Instructions**: Provides a step-by-step guide on how to clone the repository, customize the script, and run it.
5. **Example Configuration**: Gives users a ready-made example configuration they can quickly adapt.
6. **Important Notes**: Alerts users to potential issues, such as API rate limits, and advises on keeping their environment up to date.
7. **External Resources**: Links to additional information that users might find useful.
8. **License**: Mentions the licensing under which your code is released.
9. **Contributing**: Invites others to contribute to the project.
10. **Acknowledgments**: Credits the organizations and services that provided data and support.

This `README.md` provides a professional and comprehensive overview of your project, en
