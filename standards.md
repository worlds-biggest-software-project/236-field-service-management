# Standards & API Reference

> Project: Field Service Management · Generated: 2026-05-03

## Industry Standards & Specifications

### ISO Standards

**ISO 9001:2015 — Quality Management Systems**
- URL: https://www.iso.org/standard/62085.html
- Defines requirements for a quality management system. Directly applicable to field service organisations that must demonstrate consistent service delivery, audit trails, and process documentation for work orders, inspections, and corrective actions.

**ISO 41001:2018 — Facility Management — Management Systems**
- URL: https://www.iso.org/standard/68021.html
- Specifies requirements for a facility management (FM) system, including the management of field-based service delivery, contractor coordination, and workplace support services. Adopts the Annex SL high-level structure, enabling integration with ISO 9001 and ISO 55001.

**ISO 55000:2014 / ISO 55001:2014 — Asset Management**
- URL: https://www.iso.org/standard/55088.html
- Governs the lifecycle management of physical assets. Field service management systems that integrate with asset registers must align maintenance activities, service histories, and condition data with ISO 55001 requirements to support whole-life costing and risk-based maintenance strategies.

**ISO/IEC 42001:2023 — Artificial Intelligence Management System**
- URL: https://www.iso.org/standard/81230.html
- Provides a framework for responsible AI governance. Relevant when FSM platforms embed AI for scheduling optimisation, predictive dispatch, or customer interaction, particularly to satisfy procurement requirements from public-sector or regulated-industry customers.

**ISO/IEC 27001:2022 — Information Security Management Systems**
- URL: https://www.iso.org/standard/27001
- Establishes controls for protecting sensitive field-service data including customer locations, equipment records, contract terms, and technician personal data. Increasingly required for enterprise and public-sector FSM deployments.

### W3C & IETF Standards

**RFC 7231 — Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content**
- URL: https://datatracker.ietf.org/doc/html/rfc7231
- Defines HTTP request methods, status codes, and headers that form the foundation of all REST-based FSM APIs.

**RFC 9457 — Problem Details for HTTP APIs**
- URL: https://www.rfc-editor.org/rfc/rfc9457.html
- Supersedes RFC 7807. Defines a standard JSON/XML format for communicating API error responses. Adopted by well-designed FSM REST APIs to return structured error information (type, title, status, detail, instance).

**RFC 6749 — The OAuth 2.0 Authorization Framework**
- URL: https://datatracker.ietf.org/doc/html/rfc6749
- Defines the delegation protocol used by all major FSM APIs (Salesforce, ServiceTitan, Jobber, Simpro, Zuper) to grant third-party integrations access to customer data without exposing credentials.

**RFC 7636 — Proof Key for Code Exchange (PKCE)**
- URL: https://datatracker.ietf.org/doc/html/rfc7636
- Extends OAuth 2.0 for mobile and single-page applications. Essential for FSM mobile worker apps that authenticate against platform APIs without a server-side secret.

**RFC 5545 — Internet Calendaring and Scheduling Core Object Specification (iCalendar)**
- URL: https://datatracker.ietf.org/doc/html/rfc5545
- Defines the iCalendar format for representing scheduling events, recurring patterns, and free/busy information. Applicable to FSM platforms that export technician schedules or appointment confirmations to external calendaring systems (Google Calendar, Outlook, Apple Calendar).

**RFC 7946 — The GeoJSON Format**
- URL: https://datatracker.ietf.org/doc/html/rfc7946
- Defines a JSON-based interchange format for geographic features. Relevant to FSM platforms that represent technician locations, job-site addresses, service territories, and route geometries as geospatial data.

**RFC 4122 — A Universally Unique Identifier (UUID) URN Namespace**
- URL: https://datatracker.ietf.org/doc/html/rfc4122
- Defines UUID generation for unique identifiers on work orders, assets, technicians, and customers across distributed FSM systems and integrations.

### Data Model & API Specifications

**OpenAPI Specification 3.1 (OAS 3.1)**
- URL: https://spec.openapis.org/oas/v3.1.0.html
- The de-facto standard for documenting REST APIs. OAS 3.1 achieves full JSON Schema Draft 2020-12 compatibility, supporting rich work-order and scheduling data model definitions. Salesforce Field Service REST API publishes OAS 3.0 documents; the wider ecosystem is migrating to 3.1.

**OData 4.01 Protocol (ISO/IEC 20802-1:2016)**
- URL: https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html
- An OASIS and ISO/IEC standard REST protocol providing a uniform way to query and manipulate data via HTTP. Used natively by Microsoft Dynamics 365 Field Service and IFS FSM for exposing entity data (work orders, resources, bookings). Enables standard filter, expand, and select query patterns across FSM resources.

