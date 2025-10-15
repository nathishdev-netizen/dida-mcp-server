# Dida MCP Server

<!-- mcp-name: io.github.nathishdev-netizen/dida-mcp-server -->

A Model Context Protocol (MCP) server for hotel search, booking, and reviews.

[![MCP Registry](https://img.shields.io/badge/MCP-Registry-blue)](https://registry.modelcontextprotocol.io/v0/servers?search=dida)
[![PyPI](https://img.shields.io/pypi/v/dida-mcp-server)](https://pypi.org/project/dida-mcp-server/)

## Features

🏨 **Search Hotels** - Find hotels by location, price, rating, and amenities with 12+ detailed fields per hotel  
📅 **Book Rooms** - Reserve hotel rooms with guest information  
⭐ **View Reviews** - Read customer reviews and ratings

## Installation

### Option 1: Install Locally (PyPI)
```bash
pip install dida-mcp-server
```

Configure in Claude Desktop:
```json
{
  "mcpServers": {
    "dida-hotels": {
      "command": "python",
      "args": ["-m", "dida_mcp_server"]
    }
  }
}
```

### Option 2: Use Remote Server (Cloud)
```json
{
  "mcpServers": {
    "dida-hotels": {
      "url": "https://uninventive-davin-semihistorically.ngrok-free.dev/sse",
      "transport": "sse",
      "headers": {
        "Authorization": "Bearer YOUR_TOKEN"
      }
    }
  }
}
```

Contact: nathishdev@gmail.com for access token.

## Tools

### search_hotels
Search for hotels based on various criteria:
- **city** - Location to search
- **max_price** - Maximum price per night
- **min_rating** - Minimum hotel rating (0-5)
- **amenities** - Required amenities (WiFi, Pool, Gym, etc.)
- **available_only** - Show only available hotels

**Example:**
```json
{
  "city": "New York",
  "max_price": 300,
  "min_rating": 4.5,
  "amenities": ["WiFi", "Pool"]
}
```

### book_hotel
Book a hotel room with guest information:
- **hotel_id** - Hotel identifier
- **guest_name** - Guest's full name
- **guest_email** - Guest's email
- **guest_phone** - Guest's phone number
- **check_in** - Check-in date (YYYY-MM-DD)
- **check_out** - Check-out date (YYYY-MM-DD)

### get_hotel_reviews
Get customer reviews for a specific hotel:
- **hotel_id** - Hotel identifier

## Hotel Data Fields

Each hotel includes 17 detailed fields:
- id, name, description
- price_per_night, currency
- location (city, country, address, coordinates)
- rating, total_reviews
- amenities (array)
- room_types (array)
- availability, available_rooms
- check_in_time, check_out_time
- cancellation_policy
- contact (phone, email, website)
- images (array)

## MCP Registry

This server is registered in the official MCP Registry:
- **Name:** `io.github.nathishdev-netizen/dida-mcp-server`
- **Registry:** https://registry.modelcontextprotocol.io

## License

MIT

## Author

Nathish - [GitHub](https://github.com/nathishdev-netizen)
