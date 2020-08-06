# mockjson
##16 Day Weather Forecast API (1 day interval)
This API returns a 16 day forecast in 1 day intervals from any point on the planet.

All parameters should be supplied to the Weather API as query string parameters.

Base URL
HTTP: http://api.weatherbit.io/v2.0/forecast/daily
HTTPS: https://api.weatherbit.io/v2.0/forecast/daily
Supported Methods: GET
Request Parameters
key=[key] (REQUIRED)
key - Your API Key.
lang=[language](optional)
en - [DEFAULT] English
ar - Arabic
az - Azerbaijani
be - Belarusian
bg - Bulgarian
bs - Bosnian
ca - Catalan
cz - Czech
da - Danish
de - German
fi - Finnish
fr - French
el - Greek
es - Spanish
et - Estonian
hr - Croation
hu - Hungarian
id - Indonesian
it - Italian
is - Icelandic
iw - Hebrew
kw - Cornish
lt - Lithuanian
nb - Norwegian Bokmål
nl - Dutch
pl - Polish
pt - Portuguese
ro - Romanian
ru - Russian
sk - Slovak
sl - Slovenian
sr - Serbian
sv - Swedish
tr - Turkish
uk - Ukrainian
zh - Chinese (Simplified)
zh-tw - Chinese (Traditional)
units=[units](optional)
M - [DEFAULT] Metric (Celcius, m/s, mm)
S - Scientific (Kelvin, m/s, mm)
I - Fahrenheit (F, mph, in)
callback=[function] (optional: JSON-P callback)
days=[integer] (optional: return a specific number of forecast days)
16 - [DEFAULT] 16 days
API Endpoints
Description	Required Parameters	Example(s)
Get forecast by lat/lon	lat,lon	&lat=38.123&lon=-78.543
Get forecast by city name	city, state(optional), country (optional)	
&city=Raleigh&country=US
&city=Raleigh,NC
&city=Raleigh,North+Carolina
Get forecast by postal code	postal_code, country (optional)	&postal_code=27601&country=US
Get forecast by Station	station	
&station=KRDU
Get forecast by city id	city_id	&city_id=8953360
Example Request:
https://api.weatherbit.io/v2.0/forecast/daily?city=Raleigh,NC&key=API_KEY
Example Response (JSON):

          {  
             "data":[  
                {  
                  "valid_date":"2017-04-01",
                   "ts":1503954000,
                   "datetime":"2017-04-01",
                   "wind_gust_spd":16.7,
                   "wind_spd":6.4,
                   "wind_dir":45,
                   "wind_cdir":"NE",
                   "wind_cdir_full":"northeast",
                   "temp":25,
                   "max_temp":30,
                   "min_temp":26,
                   "high_temp":30,
                   "low_temp":24.5,
                   "app_max_temp":30.64,
                   "app_min_temp":23.64,
                   "pop":0,
                   "precip":0,
                   "snow":0,
                   "snow_depth":0,
                   "slp":1017,
                   "pres":1003.5,
                   "dewpt":17.8,
                   "rh":64.3,
                   "weather":{  
                      "icon":"c04d",
                      "code":"804",
                      "description":"Overcast clouds"
                   },
                   "pod":"d",
                   "clouds_low":25,
                   "clouds_mid":100,
                   "clouds_hi":50,
                   "clouds":100,
                   "vis":10,
                   "max_dhi":178,
                   "uv":2,
                   "moon_phase":0.99,
                   "moon_phase_lunation":0.48,
                   "moonrise_ts":1530341260,
                   "moonset_ts":1530351260,
                   "sunrise_ts":1530321260,
                   "sunset_ts":1530391260
                }, ...
             ],
             "city_name":"Raleigh",
             "lon":"-78.63861",
             "timezone":"America\/New_York",
             "lat":"35.7721",
             "country_code":"US",
             "state_code":"NC"
          }
        
## Field Decriptions:
- lat: Latitude (Degrees)
lon: Longitude (Degrees)
timezone: Local IANA Timezone
city_name: Nearest city name
country_code: Country abbreviation
state_code: State abbreviation/code
data: [
valid_date: Date the forecast is valid for in format YYYY-MM-DD [Midnight to midnight local time]
ts: Forecast period start unix timestamp (UTC)
datetime:[DEPRECATED] Forecast valid date (YYYY-MM-DD)
wind_gust_spd: Wind gust speed (Default m/s)
wind_spd: Wind speed (Default m/s)
wind_dir: Wind direction (degrees)
wind_cdir: Abbreviated wind direction
wind_cdir_full: Verbal wind direction
temp: Average Temperature (default Celcius)
max_temp: Maximum Temperature (default Celcius)
min_temp: Minimum Temperature (default Celcius)
high_temp: High Temperature - Calculated from 6AM to 6AM local time (default Celcius)
low_temp: Low Temperature - Calculated from 6AM to 6AM local (default Celcius)
app_max_temp: Apparent/"Feels Like" temperature at max_temp time (default Celcius)
app_min_temp: Apparent/"Feels Like" temperature at min_temp time (default Celcius)
pop: Probability of Precipitation (%)
precip: Accumulated liquid equivalent precipitation (default mm)
snow: Accumulated snowfall (default mm)
snow_depth: Snow Depth (default mm)
pres: Average pressure (mb)
slp: Average sea level pressure (mb)
dewpt: Average dew point (default Celcius)
rh: Average relative humidity (%)
weather: {
icon:Weather icon code
code:Weather code
description: Text weather description
}
pod: Part of the day (d = day / n = night)
clouds_low: Low-level (~0-3km AGL) cloud coverage (%)
clouds_mid: Mid-level (~3-5km AGL) cloud coverage (%)
clouds_hi: High-level (>5km AGL) cloud coverage (%)
clouds: Average total cloud coverage (%)
vis: Visibility (default KM)
max_dhi: [DEPRECATED] Maximum direct component of solar radiation (W/m^2)
uv: Maximum UV Index (0-11+)
ozone: Average Ozone (Dobson units)
moon_phase: Moon phase illumination fraction (0-1)
moon_phase_lunation: Moon lunation fraction (0 = New moon, 0.50 = Full Moon, 0.75 = Last quarter moon)
moonrise_ts: Moonrise time unix timestamp (UTC)
moonset_ts: Moonset time unix timestamp (UTC)
sunrise_ts: Sunrise time unix timestamp (UTC)
sunset_ts: Sunset time unix timestamp (UTC)
... ]
 to get false data for testing
