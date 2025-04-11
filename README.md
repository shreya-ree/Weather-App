# Weather App

A sleek and modern weather application built with Jetpack Compose for Android that allows users to check current weather conditions for any city.

## User Interface

<p align="center">
  <img src="Weather%20App%20Screenshot1.png" alt="Dark Mode" width="250"/>
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="Weather%20App%20Screenshot%202.png" alt="Light Mode" width="250"/>
</p>



## Features

- Clean and intuitive UI built with Jetpack Compose
- Real-time weather information retrieval
- Display of key weather data:
  - Current temperature
  - Humidity levels
  - Weather conditions description
  - City name confirmation
- Attractive weather-themed background design
- Simple city-based search functionality

## Technologies Used

- Kotlin
- Jetpack Compose for UI
- MVVM Architecture
- StateFlow for reactive UI updates
- Retrofit for API communication
- OpenWeatherMap API for weather data

## Project Structure

```
app/
├── src/
│   ├── main/
│   │   ├── java/com/example/theweatherapp/
│   │   │   ├── MainActivity.kt        # Main UI components and screen
│   │   │   ├── WeatherApi.kt          # Retrofit API interface
│   │   │   ├── WeatherResponse.kt     # Data models
│   │   │   ├── WeatherViewModel.kt    # ViewModel for weather data
│   │   │   └── ui/theme/              # UI theme definitions
│   │   ├── res/                       # Android resources
│   │   └── AndroidManifest.xml        # App configuration
│   ├── androidTest/                   # Instrumented tests
│   └── test/                          # Unit tests
└── build.gradle                       # Project build configuration
```

## Setup Instructions

### Prerequisites

- Android Studio Arctic Fox (2023.3.1) or higher
- JDK 11 or higher
- Android SDK 26+ (Android 8.0 Oreo)
- OpenWeatherMap API key (get one from [OpenWeatherMap](https://openweathermap.org/api))

### Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/theweatherapp.git
   ```

2. Open the project in Android Studio.

3. Sync the project with Gradle files.

4. Run the app on an emulator or physical device.

### API Key Configuration

The app uses a hardcoded API key for demonstration purposes. In a production environment, you should:

1. Create a `local.properties` file in the project root
2. Add your API key: `weather.apiKey=YOUR_API_KEY_HERE`
3. Configure the build.gradle to read from this file

## How It Works

The app follows the MVVM (Model-View-ViewModel) architecture:

- **View Layer**: Implemented with Jetpack Compose in `MainActivity.kt`. Contains the UI components that display the weather interface and handle user interactions.

- **ViewModel Layer**: The `WeatherViewModel.kt` manages the business logic and data retrieval.

- **Model Layer**: `WeatherResponse.kt` defines the data models used for storing weather information.

- **Network Layer**: `WeatherApi.kt` handles the communication with the OpenWeatherMap API using Retrofit.

- **Data Flow**:
  - User enters a city name and requests weather data
  - ViewModel calls the API through Retrofit
  - API response is processed and stored in StateFlow
  - UI observes the StateFlow and updates accordingly

## Permissions

The app requires the following permissions:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

## Acknowledgments

- [OpenWeatherMap API](https://openweathermap.org/) for providing weather data
- [Jetpack Compose Documentation](https://developer.android.com/jetpack/compose)
- [Retrofit](https://square.github.io/retrofit/) for API integration
