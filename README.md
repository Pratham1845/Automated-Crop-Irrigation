# AgriFlow — Automated Crop Irrigation Using Weather Forecasting

AgriFlow is a browser-only, responsive smart-agriculture dashboard for an interdisciplinary BCA + MBA project. It combines simulated soil readings, a forecast-aware irrigation decision engine, historical records, cost modelling and responsible agricultural-input guidance.

## Project structure

```text
automated-crop-irrigation/
├── index.html    # Semantic dashboard sections and accessible controls
├── style.css     # Responsive visual system, cards, charts and layout
├── script.js     # Navigation, simulation logic, Chart.js, API and localStorage
└── README.md
```

## Run in VS Code with Live Server

1. Install [Visual Studio Code](https://code.visualstudio.com/).
2. Open VS Code, choose **File > Open Folder**, and select the `automated-crop-irrigation` folder.
3. Install the **Live Server** extension by Ritwick Dey from the Extensions panel. (It is free and does not require a project build step.)
4. Open `index.html`, right-click inside the editor, and choose **Open with Live Server**.
5. Your browser will open a local address such as `http://127.0.0.1:5500/index.html`.

The page uses Chart.js and Google Fonts from CDNs. An internet connection is recommended for charts and fonts; the rest of the demo works locally.

## Configure OpenWeather

Open `script.js` and set the clearly marked configuration variable:

```js
const CONFIG = {
  OPENWEATHER_API_KEY: 'your-openweather-api-key',
  API_BASE: 'https://api.openweathermap.org/data/2.5'
};
```

The default empty value intentionally uses realistic labelled demonstration data, so the project works without credentials. A frontend API key is visible to every browser user and should not be treated as a secret. Use an appropriately restricted key and follow OpenWeather’s current plan and terms. The current-weather endpoint is used for the live lookup; the five-day cards remain demonstration cards unless you extend the forecast mapping.

## Test checklist

- Click every sidebar item and confirm the active section and breadcrumb change.
- On Dashboard, verify metric cards, charts, recent activity and the demonstration notice.
- On Weather forecast, search with an empty location, a normal location, and (if configured) an invalid API key. Confirm validation, loading, error and fallback messaging.
- On Irrigation control, move moisture/rain/threshold sliders and verify the recommendation reason changes. Test automatic/manual mode, simulated ON/OFF, timer, and Emergency STOP interlock.
- On Crop management, change the crop, edit its threshold, save, refresh, and confirm local settings persist.
- On Historical data, export CSV, refresh the page, and clear records after confirming the browser dialog.
- On Business analysis, edit each estimate and confirm total cost, profit, margin and the margin bar update.
- On Input guidance, try saving empty fields, then save an observation and refresh.
- Resize the browser to desktop, tablet and mobile widths; open the mobile menu and check that controls remain usable.

All readings and financial values are labelled as demonstrations or user-entered estimates. Manual controls change only simulated browser state and never claim to operate a real pump.
