# TaskBoard

# 🧾 Epic: Portfolio Dashboard Experience

### Description:
Design and develop a complete portfolio dashboard experience that provides users with a summarized view of their properties, EPC statuses, and watchlists. The dashboard should be responsive, intuitive, and powered by efficient backend logic using FastAPI and MongoDB to ensure real-time and aggregated metrics.

## ✅ User Story 1: View portfolio overview on dashboard

### Description
As a user, I want to view a responsive dashboard that shows key metrics like properties monitored, EPCs expiring soon, average EPC rating, and watchlists, so that I can quickly understand my portfolio status.

Subtasks:
- [ ] Design responsive dashboard layout (Next JS)
- [ ] Display total properties monitored in a card
- [ ] Show count of expiring EPCs (next 2 years)
- [ ] Display average EPC rating (letter grade with visual indicator)
- [ ] Show count of watchlists with clickable view

**Module**: Frontend  
**Priority**: High  
**Status**: Open  

---

## ✅ User Story 2: Access recent watchlists from dashboard

### Description
As a user, I want to view my recent watchlists on the dashboard, so that I can quickly access them without navigating away.

Subtasks:
- [ ] Fetch watchlist preview from backend
- [ ] Display up to 3 watchlists with scroll support
- [ ] Add view, edit, and delete buttons for each watchlist

**Module**: Frontend  
**Priority**: Medium  
**Status**: Open  

---

## ✅ User Story 3: Get summary metrics for dashboard

### Description
As a user, I want the dashboard to load with all my key metrics in one go, so that I don't wait for multiple API calls.

Subtasks:
- [ ] Create `/dashboard/summary` API endpoint
- [ ] Use MongoDB aggregation to fetch properties, EPCs, ratings, and watchlist count
- [ ] Return metrics in single JSON response

**Module**: Backend  
**Priority**: High  
**Status**: Open  

---

## ✅ User Story 4: See how many properties are being monitored

### Description
As a user, I want to know how many properties I’m monitoring, so that I can track my portfolio size.

Subtasks:
- [ ] Implement backend logic to track portfolio
- [ ] Use MongoDB filter for user-specific properties
- [ ] Write unit test for API response

**Module**: Backend  
**Priority**: Medium  
**Status**: Open  

---

## ✅ User Story 5: Know which EPC ratings are expiring soon

### Description
As a user, I want to know how many EPC ratings are expiring soon, so that I can renew or take action.

Subtasks:
- [ ] Implement backend logic to get the expiring soon epcs
- [ ] Use MongoDB date filters
- [ ] Add support for configurable expiry window

**Module**: Backend  
**Priority**: Medium  
**Status**: Open  

---

## ✅ User Story 6: Understand average EPC rating of my portfolio

### Description
As a user, I want to see the average EPC rating of my properties, so that I can assess overall energy efficiency.

Subtasks:
- [ ] Implement logic to give average EPC rating
- [ ] Calculate average EPC score and convert to grade
- [ ] Return both grade and numeric average

**Module**: Backend  
**Priority**: Medium  
**Status**: Open  

---

## ✅ User Story 7: Know how many watchlists I have

### Description
As a user, I want to know how many watchlists I’ve created, so that I can manage my tracking lists.

Subtasks:
- [ ] Implement backend logic to watchlist count
- [ ] Filter watchlists by `is_active` and user ID
- [ ] Return total count

**Module**: Backend  
**Priority**: Low  
**Status**: Open  

---

## ✅ User Story 8: Manage my watchlists easily

### Description
As a user, I want to view, edit, and delete my watchlists, so that I can organize my property tracking efficiently.

Subtasks:
- [ ] Implement GET, PUT, DELETE APIs for watchlists
- [ ] Support soft-delete using `is_active = false`
- [ ] Add validation and auth check

**Module**: Backend  
**Priority**: High  
**Status**: Open  

---

# 🧾 Epic: Integrate Property Platform APIs in Frontend

### Description
Develop frontend components to integrate and consume APIs from the property platform, enabling a seamless user experience. This includes displaying key metrics, property data, EPC ratings, and watchlist information on the dashboard using real-time or aggregated API responses. The frontend should ensure responsive design, intuitive layout, and efficient data binding for an engaging and performant UI


---

## ✅ User Story 1: Health check integration

**As a** user,  
**I want** the frontend to check the backend service's health status,  
**So that** I am informed when the system is unavailable and can avoid failed operations.

### Subtasks:
- [ ] Create API client for calling `/health` endpoint  
- [ ] Add a health status indicator (green = healthy, red = down) in the app header  
- [ ] Show an error toast/alert if health check fails  
- [ ] Automatically invoke health check on app initialization  

---

## ✅ User Story 2: Search for address

**As a** user,  
**I want** to type in an address or partial address in a search bar,  
**So that** I can find matching properties and select one to view its details.

### Subtasks:
- [ ] Implement `/api/v1/addresses/search` API integration using debounced input  
- [ ] Create a responsive address search bar with autocomplete dropdown  
- [ ] Display a loading spinner during API calls  
- [ ] Show “no results” and error messages appropriately  

---

## ✅ User Story 3: View comprehensive property data

**As a** user,  
**I want** to retrieve and view all available data about a property using its UPRN,  
**So that** I can analyze its full profile in one place.

### Subtasks:
- [ ] Call `/api/v1/property/{uprn}` to get complete property information  
- [ ] Design a detailed property view page (sectioned by data types)  
- [ ] Pass UPRN dynamically from search results or URL route  
- [ ] Add loading state and error boundary for API failures  

---

## ✅ User Story 4: View basic property details

**As a** user,  
**I want** to see the most essential details of a property without extra metadata,  
**So that** I can quickly understand key attributes without distraction.

### Subtasks:
- [ ] Integrate `/api/v1/property/{uprn}/details` endpoint  
- [ ] Display only basic attributes (e.g., address, type, tenure)  
- [ ] Embed this summary in search result previews and overview cards  
- [ ] Provide a "View Full Details" button to navigate to comprehensive data  

---

## ✅ User Story 5: View EPC certificates

**As a** user,  
**I want** to view the EPC (Energy Performance Certificate) data of a property,  
**So that** I can assess its environmental efficiency and energy cost effectiveness.

### Subtasks:
- [ ] Fetch EPC data from `/api/v1/property/{uprn}/epc`  
- [ ] Show EPC rating with visual indicator (e.g., letter scale, color-coded)  
- [ ] Display details such as issue date, expiry date, and assessor name  
- [ ] Handle cases where EPC data is unavailable or expired  

---

## ✅ User Story 6: View Land Registry data

**As a** user,  
**I want** to access land registry titles for a property,  
**So that** I can verify legal ownership and registration history.

### Subtasks:
- [ ] Implement API call to `/api/v1/property/{uprn}/land-registry`  
- [ ] Display title number, date, and ownership status  
- [ ] Add "Download Title" or "View Registry" link (if available)  
- [ ] Provide a fallback UI if no registry data exists  

---

## ✅ User Story 7: View associated companies

**As a** user,  
**I want** to find company information linked to a property,  
**So that** I can understand the ownership structure or managing business entity.

### Subtasks:
- [ ] Consume `/api/v1/property/{uprn}/companies` endpoint  
- [ ] Display company name, registration ID, and active/inactive status  
- [ ] Link to company house or external registry when possible  
- [ ] Handle properties with no associated companies gracefully  

