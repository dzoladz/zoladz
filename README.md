Some preliminary documentation on setting up reports for the Consortium of Ohio Libraries

#### Setting Up COOL Automated Reporting
- Python3 will be used for scripting
- Utility server IP needs to be added for Sequoia DB access

#### Requests
- Add all cron jobs to `/etc/cron.d`

#### Using Virtual Environments
- Virtual Environments [virtualenv docs](http://docs.python-guide.org/en/latest/dev/virtualenvs/)

```bash
virtualenv -p /usr/bin/python3 project_name
```