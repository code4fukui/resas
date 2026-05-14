# resas

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A collection of client-side JavaScript examples demonstrating the use of Japan's RESAS (Regional Economy Society Analyzing System) API.

**Live Demo:** [http://codeforfukui.github.io/resas/](http://codeforfukui.github.io/resas/)

## About The Project

This repository provides simple, self-contained HTML and JavaScript applications that fetch and display economic and demographic data from the RESAS API. The examples are written in vanilla JavaScript, using a small utility library (`fukuno.js`) for DOM manipulation and helper functions. They serve as a practical guide for developers looking to integrate RESAS data into their own web applications.

## Examples

The demo site includes the following examples:

*   **[Inbound Tourism Stats (`getinbound.html`)](http://codeforfukui.github.io/resas/getinbound.html)**
    *   Displays inbound tourism data (number of foreign visitors) for a selected prefecture.
    *   Users can filter data by month and time of day (day/night).
    *   Results are presented in a table, sorted by country of origin.

*   **[Per-Capita Local Tax (`gettax.html`)](http://codeforfukui.github.io/resas/gettax.html)**
    *   Provides a drill-down interface to explore per-capita local tax data.
    *   Users first select a prefecture, which then lists all its municipalities.
    *   Clicking a municipality fetches its tax data and displays the raw JSON response.

*   **[Prefectures and Municipalities (`allcity.html`)](http://codeforfukui.github.io/resas/allcity.html)**
    *   A hierarchical browser for all prefectures and their respective municipalities.
    *   Clicking a prefecture expands to show a list of its cities, along with statistics like the number of "big cities".

*   **[List of Prefectures (`allpref.html`)](http://codeforfukui.github.io/resas/allpref.html)**
    *   A basic example that fetches and displays the raw JSON data for all Japanese prefectures.

## How to Use

To run these examples, you will need a RESAS API key.

1.  **Get an API Key:** Register and obtain a free API key from the [RESAS API Portal](https://opendata.resas-portal.go.jp).
2.  **Open an Example:** Navigate to one of the demo pages, such as [getinbound.html](http://codeforfukui.github.io/resas/getinbound.html).
3.  **Enter Your Key:** Paste your API key into the input field at the bottom of the page and click the "データ取得開始" (Start Data Fetch) button. The key will be saved in your browser's local storage for future use.
4.  **Explore:** Interact with the dropdowns and lists to query the API and view the data.

## API Endpoints Used

These examples demonstrate how to consume the following RESAS API endpoints:

*   `/api/v1-rc.1/prefectures` - Get a list of all prefectures.
*   `/api/v1-rc.1/cities` - Get a list of cities within a prefecture.
*   `/api/v1-rc.1/municipality/taxes/perYear` - Get per-capita tax data for a municipality.
*   `/api/v1/partner/docomo/inbound` - Get inbound tourism data provided by NTT Docomo.

*Note: The RESAS API has usage limits, typically 5 requests per second and 2000 requests per day.*
