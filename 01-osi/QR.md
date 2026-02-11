# Week 1 Notes: QR Codes

## What is a QR Code?

A **QR (Quick Response) Code** is a **2D barcode** that stores data in a grid of black and white squares. Unlike 1D barcodes, QR codes can hold much more information and can be scanned from any orientation.

---

## Why QR Codes Matter (Cyber / Security Context)

* Commonly used for **URLs**, **authentication**, **payments**, and **logins**
* Frequently abused for **phishing** and **malware delivery** ("quishing")
* Popular in **CTFs** to hide flags, links, or encoded data

---

## Key QR Code Concepts

### 1. QR Code *Type*

* QR codes are their **own symbology** (Type: `QR Code`)
* No need to distinguish subtypes like CODE39 or CODE128

---

### 2. QR Code *Value*

The **value** is the decoded content, which may be:

* A URL
* Plain text
* Wi-Fi credentials
* Contact information
* A flag (e.g., `SKY{example_flag}`)

---

## QR Code Structure (Visual Features)

* **Finder Patterns**: Large squares in three corners (used for alignment)
* **Timing Patterns**: Alternating black/white lines
* **Data Modules**: The remaining squares that store the data
* **Quiet Zone**: Blank border around the code (required for scanning)

---

## Error Correction

QR codes support **error correction**, allowing recovery even if damaged.
Levels:

* **L** – ~7% recovery
* **M** – ~15% recovery
* **Q** – ~25% recovery
* **H** – ~30% recovery

Higher correction = less data capacity

---

## How to Analyze a QR Code (Step-by-Step)

1. Scan with phone camera or QR scanner
2. Observe decoded **value**
3. If it’s a URL:

   * Inspect before opening
   * Look for suspicious domains
4. Use the decoded data as the flag or next step

---

## Common Tools

* Phone camera (basic scan)
* QR scanner apps (more details)
* Online QR decoders

---

## Common Attacks Using QR Codes

* **Quishing**: QR code leads to phishing site
* **Malware links** hidden in QR codes
* **Credential harvesting** via fake login pages

---

## Common Mistakes to Avoid

* Blindly opening QR links
* Assuming QR codes only store URLs
* Ignoring error correction and structure

---
