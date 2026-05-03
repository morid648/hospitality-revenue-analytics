# 📖 Data Dictionary — Hospitality Dataset
### Source: Codebasics Data Analytics Bootcamp

---

## 1. dim_date

| Column | Description | Type |
|--------|-------------|------|
| date | Calendar date | Date |
| mmm yy | Month and year (e.g., May 22) | Text |
| week no | Week number of the year | Integer |
| day_type | Weekday or Weekend | Text |

---

## 2. dim_hotels

| Column | Description | Type |
|--------|-------------|------|
| property_id | Unique ID for each hotel property | Integer |
| property_name | Name of the hotel | Text |
| category | Hotel class — Luxury or Business | Text |
| city | City where hotel is located | Text |

---

## 3. dim_rooms

| Column | Description | Type |
|--------|-------------|------|
| room_id | Unique room type code | Text |
| room_class | Room category — Standard, Elite, Premium, Presidential | Text |

---

## 4. fact_aggregated_bookings

| Column | Description | Type |
|--------|-------------|------|
| property_id | Hotel property ID (links to dim_hotels) | Integer |
| check_in_date | Date of guest check-in | Date |
| room_category | Room type booked | Text |
| successful_bookings | Number of confirmed bookings | Integer |
| capacity | Total available rooms for that date | Integer |

---

## 5. fact_bookings

| Column | Description | Type |
|--------|-------------|------|
| booking_id | Unique booking identifier | Text |
| property_id | Hotel property ID (links to dim_hotels) | Integer |
| booking_date | Date booking was made | Date |
| check_in_date | Date of guest check-in | Date |
| checkout_date | Date of guest checkout | Date |
| no_guests | Number of guests in booking | Integer |
| room_category | Room type booked | Text |
| booking_platform | Channel used — OTA, direct, corporate, etc. | Text |
| ratings_given | Guest rating (if provided) | Float |
| booking_status | Cancelled, Checked Out, or No Show | Text |
| revenue_generated | Total revenue from booking (₹) | Float |
| revenue_realized | Actual revenue after cancellation adjustment (₹) | Float |

---

## 🔗 Table Relationships

dim_hotels → fact_bookings (via property_id)
dim_hotels → fact_aggregated_bookings (via property_id)
dim_date → fact_bookings (via check_in_date)
dim_rooms → fact_bookings (via room_category)

---

## ⚠️ Note
Raw data not included in this repository.
Sourced from Codebasics Data Analytics Bootcamp.
Visit [codebasics.io](https://codebasics.io) for access.
