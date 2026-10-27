# SwiftCare – 24×7 ambulance booking demo

**Live demo:** https://dibyanshi29.github.io/swiftcare/

An interactive ambulance booking web app built around a **live city map**. Choose the right vehicle for the emergency, from a bike first responder to an ICU on wheels or a pet ambulance, then watch it drive to the pickup point and on to the hospital or vet clinic.

The idea comes from my BCA major project (2021), which was built on a PHP template. This version was designed and built from scratch in 2026 as a single-page web app that runs in the browser with no server.

> This is a demo. No real ambulance is dispatched, and all operators, hospitals and vet clinics are fictional. In a real emergency in India, call 108.

## Services

| Service | What it is | How the app handles it |
| --- | --- | --- |
| Bike first responder | A paramedic on a motorbike who beats traffic and starts first aid early | Offered as an add-on to a human ambulance. It arrives first and waits with the patient until the ambulance comes |
| Basic Life Support | Oxygen, stretcher and a trained attendant | Standard ambulance option |
| Advanced Life Support | Ventilator, cardiac monitor and a paramedic | Standard ambulance option |
| Critical Care (ICU) | An ICU on wheels with a doctor on board | Highest fare, for critical patients and transfers |
| Pet ambulance | Transport for dogs, cats and other pets | Goes to vet clinics instead of hospitals, and asks for the animal type and size instead of patient details |

## Views

- **Book:** pick places from the lists or by tapping the map, compare vehicles by arrival time, fare and rating, add a bike responder, confirm, then follow the trip live with a countdown
- **Hospital & vet:** a directory of every hospital and vet clinic, each with an illustration, specialties, facilities, ER wait, rating and free ICU beds. Selecting one shows who is on the way, with condition, animal details and crew notes. The selected destination's details also appear while booking
- **Operator:** summary numbers, a live fleet map, booking status controls, and on/off duty switches for every vehicle

## How it works

- **One file:** `index.html` holds the layout (HTML), design (CSS) and logic (JavaScript).
- **Pictures:** each hospital and vet clinic has its own building illustration, drawn in SVG from a few settings (floors, wings, colours), so no photos are needed.
- **Map:** drawn in SVG. Each place has map coordinates, which are converted to screen positions.
- **Fare:** base fare + price per km × trip distance. The bike responder is a flat add-on.
- **Arrival time:** based on each vehicle's distance from the pickup point. Bikes are modelled as faster in traffic.
- **Matching:** only vehicles that are on duty, free and of the right type are offered. Pet trips only match pet ambulances and vet clinics.
- **Live tracking:** each trip saves its start time and the length of each stage. Four times a second, the app works out where each vehicle should be and moves it. The demo runs fast: one map minute is about one real second.
- **Saving data:** bookings are stored in the browser's `localStorage`, so each visitor has a private copy. "Reset demo data" in the operator view starts fresh.
- **Safety:** everything a user types is escaped before it appears on the page, which prevents script injection (XSS).

## Tech used

HTML · CSS · JavaScript (no frameworks) · SVG · GitHub Pages

## Run it yourself

Download `index.html` and open it in any browser. No installation needed.
