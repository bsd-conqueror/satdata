# SatData - a Python library for fetching space weather datasets

SatData has a machine-learning-ready unified API that allows you to fetch all
public available space weather datasets of a data center via its provided
driver.
Currently, only one driver by the Space Monitoring Data Center (SMDC -
http://smdc.sinp.msu.ru) of SINP MSU is
provided.

If you're interested in using SatData in your work, please send me an e-mail to
nguyendmitri@gmail.com.

# Examples

## To use the SMDC driver

* create a file called smdc_config.json
* put it to the same folder where smdc.py is located
* add the following authorization credentials to smdc_config.json
```
{
  "username": "your SMDC username",
  "password": "you SMDC password"
}
```
* to fetch data of the das3vrt1 channel of the SKL instrument of the Electro-L2 satellite
```Python
from satdata import providers
smdc = providers.smdc()
smdc.authorize()
df = smdc.fetch(source='electro_l2',
                instrument='skl',
                channel='das3vrt1',
                start_dt='2017-10-14 10:43:38',
                end_dt='2017-10-14 10:43:47',
                time_frame='1s',
                level='default')
```

