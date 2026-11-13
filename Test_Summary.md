# Test Execution Summary

## Scope
Manual functional testing of [SauceDemo](https://www.saucedemo.com/) in Google Chrome, based on the recorded Lab 1 execution results. Coverage includes login, validation, cart operations, and price sorting. No new test execution was performed while organizing this portfolio.

## Results

| Metric | Count |
|---|---:|
| Documented test cases | 9 |
| Passed (lab results) | 9 |
| Failed (lab results) | 0 |
| Test cases with supplied screenshot evidence | 9 |
| Test cases awaiting screenshots | 0 |

The original report lists eight passed cases and records a successful locked-out-user challenge. The latter is included as TC009 and classified as passed because the observed result matches the expected result.

## Evidence traceability

| Test case | Scenario | Lab status | Screenshot evidence | Observation |
|---|---|---|---|---|
| TC001 | Valid login | Pass | [Login input](screenshots/TC001_01_Valid_Login_Input.png) · [Products page](screenshots/TC001_02_Products_Page.png) | Products page displayed after login. |
| TC002 | Invalid password | Pass | [Error message](screenshots/TC002_Invalid_Password.png) | Login rejected with username/password mismatch error. |
| TC003 | Empty username | Pass | [Validation message](screenshots/TC003_Empty_Username.png) | Username is required message displayed. |
| TC004 | Empty password | Pass | [Validation message](screenshots/TC004_Empty_Password.png) | Password is required message displayed. |
| TC005 | Add product to cart | Pass | [Cart count](screenshots/TC005_Cart_Count.png) | Cart badge shows 1; the screenshot does not show the product name. |
| TC006 | View shopping cart | Pass | [Cart contents](screenshots/TC006_View_Cart.png) | Sauce Labs Backpack, quantity 1, price $29.99 displayed. |
| TC007 | Remove product | Pass | [Empty cart](screenshots/TC007_Empty_Cart.png) | Cart is empty and the badge count is no longer displayed. |
| TC008 | Sort by price (low to high) | Pass | [Sort selection](screenshots/TC008_01_Price_Sort_Selection.png) · [Sorted products](screenshots/TC008_02_Sorted_Products.png) | Dropdown highlights low-to-high; the subsequent screenshot shows $7.99, $9.99, $15.99 and $15.99 in ascending order. |
| TC009 | Locked-out user login | Pass | [Lockout message](screenshots/TC009_Locked_Out_User.png) | Login rejected with locked-out user message. |

## Observations and limitations
- No functional defects were reported in the original lab for these scenarios.
- The invalid-password screenshot appears to show text extending beyond the red error-message container. This is a possible UI issue for separate reproduction and viewport verification, not a confirmed defect or an executed additional test. The functional authentication result remains Pass.
- TC004 now has a screenshot of the expected error. TC008 has two screenshots showing the sort selection and four visible products in nondecreasing price order; the remaining products are outside the captured view. The overall Pass status is based on the original lab.
- Screenshots were supplied by the tester and are preserved as captured. Some are cropped. They document visible outcomes but do not independently establish every step or input value.
- Testing was limited to the scenarios documented in the workbook. No checkout, cross-browser, performance, security or automated testing coverage is claimed.

## Next steps
1. Capture the complete sorted product list during a future run for full price-order evidence.
2. Recheck the possible invalid-password message clipping at a documented viewport size.
3. Automate core login and cart regression scenarios using Selenium WebDriver in a future project.
