<img width="820" height="312" alt="4" src="https://github.com/user-attachments/assets/07643e03-faba-4ce5-bc06-b7be1a6732f8" />

## Project Brief
As we know in England, trains are plagued by delays and cancellations, the reliability of train services in England have been a significant concern. Data from the first half of 2025 revealed that 41% of train services were delayed by at least one minute and 3% were cancelled entirely. That's why we've created an app called Track Travel Disruptions. TTD aims to help commuters stay informed about their journey while only having to glance at the application. This app is especially useful for people who regularly utilise the same journey to commute to work, school or other destinations.

## Demo Video

https://github.com/user-attachments/assets/119ca79e-d609-4aa9-9f8d-8c4d60ffa8fd

## Learnings

- Android
- Recycler View
- Two-way data binding
- Custom activities with click handling
- .xml layout creation
- MVVM architecture
- Retrofit
- Interaction with an external API
  
## Screenshots

### Home Page with Recycler View
<img width="287" height="853" alt="Screenshot from 2025-07-30 23-05-16" src="https://github.com/user-attachments/assets/4ac8013e-22c2-4470-b3d6-004dbc8dbdb8" />

When there is no journeys in the database, a message prompt is displayed.

<img width="287" height="853" alt="Screenshot from 2025-07-30 23-07-04" src="https://github.com/user-attachments/assets/03ec311c-5b49-443f-af79-86dc8128bc74" />

Cards show journey details at a glance, three icons (No rail data avaliable, Service on time, Delays) specify the status of the service.


### Add a New Journey
<img width="287" height="853" alt="Screenshot from 2025-07-30 23-06-15" src="https://github.com/user-attachments/assets/a7c172ec-f81c-4306-9428-14bf5381a06e" />

A searchable spinner is used to search for the origin and destination stations and a universal time picker is used for time selection. Upon clicking `Next` the journey is sent to the TTD API however if the train journey does not exist a toast `Failed to add journey, Journey not valid` will be shown.

### Disruption page
<img width="287" height="853" alt="Screenshot from 2025-07-30 23-07-18" src="https://github.com/user-attachments/assets/6acb5928-1d67-4e30-b070-357277b741b2" /><img width="287" height="853" alt="Screenshot from 2025-07-30 23-07-35" src="https://github.com/user-attachments/assets/c68e3647-afbd-4824-9a42-ccd0880869dc" /><img width="287" height="853" alt="Screenshot from 2025-07-30 23-08-37" src="https://github.com/user-attachments/assets/eecce791-d772-4c7e-829a-835b10156896" />

The disruption page shows journey information in detail, giving the user information about the next train and any disruptions after their chosen departure time. The platform and service provider is also shown as well as a delay reason if any. 
>[!NOTE]
>The pending icon (No rail data avaliable) is shown if the departure time is not within 2 hrs of current time, as the API doesn't track status information outside that window.

### Edit Journey
<img width="287" height="853" alt="Screenshot from 2025-07-30 23-08-08" src="https://github.com/user-attachments/assets/74ef3fe9-d7fc-4be3-9b67-cc4ead767662" />

The user can edit the journey on this page by clicking the pen icon from the home page, the existing CRS code of stations are displayed. The origin and departure station, departure time and frequency of travel can be updated and option to delete the journey is present. On clicking update a PUT request is sent to the API however if the train journey does not exist a toast `Failed to add journey, Journey not valid` will be shown.

## Installation

### Prerequisites
  - Android Studio or IntelliJ IDEA with Android SDK installed.
  - Java JDK 8+ installed.
  - Gradle (usually bundled with the project via Gradle Wrapper)

### 🚀 Option 1: Run in IntelliJ/Android Studio **(Recommended)**

1. Clone the repository
   
&nbsp;&nbsp;&nbsp;&nbsp;`git clone https://github.com/Jimmyrai321/TTD-Track-Travel-Disruptions-Frontend`

2. Run ▶ 
   
&nbsp;&nbsp;&nbsp;&nbsp;Run to deploy to an emulator or device. The IDE runs Gradle tasks under the hood. You **MUST** have [TTD-API](https://github.com/Jimmyrai321/TTD-Track-Travel-Disruptions-Backend) running locally on port 8080.

### 🛠️ Option 2: Build with Gradle

1. Clone the repository.

   `git clone https://github.com/Jimmyrai321/TTD-Track-Travel-Disruptions-Frontend`

2. Build the project

&nbsp;&nbsp;&nbsp;&nbsp;From the project root, run:
  ```bash
  ./gradlew build        # Mac/Linux
  gradlew.bat build      # Windows
  ```
  
&nbsp;&nbsp;&nbsp;&nbsp;This will compile the app and produce an APK.

3. Install & run

&nbsp;&nbsp;&nbsp;&nbsp;The generated APK can be found under:
  
&nbsp;&nbsp;&nbsp;&nbsp;`app/build/outputs/apk/debug/app-debug.apk`


&nbsp;&nbsp;&nbsp;&nbsp;To install on an emulator or connected device:
  
&nbsp;&nbsp;&nbsp;&nbsp;`adb install app/build/outputs/apk/debug/app-debug.apk`

>[!WARNING]
>The current version of the app requires the [TTD-API](https://github.com/Jimmyrai321/TTD-Track-Travel-Disruptions-Backend) to be ran on port 8080 on localhost.

## Future Considerations
- [ ] Add notifications
- [ ] Different users/login feature
- [ ] Dark theme
- [ ] Add car disruptions feature
- [ ] Add TFL disruptions feature
- [ ] API cloud deployment
