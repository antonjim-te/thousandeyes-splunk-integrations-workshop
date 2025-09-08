# ThousandEyes - Splunk Integrations Workshop 

All the docs in: https://antonjim-te.github.io/thousandeyes-splunk-integrations-workshop


# TODO
- Document the ThousandEyes permissions 
- Add traces to Splunk App
- Add ThousandEyes alerts into Splunk (using Splunk App)
- Activity log
    - In the Splunk App - Activity log dashboard -> add resource column
    - update the steps to use the new input


# Run it locally
```
python3 -m venv .venv 
source .venv/bin/activate
python3 -m pip install -r requirements.txt
python3 -m mkdocs serve
```