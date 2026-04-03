# Cryptography Practice game answers

---

## Decoding 1

1.  Q: `V2UgbXVzdCBjaGFuZ2Ugb3VyIHBhc3N3b3JkcyBldmVyeSBldmVyeSAzNyBkYXlz`

  This is in Base64

  A: We must change our passwords every every 37 days

2. Q: `54335679494739775a584a6864476c7662694273595856755932686c63794270626941784d69426f6233567963773d3d`

  This is in hex. So we've got to convert it to ACSII
  
  ACSII is: 
  - `T3VyIG9wZXJhdGlvbiBzaXNuY2hlcyBpbiAxMiBob3Vycy==`

  which is in base 64. So convert that.

  A: Our operation launches in 12 hours

---

## Decoding 2

1. Q: `83-111-109-101-111-110-101-32-112-108-101-97-115-101-32-99-97-108-108-32-116-104-101-32-97-99-99-111-117-110-116-32-114-101-112-32-116-111-32-97-115-107-32-104-111-119-32-105-115-32-74-73-82-65-32-115-116-105-108-108-32-100-111-119-110-32-97-102-116-101-114-32-56-53-32-100-97-121-115`

  This is a sequence of decimal ASCII codes separated by dashes. So what we've got to do is convert each mumber into an ASCII character.

  A: Someone please call the account rep to ask how is JIRA still down after 85 days

---

## Decoding 3

So...we've got a transmission in an mp3 that we've got to decode. Download that, and listen to it.

1. Q: What is the name of the scheme that is encoding the plaintext message?

  A: Morse Code.

2. Q: What is the flag?

  So...we've got to do some listening. If you want to do the hard work, do so. However, there is a website you could go to and upload the mp3 called [https://morsecode.world/international/decoder/audio-decoder-adaptive.html](Morse Code World) that you could visit. It DOES work!

  A: SKY-MORS-5034

---

## Decoding 4

We've got some binary we've got to work through.

1. Q: What is the name of the medium the data is encoded on?

  A: Punched Card

2. Q: What is the flag?

  A: SKY-PNCH-7592

(I hated this visit [https://www.masswerk.at/cardsampler/](masswerk). You have to punch them in yourself but who the hell cares.)

---

## Decoding 5

I'll just give you the answer.

1. Q: What's the plaintext message?
  
  Here's the message

  `35 53 8 62 11 3 15 122 3 53 54 54 122 12 49 60 11 11 14 122 48 11 12 122 61 8 122 1 10 62 61 14 49 122 53 8 122 69 122 9 53 8 1 14 49 15`

  A: (dont even bother yet)

---

## Signature

We have identified a set of 1000 possible flags, not all of them are the correct flag. However, the files with the correct flag should be signed by one of the certificates created by the included certificate authority.

1. Q: What is the organization name of the certificate authority?

  Here is the command for how to get the org name: `openssl x509 -in [filename.pem] -text -noout | grep "Issuer"

  A: Windoge Certificate Authority

2. Q: What is a valid flag from this set of files?

  A: (dont bother with this one either if you can do it great)