**JSON Schema (Draft 2020-12)**
- URL: https://json-schema.org/specification
- Used within OAS 3.1 to define and validate FSM data models for work orders, service appointments, technician records, parts inventory, and customer assets.

**GraphQL Specification**
- URL: https://spec.graphql.org/
- Jobber uses GraphQL as its primary API protocol, allowing integrators to query only the fields they need (e.g., work order status, technician location, invoice amount) without over-fetching.

### Security & Authentication Standards

**OpenID Connect 1.0**
- URL: https://openid.net/specs/openid-connect-core-1_0.html
- Identity layer on top of OAuth 2.0 used by enterprise FSM platforms for federated authentication (SSO). Supports user-consent flows aligned with GDPR data-minimisation requirements, particularly relevant when FSM platforms process technician biometric data or customer personal information.

**OWASP API Security Top 10 (2023)**
- URL: https://owasp.org/www-project-api-security/
- Defines the most critical security risks for APIs. FSM APIs should be audited against this list, particularly Broken Object Level Authorisation (BOLA) risks when technicians or customers access work order records.

**NIST Special Publication 800-53**
- URL: https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final
- Security and privacy controls catalogue referenced by US public-sector FSM procurement. Relevant for field service platforms deployed in utilities, government facilities, or critical infrastructure.

**GDPR (EU) 2016/679**
- URL: https://gdpr-info.eu/
- EU regulation governing the collection, processing, and storage of personal data. FSM platforms that record technician GPS locations, capture customer signatures, or store job-site photographs must implement data retention policies, right-to-erasure endpoints, and lawful-basis documentation.

### MCP Server Specifications

**Model Context Protocol (MCP)**
- URL: https://modelcontextprotocol.io/
- Anthropic's open standard for connecting AI agents to external tools and data sources. Relevant for an AI-native FSM platform: an MCP server could expose work-order queries, technician availability, and parts-inventory lookups as tools callable by an LLM-based dispatch agent or customer-facing chatbot.

---

## Similar Products — Developer Documentation & APIs

### Salesforce Field Service

- **Description:** FSM module built on Salesforce CRM, featuring AI-powered scheduling (Einstein), a mobile worker app, and deep integration with Service Cloud.
- **API Documentation:** https://developer.salesforce.com/docs/atlas.en-us.field_service_dev.meta/field_service_dev/fsl_dev_rest.htm
- **SDKs/Libraries:** Salesforce Mobile SDK (iOS, Android, JavaScript); Apex (server-side); Lightning Web Components
- **Developer Guide:** https://developer.salesforce.com/docs/apis
- **Standards:** REST/JSON; OpenAPI 3.0 (Beta for sObjects); Bulk API 2.0 for large data volumes
- **Authentication:** OAuth 2.0 (authorization code, JWT bearer, client credentials)

### Microsoft Dynamics 365 Field Service

- **Description:** FSM module within the Dynamics 365 platform offering work order management, intelligent scheduling, IoT-triggered dispatch, and AR remote assistance.
- **API Documentation:** https://learn.microsoft.com/en-us/dynamics365/field-service/developer/reference/about-entity-reference
- **SDKs/Libraries:** Dataverse .NET SDK; Power Platform CLI; JavaScript/TypeScript client libraries
- **Developer Guide:** https://learn.microsoft.com/en-us/dynamics365/field-service/
- **Standards:** OData 4.0 (Web API); REST/JSON; OpenAPI 2.0 (Swagger) via Power Platform connectors
- **Authentication:** OAuth 2.0 (Azure AD / Entra ID); MSAL libraries for token acquisition

### Oracle Field Service (formerly TOA / ClickSoftware)

- **Description:** Enterprise scheduling and optimisation platform serving utilities, telecoms, and field-operations-intensive industries.
- **API Documentation:** https://docs.oracle.com/en/cloud/saas/field-service/api.html
- **SDKs/Libraries:** No official SDK; REST API accessed via standard HTTP clients
- **Developer Guide:** https://docs.oracle.com/en/cloud/saas/field-service/faasv/understanding-field-service-apis.pdf
- **Standards:** REST/JSON; legacy SOAP Web Service API supported for upgrading customers
- **Authentication:** OAuth 2.0

### ServiceNow Field Service Management

- **Description:** FSM module within the ServiceNow platform for managing planned and reactive maintenance, technician dispatch, and SLA tracking.
- **API Documentation:** https://www.servicenow.com/docs/r/api-reference/rest-apis/api-rest.html
- **SDKs/Libraries:** ServiceNow JavaScript API (server-side Glide); REST integration via Table API
- **Developer Guide:** https://developer.servicenow.com/
- **Standards:** REST/JSON; Table API for CRUD operations; OpenAPI 3.0 (downloadable spec per instance)
- **Authentication:** OAuth 2.0; Basic Auth; API Key; mutual TLS

