# TaskBoard

## 1. View portfolio overview on dashboard

### Description
As a user, I want to view a responsive dashboard that shows key metrics like properties monitored, EPCs expiring soon, average EPC rating, and watchlists, so that I can quickly understand my portfolio status.

Subtasks:
- Design responsive dashboard layout (React)
- Display total properties monitored in a card
- Show count of expiring EPCs (next 90 days)
- Display average EPC rating (letter grade with visual indicator)
- Show count of watchlists with clickable view

**Module**: Frontend  
**Priority**: High  
**Status**: Open  

---

## 2. Access recent watchlists from dashboard

### Description
As a user, I want to view my recent watchlists on the dashboard, so that I can quickly access them without navigating away.

Subtasks:
- Fetch watchlist preview from backend
- Display up to 3 watchlists with scroll support
- Add view, edit, and delete buttons for each watchlist

**Module**: Frontend  
**Priority**: Medium  
**Status**: Open  

---

## 3. Get summary metrics for dashboard

### Description
As a user, I want the dashboard to load with all my key metrics in one go, so that I don't wait for multiple API calls.

Subtasks:
- Create `/dashboard/summary` API endpoint
- Use MongoDB aggregation to fetch properties, EPCs, ratings, and watchlist count
- Return metrics in single JSON response

**Module**: Backend  
**Priority**: High  
**Status**: Open  

---

## 4. See how many properties are being monitored

### Description
As a user, I want to know how many properties I’m monitoring, so that I can track my portfolio size.

Subtasks:
- Implement `/properties/count` API
- Use MongoDB filter for user-specific properties
- Write unit test for API response

**Module**: Backend  
**Priority**: Medium  
**Status**: Open  

---

## 5. Know which EPC ratings are expiring soon

### Description
As a user, I want to know how many EPC ratings are expiring soon, so that I can renew or take action.

Subtasks:
- Create `/properties/expiring_soon?days=90` endpoint
- Use MongoDB date filters
- Add support for configurable expiry window

**Module**: Backend  
**Priority**: Medium  
**Status**: Open  

---

## 6. Understand average EPC rating of my portfolio

### Description
As a user, I want to see the average EPC rating of my properties, so that I can assess overall energy efficiency.

Subtasks:
- Implement `/properties/average_epc` API
- Calculate average EPC score and convert to grade
- Return both grade and numeric average

**Module**: Backend  
**Priority**: Medium  
**Status**: Open  

---

## 7. Know how many watchlists I have

### Description
As a user, I want to know how many watchlists I’ve created, so that I can manage my tracking lists.

Subtasks:
- Build `/watchlists/count` endpoint
- Filter watchlists by `is_active` and user ID
- Return total count

**Module**: Backend  
**Priority**: Low  
**Status**: Open  

---

## 8. Manage my watchlists easily

### Description
As a user, I want to view, edit, and delete my watchlists, so that I can organize my property tracking efficiently.

Subtasks:
- Implement GET, PUT, DELETE APIs for watchlists
- Support soft-delete using `is_active = false`
- Add validation and auth check

**Module**: Backend  
**Priority**: High  
**Status**: Open  
