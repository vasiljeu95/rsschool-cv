# junior iOS developer CV

### 1. Stepan Vasilyeu

### 2. Contact Info: vasilyeu95@gmail.com

### 3. Summary:

I am a purposeful and motivated person, having a great desire to learn and progress in the field, who can adjust quickly to new surroundings. 
My qualities such as sociability, flexibility and reliability make me good at teamwork.

### 4. Skills:

- Swift programming language
- Apple’s Xcode IDE
- Foundation, UIKit.
- Apple Human Interface Guidelines
- OOP, SOLID
- MVC
- ARC
- Git code repository technology
- Worked with Google API, used maps and blog;
- Swift Core Data

### 5. Code examples:

Code snippet from the "Weathers" app"

```swift
func getTemp(city: String) {
        let jsonUrl = "https://api.openweathermap.org/data/2.5/weather?q=" + city + "&appid=4d24cbf9d70b0c3cedc62cc36c70ec13"
        guard let url = URL(string: jsonUrl) else { return }
        
        URLSession.shared.dataTask(with: url) { (data, _, _) in
            guard let data = data else { return }
            
            do {
                let weatherProperty = try JSONDecoder().decode(WeatherProperty.self, from: data)
                DispatchQueue.main.async {
                    
                    let tempCelsius = fahrenheitInCelsius(fahrenheitTemp: (weatherProperty.main!.temp ?? 0))
                    let pressure = weatherProperty.main!.pressure ?? 0
                    let humidity = weatherProperty.main!.humidity ?? 0
                    let windSpeed = weatherProperty.wind!.speed ?? 0
                    let cloudiness = weatherProperty.clouds!.all ?? 0
                    let perceivedTemperature = windColdIndex(tempAir: tempCelsius, speedWind: windSpeed)
                    let cloudImageView = weatherProperty.weather![0].icon
                        
                    self.cityNameLabel.text = weatherProperty.name
                    self.weathersLabel.text = weatherProperty.weather![0].weatherDescription
                    self.temperatureCityLabel.text = ("\(NSString(format:"%.f", tempCelsius)) °")
                    self.perceivedTemperatureLabel.text = ("feels like: \(NSString(format:"%.f", perceivedTemperature)) °")
                    self.pressureLabel.text = ("pressure: \(NSString(format:"%.f", pressure)) hPa")
                    self.humidityLabel.text = ("humidity: \(NSString(format:"%.f", humidity)) %")
                    self.windSpeedLabel.text = ("wind: \(NSString(format:"%.f", windSpeed)) m/s")
                    self.cloudinessLabel.text = ("cloud: \(NSString(format:"%.f", cloudiness)) %")
                    self.cloudImageView.image = UIImage(named: cloudImageView ?? "sun")
                    
                    self.view.reloadInputViews()
                }
            } catch {
                print(error.localizedDescription)
            }
        }.resume()
    }
```

### 6. Experience:

* November 2019-November 2019  – Junior iOS developer. SwiftBook online webinar courses.
Project role: Team Lead, iOS developer.
Project description: application for learning English (in the development stage) - https://github.com/vasiljeu95/EnglishTestApp

* June 2019-Jule2019 – Junior iOS developer. ALOTEQ

* August 2019-present  – Area Head, Minsk Automobile Plant
Main responsibilities: monitoring of working capacity of mechanical and power equipment of production.

