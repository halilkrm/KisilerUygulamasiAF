<div align="center">

# 👥 Kişiler Uygulaması — Alamofire

An iOS contacts application built with **SwiftUI** and **Alamofire**.

![Swift](https://img.shields.io/badge/Swift-iOS-F05138?logo=swift&logoColor=white)
![SwiftUI](https://img.shields.io/badge/UI-SwiftUI-0D96F6?logo=swift&logoColor=white)
![Alamofire](https://img.shields.io/badge/Networking-Alamofire-EF3B2D)

</div>

---

## Overview

The current source code connects to an external PHP API and implements contact listing, search, insertion, update, and deletion.

JSON responses are decoded with `JSONDecoder`.

---

## Implemented Features

- Contact list
- SwiftUI navigation
- Search with `.searchable`
- Search request on search-text changes
- Create contact
- Update contact
- Delete contact
- Swipe-to-delete from the list
- Alamofire GET and POST requests
- JSON decoding

---

## API Endpoints Used by the Current Code

Base host:

```text
http://kasimadalan.pe.hu/kisiler/
```

| Operation | HTTP method | Endpoint |
|---|---|---|
| List contacts | GET | `tum_kisiler.php` |
| Search contacts | POST | `tum_kisiler_arama.php` |
| Insert contact | POST | `insert_kisiler.php` |
| Update contact | POST | `update_kisiler.php` |
| Delete contact | POST | `delete_kisiler.php` |

---

## Request Parameters Used by the Code

### Search

```text
kisi_ad
```

### Insert

```text
kisi_ad
kisi_tel
```

### Update

```text
kisi_id
kisi_ad
kisi_tel
```

### Delete

```text
kisi_id
```

---

## Main Source Structure

```text
KisilerUygulamasiAF/
└── KisilerUygulamasiAF/
    └── KisilerUygulamasi/
        ├── data/
        │   └── entity/
        └── ui/
            ├── view/
            └── viewmodel/
                ├── AnasayfaViewModel.swift
                ├── KisiKayitViewModel.swift
                └── KisiDetayViewModel.swift
```

---

## Current Data Flow

```text
SwiftUI View
   ↓
ViewModel
   ↓
Alamofire request
   ↓
External PHP API
   ↓
JSON response
   ↓
JSONDecoder
   ↓
Published contact list
```

---

## Getting Started

### Requirements

- macOS
- Xcode
- iOS Simulator or physical iOS device
- Internet connection
- Alamofire dependency resolved by the Xcode project

### Clone

```bash
git clone https://github.com/halilkrm/KisilerUygulamasiAF.git
cd KisilerUygulamasiAF
```

Open the included Xcode project and run it.

---

## Current Code Notes

- The application depends on an external API that is not included in this repository.
- The current endpoints use plain `http://`.
- Network error handling is currently limited mainly to printing decoding errors.
- The delete flow reloads the contact list after a successful response is decoded.
