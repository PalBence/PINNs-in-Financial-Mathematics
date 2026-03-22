# PINNs in Financial Mathematics

This repository for using PINNs for estimating European option prices using the Black-Scholes formula contributes to the project titled "PINNs in Financial Mathematics", completed for the DNDS5018 - Mathematics for AI course. 

## Overall project structure

As stated in the project report:

1. Research and mini-literature review
2. Deciding the scope: option pricing
3. Beginning of work on the report
4. Implementation of a PINN for European options
5. Evaluation of results
6. Finishing of work on the report
7. Presentation preparation

This repository belongs to step 4 of the project.

## Setup

### Using uv
The project is managed with [uv](https://github.com/astral-sh/uv). You will need to install it first. 
Either using its standalone installer:

Using pip:
```bash
pip install uv
```

To install packages (instead of `pip install PACKAGE_NAME`) run:
```bash
uv add PACKAGE_NAME

# For example:
uv add requests
```


### Project setup

1. Create your environment file:
   ```bash
   cp .env.example .env
   ```
   
2. Fill in your API keys inside .env (never commit this file).
   
3. Install dependencies:
   ```bash
   uv sync
   ```
4. Run the project (once implemented)
   ```bash
   uv run python main.py
   ```
   or, to run a specific file with all its dependencies (e.g. `models/calibrate_model.py`, assuming it exists), do
   ```bash
   uv run python -m models.calibrate_model
   ```

   Note, that `uv run` already executes commands in a virtual environment, so there's no need to manually create and activate virtual environments.

## Data

Options data for this project was pulled through the LSEG Refinitiv API. 

### LSEG Setup (MacOS)

1. Generate an API key in the Refinitiv Workspace App

2. Install the corresponding Python package (managed with uv)

3. Create a folder (if not automatically created) your /user folder called .lseg

4. Create an `lseg-data.config.json` file with the following data:

```
  {
    "default": "workspace",
    "sessions": {
      "workspace": {
        "type": "desktop",
        "app_key": "YOUR_API_KEY"
      }
    }
  }
```
