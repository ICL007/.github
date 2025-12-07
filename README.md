https://github.com/ICL007/.githubname: Context testing
on: push

jobs:
  dump_contexts_to_log:
    runs-on: ubuntu-latest
    steps:
      - name: Dump GitHub context
        env:
          GITHUB_CONTEXT: ${{ toJson(github) }}
        run: echo "$GITHUB_CONTEXT"
      - name: Dump job context
        env:
          JOB_CONTEXT: ${{ toJson(job) }}
        run: echo "$JOB_CONTEXT"
      - name: Dump steps context
        env:
          STEPS_CONTEXT: ${{ toJson(steps) }}
        run: echo "$STEPS_CONTEXT"
      - name: Dump runner context
        env:
          RUNNER_CONTEXT: ${{ toJson(runner) }}
        run: echo "$RUNNER_CONTEXT"
      - name: Dump strategy context
        env:
          STRATEGY_CONTEXT: ${{ toJson(strategy) }}
        run: echo "$STRATEGY_CONTEXT"
      - name: Dump matrix context
        env:
          MATRIX_CONTEXT: ${{ toJson(matrix) }}
        run: echo "$MATRIX_CONTEXT"
name: example-workflow
on: [push]
jobs:
  production-deploy:
    if: ${{ github.repository == 'octo-org/octo-repo-prod' }}
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v5
      - uses: actions/setup-node@v4
        with:
          node-version: '14'
      - run: npm install -g bats
github.repositoryhttps://api.openweathermap.org/data/2.5/weather?q=${encodeURIComponentimport React, { useState } from "react";

const API_KEY = "YOUR_OPENWEATHERMAP_API_KEY"; // Replace this with your key

export default function WeatherDashboard() {
  const [city, setCity] = useState("");
  const [weather, setWeather] = useState(null);
  const [error, setError] = useState("");

  const fetchWeather = async () => {
    setError("");
    setWeather(null);
    try {
      const res = await fetch(
        `https://api.openweathermap.org/data/2.5/weather?q=${encodeURIComponent(
          city
        )}&units=metric&appid=${API_KEY}`
      );
      if (!res.ok) {
        setError("City not found");
        return;
      }
      const data = await res.json();
      setWeather(data);
    } catch (err) {
      setError("Failed to fetch weather data.");
    }
  };

  return (
    <div style={{ maxWidth: 400, margin: "2rem auto", padding: 20, borderRadius: 8, boxShadow: "0 2px 8px #ccc" }}>
      <h2>Weather Dashboard</h2>
      <input
        type="text"
        placeholder="Enter a city"
        value={city}
        onChange={(e) => setCity(e.target.value)}
        style={{ width: "70%", padding: 8, marginRight: 8 }}
      />
      <button onClick={fetchWeather}>Get Weather</button>
      <div style={{ marginTop: 20 }}>
        {error && <div style={{ color: "red" }}>{error}</div>}
        {weather && (
          <div>
            <h3>
              {weather.name}, {weather.sys.country}
            </h3>
            <p>
              <b>Temperature:</b> {weather.main.temp} °C
            </p>
            <p>
              <b>Humidity:</b> {weather.main.humidity}%
            </p>
            <p>
              <b>Weather:</b> {weather.weather[0].main} - {weather.weather[0].description}
            </p>
            <img
              src={`https://openweathermap.org/img/wn/${weather.weather[0].icon}@2x.png`}
              alt={weather.weather[0].description}
            />
          </div>
        )}
      </div>
    </div>
  );
}20weather.name8weather.sys.countryhttps://openweathermap.org/img/wn/${weather.weatherGitHub Actions ( review-comment.yml) – dùng để tự động bình luận hướng dẫn đánh giá các Pull Yêu cầu trong kho github/docshoặc github/docs-internal.# .github