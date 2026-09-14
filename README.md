# 📈 Project 1: Basic Stock Watchlist Mobile Test Automation


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🏛️ Domain Context: Stock Watchlist & Tickers
In financial and trading mobile applications, real-time data integrity and UI responsive filtering are mission-critical. Project 1 validates:
* **Real-Time Ticker Rendering:** Verifying immediate search filtering and detail page routing.
* **Visual Market Signals:** Confirming positive gain indicators (Green) vs. negative loss indicators (Red).
* **Watchlist Data Mutations:** Ensuring stock additions, removals, drag-and-drop reordering, and session resets function without state corruption.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Acceptance Criteria (AC) MatrixAC IDTitleDescription & Verification StrategyTarget Robot Keyword / ValidationAC-01Default Watchlist LoadDefault market watchlist loads within 5s displaying standard tickers.Wait Until Element Is VisibleAC-02Valid Ticker SearchSearching "AAPL" filters list and returns matching company name.Input Text & Page Should Contain ElementAC-03Invalid Ticker SearchSearching "INVALID123" renders empty-state "No Stocks Found".Element Text Should BeAC-04Special Character InputSpecial characters (@#$%^&*) are handled gracefully without crash.Run Keyword And Return StatusAC-05Add Stock to WatchlistTapping "+" adds searched asset to user's active watchlist.Click Element & List Should Contain ValueAC-06Remove StockSwiping left or tapping "Delete" removes ticker from list.Swipe & Page Should Not Contain ElementAC-07Bullish IndicatorTickers with positive gains render price indicators in Green.Get Element Attribute (color)AC-08Bearish IndicatorTickers with losses render price indicators in Red.Get Element Attribute (color)AC-09Currency PrefixTicker price values display valid regional currency prefixes ($).Element Should ContainAC-10Pull-to-RefreshDownward swipe gesture re-queries backend APIs and updates timestamp.Swipe By Percent & Element Text Should BeAC-11Drag & ReorderLong-pressing and dragging alters ticker ordinal index.Custom Python Gesture KeywordAC-12Stock Detail RouteTapping a ticker routes to detailed interactive chart page.Click Element & Wait Until Location ContainsAC-13Clear PersistenceTapping "X" clears search query and restores default tickers.Clear Element Text & Element Should Be VisibleAC-14Max Capacity AlertExceeding 50 stocks triggers "Watchlist Limit Reached" alert.Handle Alert / Wait Until Element Is VisibleAC-15Offline BannerDisabling network displays "Network Unavailable – Showing Cached Data".Page Should ContainAC-16Background & ResumeMoving app to background for 10s preserves active state.Background App & Element Should Be VisibleAC-17Decimal PrecisionPrices strictly render rounded to 2 decimal places ($182.50).Custom Regex Match KeywordAC-18Session ResetResetting app returns all watchlist configurations to default state.Reset Application / Close Application


----------------------------------------------------------------------------------------------------------------------------------------------------
## 📂 Project Architecture & File Hierarchy

mobile_automation/
├── .github/
│   └── workflows/
│       └── robot_ci.yml              # GitHub Actions CI Workflow
├── resources/
│   ├── locators.resource            # UI Locators (Accessibility ID, XPath, ID)
│   └── watchlist_keywords.resource   # Reusable Domain-Specific Keywords
├── results/                          # Execution Artifacts (log.html, report.html)
├── tests/
│   └── test_watchlist.robot          # Project 1 Core Test Suite (18 Acceptance Criteria)
├── .gitignore                        # Git Exclusions (venv, logs, binaries)
└── README.md                         # Project Documentation
