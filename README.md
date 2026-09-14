# 📈 Project 1: Basic Stock Watchlist Mobile Test Automation


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🏛️ Domain Context: Stock Watchlist & Tickers
In financial and trading mobile applications, real-time data integrity and UI responsive filtering are mission-critical. Project 1 validates:
* **Real-Time Ticker Rendering:** Verifying immediate search filtering and detail page routing.
* **Visual Market Signals:** Confirming positive gain indicators (Green) vs. negative loss indicators (Red).
* **Watchlist Data Mutations:** Ensuring stock additions, removals, drag-and-drop reordering, and session resets function without state corruption.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Acceptance Criteria (AC) Matrix (FIN-101)
AC ID	Feature Title	Scenario Description & Verification Logic	Target Robot Keyword / Validation
AC-01	Default Watchlist Load	
Default market watchlist loads within 5s displaying standard tickers

Wait Until Element Is Visible
AC-02	Valid Ticker Search	
Searching "AAPL" filters list and returns matching company name.

Input Text & Page Should Contain Element
AC-03	Invalid Ticker Search	
Searching "INVALID123" renders empty-state "No Stocks Found".

Element Text Should Be
AC-04	Special Character Input	
Special characters (@#$%^&*) are handled gracefully without crash.

Run Keyword And Return Status
AC-05	Add Stock to Watchlist	
Tapping "+" adds searched asset to user's active watchlist.

Click Element & List Should Contain Value
AC-06	Remove Stock	
Swiping left or tapping "Delete" removes ticker from list.

Swipe & Page Should Not Contain Element
AC-07	Bullish Indicator	
Tickers with positive gains render price indicators in Green.

Get Element Attribute (color)
AC-08	Bearish Indicator	
Tickers with losses render price indicators in Red.

Get Element Attribute (color)
AC-09	Currency Prefix	
Ticker price values display valid regional currency prefixes ($).

Element Should Contain
AC-10	Pull-to-Refresh	
Downward swipe gesture re-queries backend APIs and updates timestamp.

Swipe By Percent & Element Text Should Be
AC-11	Drag & Reorder	
Long-pressing and dragging alters ticker ordinal index.

Custom Python Gesture Keyword
AC-12	Stock Detail Route	
Tapping a ticker routes to detailed interactive chart page.

Click Element & Wait Until Location Contains
AC-13	Clear Persistence	
Tapping "X" clears search query and restores default tickers.

Clear Element Text & Element Should Be Visible
AC-14	Max Capacity Alert	
Exceeding 50 stocks triggers "Watchlist Limit Reached" alert.

Handle Alert / Wait Until Element Is Visible
AC-15	Offline Banner	
Disabling network displays "Network Unavailable – Showing Cached Data".

Page Should Contain
AC-16	Background & Resume	
Moving app to background for 10s preserves active state.

Background App & Element Should Be Visible
AC-17	Decimal Precision	
Prices strictly render rounded to 2 decimal places ($182.50).

Custom Regex Match Keyword
AC-18	Session Reset	
Resetting app returns all watchlist configurations to default state.

Reset Application / Close Application


----------------------------------------------------------------------------------------------------------------------------------------------------
mobile_automation/
├── .github/
│   └── workflows/
│       └── robot_ci.yml              # GitHub Actions CI Workflow
├── resources/
│   ├── locators.resource            # UI Locators (Accessibility ID, XPath, ID)
│   └── watchlist_keywords.resource   # Reusable Robot Keywords
├── results/                          # Execution Logs (log.html, report.html)
├── tests/
│   └── test_watchlist.robot          # Project 1 Suite (18 Acceptance Criteria)
├── .gitignore                        # Environment & Artifact Exclusions
└── README.md                         # Project Documentation
