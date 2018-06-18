# サンプル

JavaScript を使用したいくつかのサンプルを紹介します．

### 天気予報を取得する

[OpenWeatherMap](https://openweathermap.org/) を使用して天気予報を取得する．

```javascript
const BASE_URL = 'http://api.openweathermap.org/data/2.5/weather'
const API_KEY = 'YOUR_API_KEY' // OpenWeatherMap で API キーを取得する

// 天気予報を取得する関数
function getWeatherForecast(latitude, longitude){
  const endpoint = BASE_URL + '?lat=' + latitude + '&lon=' + longitude + '&APPID=' + API_KEY

  function onError(error){
    alert(error.message)
  }

  function showWeatherForecast(data){
    alert(data.weather[0].description)
  }

  // OpenWeatherMap から天気予報を取得する
  fetch(endpoint)
    .catch(onError)
    .then(response => response.json()) // 取得したデータはテキストであるため JSON に変換する
    .then(showWeatherForecast)
}

// 現在位置が取得できた際に呼ばれる関数
function getCurrentPositionOnSuccess(position){
  const latitude = position.coords.latitude // 緯度
  const longitude = position.coords.longitude // 経度

  // 天気予報を取得する
  getWeatherForecast(latitude, longitude)
}

// 現在位置が取得に失敗した際に呼ばれる関数
function getCurrentPositionOnError(error){
  alert(error.message)
}

// 現在位置を取得する
navigator.geolocation.getCurrentPosition(getCurrentPositionOnSuccess, getCurrentPositionOnError)
```
