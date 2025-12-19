---
title: Banquet Hall API Docs
language_tabs:
  - csharp: C#
  - json: JSON
toc_footers:
  - <a href='#'>Get API Key</a>
  - <a href='#'>Contact Support</a>
search: true
code_clipboard: true
meta:
  - name: description
    content: Documentation for the Banquet Hall Booking System API
---

# Introduction

Welcome to the **Banquet Hall Booking Management System API**.

This API allows the frontend (Web or Mobile) to communicate with the .NET Core Backend.
It is used to:
* Search for Halls
* Make Bookings
* Process Payments

**Base URL:** `https://localhost:5001/api`

# Authentication

> To authorize, use this code:

```csharp
var client = new HttpClient();
client.DefaultRequestHeaders.Add("Authorization", "Bearer YOUR_ACCESS_TOKEN");


var client = new HttpClient();
// Request to your .NET Core API
var response = await client.GetAsync("https://localhost:5001/api/halls");
var content = await response.Content.ReadAsStringAsync();


var client = new HttpClient();

var bookingData = new
{
    UserId = 101,       // From TblLogin
    HallId = 5,         // From TblHall
    EventStartDate = "2025-11-22",
    EventEndDate = "2025-11-22",
    Time = "PM"         // AM, PM, or FullDay
};

var json = JsonSerializer.Serialize(bookingData);
var content = new StringContent(json, Encoding.UTF8, "application/json");

// POST request to create a booking
var response = await client.PostAsync("https://localhost:5001/api/bookings", content);



var client = new HttpClient();

var paymentData = new
{
    BookingId = 45,     // The ID we got from the Booking step
    Amount = 5000,
    PaymentMethod = "UPI",
    UpiId = "user@oksbi"
};

var json = JsonSerializer.Serialize(paymentData);
var content = new StringContent(json, Encoding.UTF8, "application/json");

var response = await client.PostAsync("https://localhost:5001/api/payments", content);


