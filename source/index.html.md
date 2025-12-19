---
title: Banquet Hall API Docs
language_tabs:
  - csharp: C# (.NET)
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
// Add the Bearer Token to the header
client.DefaultRequestHeaders.Add("Authorization", "Bearer YOUR_ACCESS_TOKEN");
