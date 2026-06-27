# Walking An Application

*Path:* TryHackMe → Junior Penetration Tester → Web Application Security Fundamentals → Walking An Application

---

# Assessment Goal

This room focused on developing a structured methodology for performing web application reconnaissance and understanding how modern web applications operate from a security perspective.

The objective was to analyze an application's visible and hidden components using browser-based tools, identify information exposed on the client side, and understand how user interactions translate into backend communication.

The exercises demonstrated how effective reconnaissance forms the foundation for every successful web application security assessment.

---

# Application Reconnaissance Methodology

```text
Access Application
        │
        ▼
Explore Functionality
        │
        ▼
Review Page Source
        │
        ▼
Inspect DOM Elements
        │
        ▼
Analyze JavaScript
        │
        ▼
Monitor Network Traffic
        │
        ▼
Inspect Browser Storage
        │
        ▼
Build Application Understanding
```

A complete understanding of application functionality significantly improves vulnerability discovery and reduces the likelihood of overlooking exposed functionality.

---

# Exploring The Website

The assessment began with manually interacting with the application to understand its functionality and user workflows.

Activities performed:

- Navigated through all accessible pages.
- Explored menus and hyperlinks.
- Interacted with forms and input fields.
- Identified authentication mechanisms.
- Observed user workflows and application logic.
- Mapped available functionality.

---

## Information Gathered

- Website structure
- User roles and permissions
- Authentication pages
- Search functionality
- Administrative interfaces
- Potential entry points

---

### Engineering Observation

Manual exploration remains one of the most effective reconnaissance techniques in web application testing.

Many vulnerabilities originate from:

- Hidden pages
- Unlinked functionality
- Misconfigured access controls
- Insecure user workflows

Understanding the application's functionality before testing significantly improves assessment effectiveness.

---

# Viewing The Page Source

The page source was analyzed to identify information that was not immediately visible within the rendered application.

Common findings included:

- HTML comments
- Hidden links
- JavaScript references
- API endpoints
- Email addresses
- Development notes
- Disabled functionality

---

## Example

```html
<!-- TODO: Remove test page before production -->
<a href="/admin">Admin Panel</a>
```

---

## Source Analysis Workflow

```text
View Source
      │
      ▼
Review HTML
      │
      ▼
Identify Hidden Information
      │
      ▼
Document Findings
```

---

### Engineering Observation

Developers frequently leave useful information inside source code.

Examples include:

- Internal directory names
- Administrative portals
- Development comments
- API endpoints
- Debugging information

Source code analysis often provides valuable reconnaissance data with minimal effort.

---

# Developer Tools – Inspector

The browser inspector was used to analyze the Document Object Model (DOM) and understand how the application renders content.

---

## Information Gathered

- Hidden HTML elements
- Form parameters
- Disabled buttons
- Dynamic content
- Client-side validation mechanisms

---

## Example

```html
<input type="hidden" value="admin">
```

```html
<button disabled>Delete User</button>
```

---

## Inspector Workflow

```text
Rendered Page
      │
      ▼
DOM Inspection
      │
      ▼
Analyze Elements
      │
      ▼
Identify Hidden Functionality
```

---

### Engineering Observation

Applications frequently rely on client-side controls to hide functionality.

However, client-side restrictions should never be trusted because users can directly modify:

- HTML elements
- Form values
- Hidden fields
- JavaScript variables

Server-side validation remains essential.

---

# Developer Tools – Debugger

The debugger was used to inspect JavaScript execution and understand client-side application logic.

---

## Information Gathered

- JavaScript functions
- Authentication logic
- Hidden routes
- API endpoints
- Validation mechanisms
- Sensitive variables

---

## Example

```javascript
if(user == "admin")
{
    enableAdminPanel();
}
```

---

## Debugger Workflow

```text
JavaScript Code
        │
        ▼
Set Breakpoint
        │
        ▼
Pause Execution
        │
        ▼
Inspect Variables
        │
        ▼
Analyze Logic
```

---

### Engineering Observation

