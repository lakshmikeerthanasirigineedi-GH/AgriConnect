# AgriConnect

### Connecting Farmers with Accessible Procurement

AgriConnect is a farmer-focused digital platform designed to make agricultural procurement easier to plan and manage. It helps farmers identify suitable procurement centres, plan their visits, book available slots, receive payment-related updates, and maintain digital procurement records.

This repository contains the current working prototype developed for demonstration and evaluation.

---

## Current Prototype

The current prototype demonstrates the main farmer-side workflow of AgriConnect.

### Farmer Login

The prototype uses phone-number-based login with a demo OTP for authentication.

The OTP is currently simulated for demonstration purposes and is not connected to a real SMS service.

### Crop and Quantity

The farmer can select the required crop and enter the quantity they want to take for procurement.

### Location

The prototype currently supports manual or predefined location selection.

The location is used to calculate the distance between the farmer and available procurement centres.

### Suitable Procurement Centre Finder

AgriConnect identifies suitable procurement centres by considering factors such as:

- Crop compatibility
- Required quantity
- Available slots
- Queue conditions
- Centre capacity
- Distance from the farmer

The system then presents suitable options to help the farmer plan where to visit.

### Distance Calculation

The prototype uses the Haversine formula to calculate geographical distance between the farmer's location and procurement centres.

This is currently implemented within the application and does not depend on an external map API.

### Smart Scheduling

The prototype provides scheduling support by considering factors such as distance, estimated travel time, available appointment slots, and queue conditions.

The scheduling logic is rule-based decision support. It is not currently based on a machine-learning model.

### Slot Booking

The farmer can select an available procurement slot and confirm a booking.

The booking is stored in the prototype so that it remains available when the application is reopened.

### Payment Status Notification

The prototype includes a centre-side payment update flow.

When a payment is marked as credited in the prototype, the corresponding payment status and notification are made available to the farmer.

This is a simulated workflow and is not connected to a bank or live payment API.

### Procurement History

Farmers can view their previous procurement-related records digitally, including relevant booking and payment information.

### Notifications

The prototype provides notifications for important actions such as booking confirmation and payment updates.

### Cold-Storage Recommendations

The prototype can recommend available storage facilities based on factors such as crop compatibility, available capacity, and distance.

### Multilingual Support

The application includes support for multiple Indian languages.

The current prototype uses predefined translations for the supported interface content. A translation API can be integrated later to provide broader and more complete translations throughout the application.

### Farmer Procurement Information

A dedicated Procurement Information page has been added to the farmer dashboard.

It provides reference information about:

- MSP
- Procurement rules
- Farmer eligibility and applicable conditions
- Procurement schedules
- Procurement process
- Important procurement-related notes

The information is based on official government sources and is intended to help farmers understand the procurement process.

---

## Current Prototype Limitations

Some parts of the application are intentionally represented using prototype or demonstration implementations.

Currently:

- OTP authentication uses a demo OTP instead of sending a real SMS.
- Location can be selected manually or from predefined locations.
- Procurement centre, slot, queue, and capacity information is representative prototype data.
- Payment confirmation is simulated and does not access a farmer's bank account.
- Notifications are handled within the prototype.
- Translations are currently predefined rather than generated through a translation service.
- Data is stored locally in the browser using Local Storage.
- The application is not currently connected to live government procurement systems.

These limitations are part of the current prototype implementation and do not represent the intended final production architecture.

---

## Planned Production Implementation

The current interface and application structure are designed so that the prototype data layer can be replaced with a centralized backend without changing the overall farmer-facing workflow.

### Authentication

The current demo OTP flow can be replaced with Firebase Authentication and a real OTP/SMS-based authentication process.

### Database

The current browser Local Storage can be replaced with Cloud Firestore.

The main application data can then be organized into collections such as:

- Users
- Procurement Centres
- Bookings
- Payments
- Procurement History
- Notifications
- Storage Facilities

This would allow data to be centrally stored and accessed rather than remaining only in one browser.

### Location

The prototype's manual/predefined location approach can be extended using browser geolocation and appropriate production location services.

### Translation

The current predefined translations can be extended using a translation API so that the complete farmer-facing content can be made available in supported Indian languages.

### Procurement Data

The representative centre and queue information used in the prototype can be replaced with authorized and regularly updated procurement data where appropriate government data access is available.

### Payment

The simulated payment-status workflow can be connected to an authorized procurement or payment system where such integration and access are available.

---

## Technology

The current prototype is developed as a web application using:

- HTML
- CSS
- JavaScript
- Vite
- Browser Local Storage

The application logic, including distance calculation, centre selection, scheduling support, booking, notifications, history, and storage recommendations, is implemented on the client side in the current prototype.

Firebase and other external services are part of the planned production implementation and are not claimed as currently integrated in this prototype.

---

## Smart Decision Support

AgriConnect currently uses rule-based logic to support procurement planning.

The prototype considers multiple factors rather than relying only on distance. These include crop compatibility, quantity, centre availability, queue conditions, capacity, and travel considerations.

The purpose is to help farmers make better-informed procurement visit plans.

No machine-learning model is currently implemented in the prototype.

---

## Running the Project

Install the dependencies:

```bash
npm install