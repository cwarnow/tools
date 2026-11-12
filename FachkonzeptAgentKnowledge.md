# SAP Commerce / CDC / CDP / Shopify / Emporix Solution Architect Knowledge Base

## Purpose

This knowledge base supports the creation of SAP solution concepts, technical concepts, integration concepts, effort estimations, test concepts and architecture reviews.

The focus lies on:

- SAP S/4HANA
- SAP ECC
- SAP SD
- SAP Commerce Cloud
- SAP Customer Data Cloud (CDC)
- SAP Customer Data Platform (CDP)
- Shopify
- Emporix
- SAP Integration Suite
- SAP PO
- IDoc
- RFC
- SOAP
- OData
- FIS Shopconnector

---

# Architecture Principles

Before recommending a custom development always check:

1. SAP Standard Process
2. SAP Configuration
3. Standard API
4. BAPI
5. OData Service
6. IDoc
7. RFC
8. BAdI
9. Enhancement Spot
10. User Exit
11. Shopconnector Extension
12. Custom Development

Custom code should always be the last option.

---

# SAP SD Knowledge

## Core Business Objects

### Customer

Relevant Objects:

- Business Partner
- Customer Master
- Contact Person
- Credit Account

### Sales

Relevant Objects:

- Inquiry
- Quotation
- Contract
- Sales Order
- Return Order
- Delivery
- Billing Document
- Credit Memo
- Debit Memo

### Material

Relevant Objects:

- Material Master
- Product Hierarchy
- Cross Selling
- Material Determination
- Product Substitution

---

# SAP SD Tables

## Sales Order

| Object | Table |
|----------|----------|
| Header | VBAK |
| Item | VBAP |
| Partners | VBPA |
| Business Data | VBKD |
| Schedule Lines | VBEP |
| Document Flow | VBFA |

---

## Delivery

| Object | Table |
|----------|----------|
| Delivery Header | LIKP |
| Delivery Item | LIPS |

---

## Billing

| Object | Table |
|----------|----------|
| Billing Header | VBRK |
| Billing Item | VBRP |

---

## Customer

| Object | Table |
|----------|----------|
| General Data | KNA1 |
| Company Code Data | KNB1 |
| Sales Area Data | KNVV |

---

## Business Partner

| Object | Table |
|----------|----------|
| BP General | BUT000 |
| Address | BUT020 |
| Bank Details | BUT0BK |

---

## Material

| Object | Table |
|----------|----------|
| Basic Data | MARA |
| Plant Data | MARC |
| Storage Location | MARD |
| Sales Data | MVKE |

---

# SAP User Management

| Purpose | Table |
|----------|----------|
| User Master | USR02 |

---

# Credit Management

| Purpose | Table |
|----------|----------|
| Credit Control Area | T014 |
| Credit Management | UKMBP_CMS |

---

# SAP Standard APIs and BAPIs

## Sales Orders

### Create

BAPI_SALESORDER_CREATEFROMDAT2

### Change

BAPI_SALESORDER_CHANGE

### Simulation

BAPI_SALESORDER_SIMULATE

---

## Business Partner

CL_MD_BP_MAINTAIN

---

## Customer

CMD_EI_API

---

## Material

BAPI_MATERIAL_SAVEDATA

---

## Delivery

BAPI_OUTB_DELIVERY_CHANGE

---

# Common Mapping Helpers

## Sales Item Mapping

MAP2E_VBAP_TO_BAPISDIT

Use when mapping SD items to BAPI item structures.

---

# SAP Commerce Cloud Knowledge

## Product Objects

- ProductModel
- BaseProductModel
- VariantProductModel
- GenericVariantProduct
- CatalogVersionModel

---

## Catalog Structure

- Catalog
- CatalogVersion
- Product
- Base Product
- Variant Product

---

## Pricing Objects

- PriceRow
- DiscountRow
- Europe1

---

## Inventory Objects

- StockLevel
- Warehouse
- Point Of Service

---

## Import Technologies

### Impex

Used for:

- Product Import
- Price Import
- Customer Data
- Catalog Data

### Hotfolder

Used for:

- Batch Imports
- ERP Integration
- Product Updates
- Price Updates

---

## Commerce Technical Topics

### CronJobs

Used for:

- Data Synchronization
- Product Import
- Cleanup

### OCC APIs

Used for:

- Storefront Integration
- Mobile Applications
- External Channels

---

# Shopify Knowledge

## Important Entities

### Customer

- Shopify Customer

### Products

- Product
- Variant

### Inventory

- Inventory Item
- Inventory Level

### Order

- Draft Order
- Order

### Return

- Return
- Reverse Fulfillment

### Fulfillment

- Fulfillment
- Fulfillment Order

---

## Shopify Integration Review

Always verify:

- GraphQL API Usage
- Customer Ownership
- Product Ownership
- Price Ownership
- Stock Ownership
- Order Ownership

---

# Emporix Knowledge

## Key Business Entities

### Customer

Customer

### Organization

Organization

### Product

Product

### Catalog

Catalog

### Pricing

Price

### Cart

Cart

### Order

Order

### Subscription

Subscription

---

## Emporix Integration Questions

Always clarify:

### Master Data Ownership

- Product maintained in ERP?
- Product maintained in PIM?
- Product maintained in Emporix?

### Pricing Ownership

- SAP Price Engine?
- Commerce Price Engine?
- External Pricing Service?

### Inventory Ownership

- SAP Inventory
- WMS Inventory
- External Inventory

### Order Ownership

- SAP
- Middleware
- Commerce

---

## Security

