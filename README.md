# Parking Management Assignment — Bug Fix Completed

This project was provided as a broken full-stack Parking Management assignment.
The goal of this assignment was to identify and fix issues across the Django backend, Go backend, and Next.js frontend.

I have reviewed the project, identified the bugs, and successfully fixed them.
The system is now working correctly end-to-end.

---

# Tech Stack

* Django + Django REST Framework
* Go (database/sql with PostgreSQL)
* Next.js
* PostgreSQL
* Docker

---

# Repository Structure

/backend-django — Django backend
/backend-go — Go backend
/frontend-nextjs — Next.js frontend

---

# Bugs Fixed

## Go Backend Fixes

### Active Bookings SQL Fix

Issue:

* Active bookings endpoint returned incorrect data

Fix:

* Changed condition from `end_time IS NOT NULL` to `end_time IS NULL`
* Fixed join condition from `b.slot_id = s.slot_id` to `b.slot_id = s.id`

Result:

* Active bookings API now returns correct data

---

## Django Backend Fixes

### Available Slots Fix

Issue:

* Available slots API returned occupied slots

Fix:

* Updated query to filter `is_occupied=False`

Result:

* Only available slots are returned

---

### Booking Slot Consistency Fix

Issue:

* Slot status not updated after booking

Fix:

* Updated booking logic
* Mark slot occupied during booking

Result:

* Slot occupancy remains consistent

---

### Serializer Fix

Issue:

* Booking creation failed due to serializer configuration

Fix:

* Removed `depth=1`
* Created `BookingReadSerializer`
* Updated views

Result:

* Booking create/update works properly

---

## Frontend Fixes

### API Configuration Fix

Issue:

* Frontend using wrong backend port

Fix:

* Updated API URL from port 8001 to 8000

Result:

* Frontend connects correctly

---

### Slot Loading Fix

Issue:

* Slot loading not working properly

Fix:

* Passed selected lot ID correctly

Result:

* Slots load correctly

---

### UI Refresh Fix

Issue:

* UI not updating after booking

Fix:

* Added refresh logic after booking

Result:

* UI updates automatically

---

# How To Run

## Start PostgreSQL

docker compose up -d

---

## Run Django

cd backend-django
python manage.py migrate
python manage.py runserver 8000

---

## Run Go

cd backend-go
go run main.go

---

## Run Frontend

cd frontend-nextjs
npm install
npm run dev

---

# Application URLs

Frontend
http://localhost:3000

Django
http://localhost:8000

Go
http://localhost:8080

---

# Result

* Parking lots load correctly
* Available slots display correctly
* Booking works correctly
* Slot updates after booking
* Active booking report works

---

# Summary

This assignment involved debugging and fixing real-world issues across:

* Django backend
* Go backend
* Next.js frontend
* Database integration

All bugs have been fixed and the system is now working properly.

---

