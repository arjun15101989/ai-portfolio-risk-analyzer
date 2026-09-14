# 📈 Project 1: Basic Stock Watchlist Mobile Test Automation


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🏛️ Domain Context: Stock Watchlist & Tickers
In financial and trading mobile applications, real-time data integrity and UI responsive filtering are mission-critical. Project 1 validates:
* **Real-Time Ticker Rendering:** Verifying immediate search filtering and detail page routing.
* **Visual Market Signals:** Confirming positive gain indicators (Green) vs. negative loss indicators (Red).
* **Watchlist Data Mutations:** Ensuring stock additions, removals, drag-and-drop reordering, and session resets function without state corruption.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

mobile_automation/
├── .github/
│   └── workflows/
│       └── robot_ci.yml
├── resources/
│   ├── locators.resource
│   └── watchlist_keywords.resource
├── results/
│   ├── log.html
│   └── report.html
├── tests/
│   └── test_watchlist.robot
├── .gitignore
└── README.md

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
🧪 Acceptance Criteria (AC) Matrix (FIN-101)
Below is the complete 18 Acceptance Criteria (AC) list for Project 1: The Basic Stock Watchlist, formatted in clear, scannable bullet points:

AC-01: Default Watchlist Load

Description: The default market watchlist must load within 5 seconds upon application launch, displaying standard stock tickers (e.g., AAPL, GOOGL, MSFT).

Target Robot Keyword / Validation: Wait Until Element Is Visible


AC-02: Valid Ticker Search

Description: Searching a valid stock symbol (e.g., "AAPL") dynamically filters the list and returns the matching company name.

Target Robot Keyword / Validation: Input Text & Page Should Contain Element


AC-03: Invalid Ticker Search

Description: Searching a non-existent stock symbol (e.g., "INVALID123") renders an empty-state message ("No Stocks Found").

Target Robot Keyword / Validation: Element Text Should Be


AC-04: Special Character Input

Description: Entering special characters (e.g., @#$%^&*) into the search bar is handled gracefully without crashing or freezing the app.

Target Robot Keyword / Validation: Run Keyword And Return Status


AC-05: Add Stock to Watchlist

Description: Tapping the "+" icon on a searched asset successfully adds it to the user's active watchlist.

Target Robot Keyword / Validation: Click Element & List Should Contain Value


AC-06: Remove Stock from Watchlist

Description: Swiping left or tapping "Delete" on an active ticker removes it permanently from the list.

Target Robot Keyword / Validation: Swipe & Page Should Not Contain Element


AC-07: Real-Time Bullish Indicator

Description: Tickers with positive percentage changes (gains) render price indicators in Green (#008000).

Target Robot Keyword / Validation: Get Element Attribute (color)

AC-08: Real-Time Bearish Indicator

Description: Tickers with negative percentage changes (losses) render price indicators in Red (#FF0000).

Target Robot Keyword / Validation: Get Element Attribute (color)

AC-09: Currency Symbol Formatting

Description: Ticker price values strictly display appropriate regional market currency prefixes (e.g., $, ₹, €).

Target Robot Keyword / Validation: Element Should Contain


AC-10: Pull-to-Refresh Data Update

Description: Executing a downward swipe gesture re-queries backend APIs and updates the "Last Refreshed" timestamp.

Target Robot Keyword / Validation: Swipe By Percent & Element Text Should Be


AC-11: Watchlist Item Drag & Reorder

Description: Long-pressing and dragging a stock item alters its ordinal position in the saved watchlist index.

Target Robot Keyword / Validation: Custom Python Gesture Keyword

AC-12: Navigation to Stock Detail

Description: Tapping any stock ticker item routes the user directly to its corresponding detailed interactive chart page.

Target Robot Keyword / Validation: Click Element & Wait Until Location Contains


AC-13: Clear Search Persistence

Description: Tapping the "X" button inside the search field clears the text query and restores the default ticker view.

Target Robot Keyword / Validation: Clear Element Text & Element Should Be Visible


AC-14: Max Capacity Alert

Description: Attempting to add more than 50 stocks triggers a modal pop-up: "Watchlist Limit Reached".

Target Robot Keyword / Validation: Handle Alert / Wait Until Element Is Visible


AC-15: Network Interruption Handling

Description: Disabling network connectivity displays an inline banner: "Network Unavailable – Showing Cached Data".

Target Robot Keyword / Validation: Page Should Contain


AC-16: App Background & Resume

Description: Moving the app to the background for 10 seconds and resuming preserves active search state and loaded tickers.

Target Robot Keyword / Validation: Background App & Element Should Be Visible


AC-17: Decimal Precision Verification

Description: All stock market prices display rounded strictly to two decimal places (e.g., $182.50).

Target Robot Keyword / Validation: Custom Regex Match Keyword

AC-18: Session Reset & Cleanup

Description: Re-launching or resetting the application returns all watchlist configurations to their default state.

Target Robot Keyword / Validation: Reset Application / Close Application

----------------------------------------------------------------------------------------------------------------------------------------------------