- OAuth
- REST APIs
- Webhooks

---

# SAP Customer Data Cloud (CDC)

## Main Objects

### Customer Account

Account

### Profile

Profile

### Permissions

Consent

### Preferences

Preferences

---

## CDC Architecture Questions

Always verify:

### Registration

- Guest Checkout?
- User Registration?
- Password Login?
- Social Login?

### Consent

- Opt-In
- Double Opt-In
- Consent Versioning

### Data Lifecycle

- Account Merge
- Duplicate Handling
- Data Retention

---

# SAP Customer Data Platform (CDP)

## Main Objects

### Unified Customer Profile

Single Customer View

### Audience

Audience

### Segments

Segment

### Activities

Events

---

## CDP Architecture Questions

Always verify:

### Identity Resolution

- Matching Logic
- Golden Record
- Source Prioritization

### Customer Profile

- Source Systems
- Profile Enrichment
- Consent Synchronization

### Activation

- Commerce
- Marketing
- Service

---

# SAP Integration Suite

## Components

### Cloud Integration

iFlows

### API Management

API Layer

### Open Connectors

External Platform Integration

### Event Mesh

Event Driven Integration

---

## Integration Review Checklist

Always verify:

- Error Handling
- Reprocessing
- Logging
- Monitoring
- Alerting
- Retry Strategy

---

# SOAP Integrations

## Development

SPROXY

### Monitoring

SRT_UTIL

SRT_ELOG

---

# OData Integrations

## Service Activation

/IWFND/MAINT_SERVICE

## Error Analysis

/IWFND/ERROR_LOG

---

# RFC Integrations

## Destination Management

SM59

## Transactional RFC Errors

SM58

## RFC Trace

RSRFCTRC

---

# SAP PI / PO

## Message Monitoring

SXMB_MONI

---

# IDoc Knowledge

## Core Transactions

### Display

WE02

WE05

### Test

WE19

### Segments

WE31

### Documentation

WE60

---

## Reports

### Reset Status

RC1_IDOC_SET_STATUS

### XML Transformation

IDOC_XML_TRANSFORM

---

## Tables

| Object | Table |
|----------|----------|
| Control Record | EDIDC |
| Status Records | EDIDS |
| Data Records | EDID4 |

---

# SAP Monitoring

## Dump Analysis

ST22

---

## Performance Analysis

ST12

---

## Database Analysis

DB02

---

## HTTP Monitoring

SMICM

SMMS

---

## Queue Monitoring

SMQ2

SMQS

---

## Job Monitoring

SM37

TBTCP

---

# Security and Authorization

## Authorization Errors

SU53

---

## User Activity

SM20

---

## Users

USR02

---

# Debugging and Development

## Data Dictionary

SE11

---

## Data Browser

SE16N

---

## ABAP Source Search

RS_ABAP_SOURCE_SCAN

---

## Number Ranges

SNRO

---

## Logpoints

SAAB

---

## External Breakpoints

Supported for:

- RFC
- HTTP
- Dialog Users

---

# Pricing and Conditions

## Pricing Procedure

V/08

---

## Condition Scheme

VOK0

---

# Material Determination

## Display

VB13

## Change

VB12

## Create

VB11

---

# Cross Selling

## Generate

SDCRSL01

## Display

VB43

## Change

VB42

## Create

VB41

---

# Promotions

## Display

VB23

## Change

VB22

---

# Output Management

## Message Control

NACE

## Reprocess Billing Messages

VF31

---

# Billing

## Display Billing Document

VF03

---

# Deliveries

## Change Delivery

VL02N

---

# Inventory and Availability

## Stock Overview

MMBE

---

## MRP Monitor

/RSR/MM_DISPOMON

---

# Credit Management

## ECC

FD32

## S4HANA

UKM_BP

---

# Financials

## Customer Line Items

FBL5N

## Accounting Document

FB03

---

# Position Type Determination

VOV4

---

# Technical Utilities

## Clear Buffers

/$sync

---

## Fiori Launchpad

/ui2/flp

---

# Text Management

## Text Objects

TTXOB

## Text IDs

TTXID

## Text Titles

TTXIT

---

# Transport and Quality

## Transport Check

ZTR_CHECK

## SAP Standard Transport Check

/SDF/TRCHECK

---

# FIS Specific Transactions

## FIS Custom Transactions

YTOS_TRANS

ZOSS_TRANSPORT_CLIPBOARD

---

# Effort Estimation Guidelines

## Small Change

0.25 - 1 BT

Examples:

- Mapping Adjustment
- Field Extension
- Existing Interface Enhancement

---

## Medium Change

1 - 3 BT

Examples:

- New API Mapping
- New Queue Processing
- New IDoc Segment
- New CDC Field Mapping

---

## Large Change

3 - 8 BT

Examples:

- New Integration Flow
- New Commerce Feature
- Return Process
- Customer Synchronization

---

## Typical Estimation Structure

| Activity | Typical Effort |
|-----------|-----------|
| Concept | 0.25 - 1 |
| Mapping | 0.25 - 1 |
| Development | Variable |
| Unit Test | 0.5 |
| Documentation | 0.25 |
| QA | 0.5 |
| Go Live | 0.25 |

---

# Solution Architect Review Output

Every concept should be enriched with:

## Relevant SAP Transactions

## Relevant Tables

## Relevant BAPIs

## Relevant APIs

## Relevant Enhancement Options

## Relevant Customizing

## Monitoring Considerations

## Error Handling

## Technical Risks

## Missing Test Cases

## Effort Estimation Review

## Open Questions

## Recommended Next Steps
