ATMOS AI — Color & Weather Analyzer

RUN LOCALLY (recommended):
1. Extract this ZIP.
2. Open a terminal in the extracted color_weather_ai_frontend folder.
3. Run: python -m http.server 8000
4. Open http://localhost:8000

The index.html and tfjs_model folder must remain together. The model uses TensorFlow.js from a CDN, so internet is needed on first load for the library. Camera access generally requires localhost or HTTPS. Select Photo to upload/drop an image, or Camera > Start camera for live predictions. Live analysis is throttled to about once every 1.3 seconds to reduce device load.

Model outputs: 11 color percentages, brightness (dark/medium/bright), color temperature (cool/neutral/warm), weather class (cloudy/foggy/other/rainy/shine/sunrise).
