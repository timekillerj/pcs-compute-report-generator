# pcs-compute-report-generator
This project creates HTML or PDF reports for Vulnerability and Compliance data pulled from a Prisma Cloud Compute (formerly Twistlock) instance.

## Setup
First clone this repo:

```
git clone https://github.com/timekillerj/pcs-compute-report-generator.git
```

It is recommended you create a virtual environment to keep installed python packages isolated from the rest of your system:

```
cd pcs-compute-report-generator
python3 -m venv venv
```
Activate it:

```
source venv/bin/activate
```

Next you will need to install the required python packages:

```
pip install -r requirements.txt
```

Finally, you will need to install [wkhtmltopdf](https://wkhtmltopdf.org/downloads.html) for your platform.

## Environment Variables
To fun reports with this script you will need 3 environment variables:

| Environment Variable | Description                               |
|----------------------|-------------------------------------------|
| COMPUTE_API_ENDPOINT | The api endpoint of your Compute instance |
| COMPUTE_ACCESS_KEY   | Your username for the instance            |
| COMPUTE_SECRET_KEY   | Your password                             |

## Usage
```

Console, Console and Password will read from the following environment variables. 
COMPUTE_API_ENDPOINT in the form https://<console-address>
COMPUTE_ACCESS_KEY
COMPUTE_SECRET_KEY


usage: create_report.py [-h] [-t {deployed,registry,ci}] [-f {pdf,html}] [-d] [-s] [-vo] [-co]

Create Compute Reports

optional arguments:
  -h, --help                                                show this help message and exit
  -t {deployed,registry,ci}, --type {deployed,registry,ci}  Used to select the type of report to run.
  -f {pdf,html}, --format {pdf,html}                        Selects the file format of the generated report.
  -d, --debug                                               Prints debug output during report creation
  -s, --summary                                             Summary only, do not include vulnerability or compliance details
  -vo, --vulnerabilities-only                               Exclude Compliance data from report
  -co, --compliance-only                                    Exclude Vulnerabilities data from report
```