Client-side JavaScript often exposes valuable information regarding:

- Application workflows
- Hidden features
- Backend endpoints
- Security mechanisms

Understanding JavaScript behavior significantly improves application reconnaissance.

---

# Developer Tools – Network

The Network tab was used to observe communication between the browser and the web server.

---

## Information Gathered

- HTTP methods
- Request parameters
- Cookies
- Authentication tokens
- Response headers
- API requests
- Downloaded resources

---

## Example Requests

```http
GET /profile HTTP/1.1
```

```http
POST /login HTTP/1.1
```

---

## Network Analysis Workflow

```text
User Interaction
        │
        ▼
HTTP Request
        │
        ▼
Server Response
        │
        ▼
Traffic Analysis
```

---

### Engineering Observation

The Network tab provides one of the most valuable perspectives during web application assessments because it reveals exactly how the frontend communicates with backend services.

Many vulnerabilities are discovered by analyzing:

- Hidden parameters
- API endpoints
- Authentication tokens
- Access control mechanisms

---

# Developer Tools – Storage

The Storage tab was used to inspect information stored locally within the browser.

---

## Storage Mechanisms

| Storage Type | Purpose |
|--------------|----------|
| Cookies | Session management |
| Local Storage | Persistent client data |
| Session Storage | Temporary client data |
| IndexedDB | Browser database storage |

---

## Information Gathered

- Session identifiers
- Authentication tokens
- User preferences
- Cached application data
- Sensitive information

---

## Example

```text
Cookie:
PHPSESSID=9f4d8f3a8c
```

```text
Local Storage:
jwt_token=eyJhbGciOi...
```

---

## Storage Analysis Workflow

```text
Browser Storage
       │
       ├── Cookies
       ├── Local Storage
       ├── Session Storage
       └── IndexedDB
```

---

### Engineering Observation

Improper storage of sensitive information within the browser can significantly increase the risk of account compromise.

Examples include:

- Authentication tokens in Local Storage
- Persistent credentials
- Sensitive user data
- Unencrypted session information

---

# Application Intelligence Correlation

```text
Website Exploration
        │
        ▼
Source Code Analysis
        │
        ▼
DOM Inspection
        │
        ▼
JavaScript Analysis
        │
        ▼
Network Monitoring
        │
        ▼
Storage Inspection
        │
        ▼
Complete Application Understanding
```

Comprehensive application reconnaissance depends on combining multiple analysis techniques rather than relying on a single source of information.

---

# Engineering Observations

Several important observations emerged during this assessment:

- Manual exploration remains an essential reconnaissance technique.
- Source code frequently exposes hidden information.
- Client-side controls should never be trusted.
- JavaScript often reveals application logic.
- Network monitoring provides visibility into backend communication.
- Browser storage can expose sensitive information.
- Thorough reconnaissance improves vulnerability discovery.

---

# Operational Security Considerations

Web application reconnaissance generates observable activity and may be recorded by:

- Web server logs
- Authentication systems
- API monitoring platforms
- SIEM solutions
- Web Application Firewalls (WAF)

Reconnaissance activities should always remain within authorized testing boundaries.

---

# Defensive Engineering Perspective

Organizations should:

- Remove unnecessary comments before deployment.
- Implement server-side validation.
- Minimize exposure of sensitive information.
- Secure API endpoints.
- Protect session tokens.
- Avoid storing sensitive information in browser storage.
- Monitor unusual browsing activity.

---

# Key Technical Takeaways

- Understanding application behavior is the foundation of web application testing.
- Source code analysis often reveals valuable information.
- Browser Developer Tools provide deep visibility into application internals.
- Network analysis exposes backend communication mechanisms.
- Browser storage can contain sensitive information.
- Effective reconnaissance significantly improves subsequent security assessments.

---

# Technologies & Tools Practiced

- Browser Developer Tools
- View Page Source
- DOM Inspection
- JavaScript Debugging
- Network Analysis
- Browser Storage Inspection
- Web Application Reconnaissance
- Client-Side Security Analysis
- Application Mapping
