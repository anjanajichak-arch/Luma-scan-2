# Luma-scan-2
A Document scanner offline Application 
LumaScan

Premium Offline PDF Scanner

Version: 1.0

---

PRODUCT OVERVIEW

LumaScan is an offline-first document scanner application designed with an iPhone-inspired interface. Users can scan documents or import images, edit pages, rearrange them, and export PDFs locally.

No account.
No cloud.
No ads.
No internet dependency.

---

TARGET PLATFORM

Android 8+
Tablet support
Portrait orientation preferred

---

DESIGN SYSTEM

Color Palette

Primary Blue
#4F8CFF

Accent Green
#7ED957

Accent Yellow
#FFD84D

Background
#FFFFFF

Surface
#F7F8FA

Text Primary
#222222

Text Secondary
#6B7280

---

UI STYLE

- iPhone-inspired
- Rounded corners (20dp)
- Smooth animations
- Material 3 components
- Soft shadows
- Large touch targets
- Card-based design

---

APP STRUCTURE

SplashScreen

HomeScreen

ScannerScreen

GalleryImportScreen

CropScreen

EditorScreen

PageArrangeScreen

PreviewScreen

SavePDFScreen

SavedFilesScreen

SettingsScreen

---

DATA MODEL

Project

id
name
createdTime
lastModified

pages[]

Page

imagePath

croppedImagePath

rotation

brightness

saturation

contrast

filterType

isBlackWhite

pdfIndex

---

FILTER TYPES

ORIGINAL

BLACK_WHITE

GRAYSCALE

HIGH_CONTRAST

DOCUMENT

---

LOCAL STORAGE

Projects stored locally

App/Documents/

Project folder

ProjectName/

page1.jpg

page2.jpg

metadata.json

output.pdf

No database required.

Metadata stored as JSON.

---

SCREEN 1

SPLASH SCREEN

Duration

1.5 seconds

Components

Logo

App name

Fade animation

Navigation

Splash

↓

Home

---

SCREEN 2

HOME SCREEN

Components

Top AppBar

Logo

LumaScan

Buttons

Scan Document

Import Images

Recent Projects

Recent PDFs

Bottom Navigation

Home

Files

Settings

---

HOME LOGIC

Press Scan

Open ScannerScreen

Press Import

Open GalleryImportScreen

Open recent item

Load project

Continue editing

---

SCREEN 3

SCANNER SCREEN

Camera Preview

Capture Button

Flash Toggle

Retake

Done

---

SCAN FLOW

Capture image

↓

Preview image

↓

Accept

↓

CropScreen

↓

EditorScreen

↓

Add next page

OR

Finish

---

SCREEN 4

GALLERY IMPORT SCREEN

Features

Multiple image selection

JPG

PNG

JPEG

Sort selected images

Confirm button

---

IMPORT FLOW

User selects images

↓

Create pages[]

↓

Open CropScreen

---

SCREEN 5

CROP SCREEN

Features

Manual corner cropping

Rotate left

Rotate right

Reset crop

Preview crop

Done button

---

CROP BEHAVIOR

When Done

Save cropped bitmap

Update page object

Navigate to EditorScreen

---

SCREEN 6

EDITOR SCREEN

Top Bar

Back

Page count

Apply To All

Main Preview

Toolbar

Brightness slider

Saturation slider

Contrast slider

Filter selector

Rotate Left

Rotate Right

Reset

Delete page

Next Page

Previous Page

---

BRIGHTNESS RANGE

-100 to +100

Default 0

---

SATURATION RANGE

0 to 200

Default 100

---

CONTRAST RANGE

0.5 to 2.0

Default 1

---

BLACK AND WHITE MODE

Toggle

Convert page to monochrome

Maintain sharp text

High contrast

---

FILTER ALGORITHM

Original

No changes

Document

Adaptive threshold

Black White

Pure monochrome

Gray

Grayscale

High Contrast

Increase contrast

---

APPLY TO ALL LOGIC

When enabled

Current page settings

Brightness

Contrast

Saturation

Filter

Rotation

Copied to every page

Do not overwrite crop coordinates.

---

PAGE DELETE

Remove page

Renumber pages

Update metadata

---

SCREEN 7

PAGE ARRANGEMENT SCREEN

Grid layout

Thumbnail cards

Drag and drop reorder

Delete page

Duplicate page

---

REORDER LOGIC

After drag

Update page order

Save metadata

Refresh PreviewScreen

---

SCREEN 8

PREVIEW SCREEN

PDF page preview

Zoom

Swipe pages

Page count

Edit button

Save button

Share button

---

SCREEN 9

SAVE PDF SCREEN

Fields

File name

Quality

Low

Medium

High

Buttons

Save PDF

Cancel

---

PDF GENERATION

Input

Page bitmaps

↓

Compress

↓

Generate PDF

↓

Save locally

↓

Show success dialog

---

PDF QUALITY

Low

70%

Medium

85%

High

100%

---

OUTPUT PATH

Documents/LumaScan/

filename.pdf

---

SCREEN 10

FILES SCREEN

List saved PDFs

Search

Sort by

Name

Date

Size

Options

Open

Rename

Share

Delete

---

SCREEN 11

SETTINGS SCREEN

Theme

Light

Dark

Output Quality

Default Filter

Clear Recent Projects

About

Privacy Policy

Version

---

STATE MANAGEMENT

ProjectState

Current project

Current page

Page list

Edit settings

Preview state

Export state

---

IMAGE PROCESSING PIPELINE

Original Image

↓

Crop

↓

Rotate

↓

Brightness

↓

Saturation

↓

Contrast

↓

Filter

↓

Save Processed Bitmap

↓

PDF Generator

---

MEMORY OPTIMIZATION

Use bitmap caching

Load thumbnails only

Recycle unused bitmaps

Background image processing

Avoid OOM crashes

Lazy loading

---

ERROR HANDLING

Camera unavailable

Show dialog

Storage permission denied

Request again

Image processing failed

Retry option

PDF save failed

Display error

---

ANIMATIONS

200ms transitions

Card scaling

Fade navigation

Smooth page swipe

No lag

60fps target

---

PERFORMANCE REQUIREMENTS

Open app <1 sec

Page switch <100 ms

PDF export <5 sec for 20 pages

Memory optimized

No ANR

---

PRIVACY

No analytics

No ads

No cloud

No internet access

Everything remains on device

---

RECOMMENDED MODULES

core

ui

scanner

gallery

crop

editor

filters

arrangement

preview

pdf

files

settings

storage

utilities

---

FINAL INSTRUCTION TO AI AGENT

Build a complete production-ready offline PDF scanner named LumaScan with premium iPhone-style UI, yellow-green-blue design language, smooth animations, local storage, manual crop, page editing, page rearrangement, apply-to-all editing, PDF export, and file management. Every feature must be fully functional and optimized. No placeholders, no mock implementations, and no online dependencies.
