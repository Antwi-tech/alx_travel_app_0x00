# ALX Travel App

This Django project is a simple travel booking API that allows users to view listings, make bookings, and leave reviews.

## 📁 Project Structure

```

alx_travel_app/
├── listings/
│   ├── models.py
│   ├── serializers.py
│   ├── management/
│   │   └── commands/
│   │       └── seed.py
│   └── ...
├── manage.py
├── README.md
└── ...
```


## ✨ Features

- **Listings**: Travel experiences or packages.
- **Bookings**: Users can book listings.
- **Reviews**: Users can leave reviews for listings.

---

## 🧱 Models

### `Listing`
- `title`: short name of the listing
- `description`: detailed information
- `location`: city, country or resort
- `price`: cost of the package
- `created_at`: auto timestamp

### `Booking`
- `listing`: foreign key to Listing
- `guest_name`
- `guest_email`
- `start_date`, `end_date`
- `booked_at`: auto timestamp

### `Review`
- `listing`: foreign key to Listing
- `reviewer_name`
- `comment`
- `rating`: integer
- `reviewed_at`: auto timestamp

---

## 🔁 Serializers

Located in `listings/serializers.py`

- `ListingSerializer`: Serializes all fields of `Listing`
- `BookingSerializer`: Serializes all fields of `Booking`

---

## 🌱 Seeder

Seeds the database with sample listings.

### Location:
`listings/management/commands/seed.py`

### To run:
```bash
python manage.py seed
````

This command will:

* Clear existing listings
* Insert 3 example listings:

  * Accra City Tour
  * Cape Coast Castle Visit
  * Safari in Mole National Park

---

## ⚙️ Setup

```bash
# Apply migrations
python manage.py makemigrations
python manage.py migrate

# Seed sample data
python manage.py seed
```