### ServiceTitan

- **Description:** FSM platform targeting home-services verticals (HVAC, plumbing, electrical) with rich job costing, dispatch, and customer communication features.
- **API Documentation:** https://developer.servicetitan.io/docs/overview/
- **SDKs/Libraries:** No official SDK; REST API via standard HTTP; Make / Zapier connectors available
- **Developer Guide:** https://developer.servicetitan.io/docs/get-going-first-api-call/
- **Standards:** REST/JSON; Transactional and Export API patterns
- **Authentication:** OAuth 2.0 (client credentials); app-key header required on all requests

### Jobber

- **Description:** FSM platform for small and medium home-service businesses with quoting, scheduling, dispatching, invoicing, and online payment features.
- **API Documentation:** https://developer.getjobber.com/docs/
- **SDKs/Libraries:** No official SDK; GraphQL client libraries (Apollo, urql, gql) work out of the box
- **Developer Guide:** https://developer.getjobber.com/docs/getting_started/
- **Standards:** GraphQL; Webhooks (HMAC-SHA256 signed, at-least-once delivery)
- **Authentication:** OAuth 2.0 (authorization code flow); access tokens valid 60 minutes; webhook verification via X-Jobber-Hmac-SHA256 header

### Simpro

- **Description:** Cloud-based field service and job management platform for trade contractors, including electrical, plumbing, HVAC, and security.
- **API Documentation:** https://developer.simprogroup.com/apidoc/
- **SDKs/Libraries:** Code examples provided in the developer portal (multiple languages)
- **Developer Guide:** https://developer.simprogroup.com/
- **Standards:** REST/JSON; OData query support
- **Authentication:** OAuth 2.0 (authorization code)

### Zuper

- **Description:** AI-powered FSM platform for service businesses, offering scheduling, dispatch, work orders, invoicing, and customer portals.
- **API Documentation:** https://developers.zuper.co/reference/getting-started-with-your-api
- **SDKs/Libraries:** No official SDK; standard REST HTTP client
- **Developer Guide:** https://developers.zuper.co/docs/getting-started
- **Standards:** REST/JSON
- **Authentication:** API Key; OAuth 2.0 for partner integrations

### Housecall Pro

- **Description:** SMB-focused FSM platform for home-services professionals with scheduling, dispatch, payments, and customer messaging.
- **API Documentation:** https://docs.housecallpro.com/
- **SDKs/Libraries:** No official SDK; REST API via standard HTTP
- **Developer Guide:** https://help.housecallpro.com/en/articles/8505035-api-overview
- **Standards:** REST/JSON; OpenAPI 3.0 specification published
- **Authentication:** OAuth 2.0; API available on MAX plan only

### Fieldwire

- **Description:** Field management platform primarily for construction, offering plans management, task tracking, and field inspections.
- **API Documentation:** https://developers.fieldwire.com/
- **SDKs/Libraries:** No official SDK; REST API via standard HTTP
- **Developer Guide:** https://developers.fieldwire.com/docs/getting-started
- **Standards:** REST/JSON; predictable URL structure for resource-oriented design
- **Authentication:** API Key (Bearer token)

---

## Notes

**Scheduling Optimisation as a Proprietary Layer:** The core scheduling optimisation engines in enterprise FSM tools (Oracle/ClickSoftware, IFS PSO, Salesforce Einstein Scheduling) are proprietary algorithms with no published standards. Open-source alternatives include Google OR-Tools (Apache 2.0) for vehicle routing problems, which provides a standards-compliant foundation for an AI-native FSM scheduler.

**No Dominant Domain-Specific Data Standard:** Unlike healthcare (HL7/FHIR) or finance (FIX/ISO 20022), field service management has no widely adopted domain-specific data interchange standard. Most interoperability occurs via OData (enterprise), GraphQL (mid-market), or REST/JSON with proprietary schemas. This represents an opportunity for an open-source AI-native FSM project to establish or adopt a community data standard.

**Geolocation & Routing:** Real-time technician tracking commonly integrates with Google Maps Platform (Directions API, Distance Matrix API) or HERE Technologies APIs, alongside GeoJSON (RFC 7946) for territory and route representations. Neither has a field-service-specific standard extension.

**Emerging AI/MCP Integration:** The Model Context Protocol (MCP) is increasingly relevant for FSM automation — enabling LLM agents to query work-order queues, check parts availability, and optimise dispatch in natural language. An open-source FSM platform with a well-designed MCP server would be highly differentiating in the current market.
