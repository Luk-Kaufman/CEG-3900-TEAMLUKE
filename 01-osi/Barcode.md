# Week 1 Notes: Barcodes

## What is a Barcode?

A **barcode** is a machine-readable representation of data using parallel lines (1D) or patterns (2D). Scanners interpret the pattern to recover the encoded value.

---

## Why Barcodes Matter (Cyber / Security Context)

* Used for **identification**, **tracking**, and **lookup**
* Common in **inventory**, **access control**, **tickets**, and **forensics challenges**
* Can hide flags, IDs, or references in CTF-style problems

---

## Key Barcode Concepts

### 1. Barcode *Type* (Symbology)

The **type** defines how data is encoded.
Examples:

* **CODE39** – Alphanumeric (A–Z, 0–9, -, ., space)
* **CODE128** – High-density, full ASCII
* **UPC-A** – Retail products (12 digits)
* **EAN-13** – International retail (13 digits)
* **QR Code** – 2D, high capacity

---

### 2. Barcode *Value*

The **value** is the decoded data stored in the barcode.

* This may be a number, text string, or flag
* Example: `SKY-UZLU-5635`

---

## CODE39 Specifics

* One of the oldest barcode standards
* Uses **narrow and wide bars**
* Typically has **start/stop (*) characters**
* Easy to visually recognize
* Common in access badges and asset tags

---

## How to Analyze a Barcode (Step-by-Step)

1. Upload image to a barcode reader
2. Locate:

   * **Type** → symbology (e.g., CODE39)
   * **Value** → decoded content
3. Use the value as the flag or lookup key

---

## Common Tools

* Online barcode readers
* Mobile barcode scanner apps
* Built-in phone camera (limited details)

---

## Example (From This Challenge)

* **Type:** CODE39
* **Value / Flag:** SKY-UZLU-5635
