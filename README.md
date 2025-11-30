# Booking Cruises Scraper

![banner](https://i.ibb.co/VYK4wF4C/booking-cruises-cover.png)

The **Booking Cruises Scraper** is an Apify actor that extracts cruise offers from Booking.com Cruises. It lets you filter by destination, departure ports, date range, cruise length, and cruise lines, and returns structured offer data suitable for analysis and monitoring.

<p align="center">
  <img src="https://apify-image-uploads-prod.s3.us-east-1.amazonaws.com/DevbkY3adMTBuoECt-actor-c39rqhKQoB9sa7bdg-P5ePlZOtME-Icon_%281%29.jpeg" alt="Booking Cruises Scraper" style="height: 60px; margin-right: 15px;" /><a href="https://apify.com/lexis-solutions/booking-cruises-scraper" target="_blank">
    <img src="https://img.shields.io/badge/Try%20it%20on-Apify-0066FF?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDA4IiBoZWlnaHQ9IjQwOCIgdmlld0JveD0iMCAwIDQwOCA0MDgiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGNsaXAtcGF0aD0idXJsKCNjbGlwMF8zNDFfNDE1NykiPgo8cGF0aCBkPSJNMjE4LjY5NSAxMDRIMzAwLjk3QzMwMi42NDMgMTA0IDMwNCAxMDUuMzU3IDMwNCAxMDcuMDNWMjMyLjc2NkMzMDQgMjM1Ljc3OCAzMDAuMDgzIDIzNi45NDUgMjk4LjQzNCAyMzQuNDI1TDIxNi4xNTkgMTA4LjY5QzIxNC44NDEgMTA2LjY3NCAyMTYuMjg3IDEwNCAyMTguNjk1IDEwNFoiIGZpbGw9IndoaXRlIi8+CjxwYXRoIGQ9Ik0xODkuMzA1IDEwNEgxMDcuMDNDMTA1LjM1NyAxMDQgMTA0IDEwNS4zNTcgMTA0IDEwNy4wM1YyMzIuNzY2QzEwNCAyMzUuNzc4IDEwNy45MTcgMjM2Ljk0NSAxMDkuNTY2IDIzNC40MjVMMTkxLjg0IDEwOC42OUMxOTMuMTU5IDEwNi42NzQgMTkxLjcxMyAxMDQgMTg5LjMwNSAxMDRaIiBmaWxsPSJ3aGl0ZSIvPgo8cGF0aCBkPSJNMjAyLjU5MSAyMDQuNjY4TDEwOS4xMjcgMjk4LjgzNUMxMDcuMjI5IDMwMC43NDcgMTA4LjU4MyAzMDQgMTExLjI3OCAzMDRIMjk2LjhDMjk5LjQ4MyAzMDQgMzAwLjg0MiAzMDAuNzcgMjk4Ljk2NyAyOTguODUyTDIwNi45MDggMjA0LjY4NUMyMDUuNzI2IDIwMy40NzUgMjAzLjc4MiAyMDMuNDY4IDIwMi41OTEgMjA0LjY2OFoiIGZpbGw9IndoaXRlIi8+CjwvZz4KPGRlZnM+CjxjbGlwUGF0aCBpZD0iY2xpcDBfMzQxXzQxNTciPgo8cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEwNCAxMDQpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==&logoColor=white" alt="Try it on Apify" style="border-radius: 12px; height: 60px;" />
  </a>
</p>


---


## 📊 Actor Stats

| Stat | Value |
|------|-------|
| **Version** | `0.1.1` |
| **Last Update** | Nov 30, 2025 |

---


## ✨ Key Features

- **Destination and port filters**: Select regions and specific departure ports.
- **Flexible date range**: Use from/to dates to target sailing windows.
- **Cruise length and line filters**: Focus on short breaks or extended voyages, and specific cruise lines.
- **Sorting and limits**: Control sort type and maximum number of items.
- **Rich offer details**: Get titles, URLs, pricing, vessel, line, sailing dates, and more.

---

## 💡 Why It's Important

Booking.com Cruises aggregates offers across many lines and regions. With this actor, you can:

- **Compare prices and itineraries** across lines, destinations, and dates.
- **Analyze offer details** like vessel, sailing length, departure ports, and promotions.
- **Automate monitoring** of availability, pricing, and featured deals.

---

## 👤 Who Is It For?

This actor is a great fit for:

- **Travel agencies and aggregators** optimizing cruise inventory and pricing.
- **Market researchers and analysts** studying cruise trends and demand.
- **Developers and data teams** building travel products and dashboards.

---

## 🚀 Business Use Cases

- **Price Monitoring**: Track fares across dates, destinations, and cruise lines.
- **Itinerary Research**: Study ports of call, sailing lengths, and seasonality.
- **Competitor Benchmarking**: Compare lines, vessels, and promotions by region.

---

## 🛠 Input Schema

```json
{
  "locations": ["antarctica", "south-america"],
  "departureDateFrom": "2025-10-01",
  "departureDateTo": "2025-12-31",
  "departurePorts": ["argentina-buenos-aires"],
  "cruiseLength": ["12_PLUS_NIGHTS"],
  "cruiseLines": ["scenic-ocean-cruises"],
  "sortType": "RECOMMENDED_CRUISES",
  "maxItems": 10
}
```

Notes:

- `locations`, `departurePorts`, `cruiseLength`, and `cruiseLines` are multi-select arrays; values must be from the predefined lists.
- `departureDateFrom` and `departureDateTo` must match `YYYY-MM-DD`.
- `sortType` accepts: `RECOMMENDED_CRUISES`, `LOWEST_PRICE`, `HIGHEST_PRICE`, `TOP_REVIEWED`, `DEPARTURE_DATE_EARLIEST`.
- Use `maxItems` to limit the number of results scraped.

---

## 📦 Output Schema

```json
{
  "id": 968261,
  "title": "21 Night Antarctica South Georgia & Falkland Islands",
  "url": "https://cruises.booking.com/sc.do?i=968261&c=375&v=1331",
  "mainImageUrl": "https://cruises.booking.com/images/web/375/1331/SHP/ship_sm.jpg",
  "visitPorts": "Falkland Islands <span aria-hidden='true'>&#8226;</span></li><li class='wth2-portsOfCallListLi'> South Georgia Island <span aria-hidden='true'>&#8226;</span></li><li class='wth2-portsOfCallListLi'> Antarctica <span aria-hidden='true'>&#8226;</span></li><li class='wth2-portsOfCallListLi'> Ushuaia, Tierra Del Fuego, Argentina",
  "departurePort": "Buenos Aires, Argentina",
  "price": 27903,
  "incentive": {
    "promo": [
      {
        "genericmessage": "Exclusive Offer: Luxury Transportation Credit - must call!",
        "disclaimerdesc": "Booking.com Bonus: Call to book a memorable luxury sailing and earn this exclusive travel credit...",
        "promoValue": 0,
        "promotionid": 34627
      }
    ],
    "callout": []
  },
  "specialType": "N",
  "numberOfSailings": 1,
  "cruisesummary": {
    "suiteBestPriceDTO": {
      "bucket": "SUITE",
      "price": 27903,
      "rateOptionType": "BF",
      "brocPrice": 27903,
      "status": "O"
    },
    "brochurePrice": 27903,
    "fromPrice": 27903,
    "numberOfNights": 21,
    "savings": 0
  },
  "vessel": {
    "vesselId": 1331,
    "vesselName": "Scenic Eclipse I"
  },
  "resultCardBanner": false,
  "cruiseline": {
    "isLuxury": true,
    "bookableOnline": false,
    "cruiselinename": "Scenic Ocean Cruises",
    "cruiselineId": 375,
    "mobileCruiselineLogo": "/images_unique/logos/cruiseline/260px/cid_375.png"
  },
  "sailingDates": "October 22, 2025"
}
```

## 🌟 Other Booking.com Scrapers

Complete your travel data collection with our full Booking.com scraper suite:

- **[Booking Flights Scraper](https://apify.com/lexis-solutions/booking-flights-scraper)** - Flight offers, prices, and airline data
- **[Booking Attractions Scraper](https://apify.com/lexis-solutions/booking-attractions-scraper)** - Tourist attractions, activities, and experiences
- **[Booking Cars Scraper](https://apify.com/lexis-solutions/booking-cars-scraper)** - Car rental offers and vehicle details
- **[Booking Taxis Scraper](https://apify.com/lexis-solutions/booking-taxis-scraper)** - Taxi services and transportation options

👀 p.s.

Got feedback or need an extension?

Lexis Solutions is a [certified Apify Partner](https://apify.com/partners/find). We can help you with custom solutions or data extraction projects.

Contact us over [Email](mailto:scraping@lexis.solutions) or [LinkedIn](https://www.linkedin.com/company/lexis-solutions)

Image Credit: https://www.booking.com/
