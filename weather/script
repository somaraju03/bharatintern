document.addEventListener('DOMContentLoaded', () => {
    const fetchWeatherBtn = document.getElementById('fetchWeatherBtn');
    const cityInput = document.getElementById('cityInput');
    const weatherInfo = document.getElementById('weatherInfo');
  
    fetchWeatherBtn.addEventListener('click', async () => {
      const city = cityInput.value.trim();
      if (city === '') {
        alert('Please enter a city name.');
        return;
      }
  
      const apiKey ='964336f3c500721ffa63944d281c38a6'; // Replace with your API key
      const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=${city},IN&appid=${apiKey}&units=metric`;
  
      try {
        const response = await fetch(apiUrl);
        const data = await response.json();
  
        if (data.cod === '404') {
          alert('City not found. Please enter a valid city name in India.');
          return;
        }
  
        const { name, main, weather } = data;
        const { temp, humidity } = main;
        const weatherDescription = weather[0].description;
  
        weatherInfo.innerHTML = `
          <h2>${name} Weather</h2>
          <p>Temperature: ${temp}°C</p>
          <p>Description: ${weatherDescription}</p>
          <p>Humidity: ${humidity}%</p>
        `;
      } catch (error) {
        console.error('Error fetching weather data:', error);
        alert('An error occurred while fetching weather data. Please try again later.');
      }
    });
  });
  
  
