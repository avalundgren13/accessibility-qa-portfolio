# accessibility-qa-portfolio
Accessibility test reports and QA artifacts from manual and automatic audits

markdown
# Accessibility Test Report: Wolverine Crossing

**Tester:** Ava Lundgren
**Test Date:** March-April 2026  
**Tools:** Google Chrome, Windows 11, NVDA Screen Reader  
**Standard:** WCAG 2.1 Level AA  

---

## Executive Summary

| Metric | Count |
| :--- | :--- |
| **Total Issues** | 11 |
| **High Severity** | 6 |
| **Moderate Severity** | 5 |
| **Top WCAG Violations** | 1.3.1 (Info & Relationships), 1.4.3 (Contrast), 2.4.4 (Link Purpose) |

**Critical Blockers:** Keyboard inaccessible footer link + screen reader cannot read primary text content.

---

## Test Environment

| Browser | Operating System | Screen Reader |
| :--- | :--- | :--- |
| Google Chrome | Windows 11 | NVDA (for screen reader-specific tests) |

---

## Detailed Findings

| Zone | Defect Summary | User Impact | Severity | WCAG Criterion | Remediation |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Carousel (Interactive Controls)** | Low color contrast on grey carousel navigation links | Users with low vision, color blindness, or age-related vision changes cannot distinguish controls | **High** | 1.4.3 Contrast | Darken the grey background |
| **Subheading** | Low color contrast | Text difficult to read for users with visual impairments | **Moderate** | 1.4.3 Contrast | Lighten the subheading text |
| **Media Player Controls** | Low color contrast | Controls blend into background, unusable for low-vision users | **High** | 1.4.11 Non-text Contrast | Darken the background behind controls |
| **Subheading** | Low color contrast | Poor readability for aging users and those with low vision | **Moderate** | 1.4.3 Contrast | Darken the text |
| **Focus Link on Display Banner** | Link focus is not sufficiently visible | Keyboard users (especially those with low vision) cannot reliably determine what's in focus | **High** | 2.4.7 Focus Visible<br>2.4.11 Focus Appearance | Darken or enlarge the focus indicator |
| **Persistent Footer Element ("Schedule a Tour")** | Link is not accessible by keyboard | Keyboard-only users cannot reach or activate the link | **High** | 2.1.1 Keyboard<br>2.4.3 Focus Order<br>4.1.2 Name, Role, Value | Ensure the link is accessible by keyboard (e.g., native `<a>` tag or `tabindex="0"`) |
| **All Text (Non-Hyperlinks)** | Screen reader announces only hyperlinks, skipping regular text | Screen reader users cannot perceive the primary content of the page | **High** | 1.3.1 Info & Relationships<br>4.1.2 Name, Role, Value<br>2.4.4 Link Purpose | Ensure all text can be read by a screen reader (not hidden or incorrectly coded) |
| **Lower-Page Navigation Area (News & Events)** | Link labeled "News & Events" visually, but screen reader announces as "link to (website page)" | Screen reader users cannot determine what the link does | **High** | 2.4.4 Link Purpose<br>4.1.2 Name, Role, Value<br>1.3.1 Info & Relationships | Ensure the link's visible text ("News & Events") is used as the accessible name |
| **Main Content Area (Heading above UVU Off-Campus Housing Title)** | Page begins with `<h5>` then moves to `<h1>` | Users may be confused or experience difficulty navigating when heading levels are skipped | **Moderate** | 1.3.1 Info & Relationships | Change tags to follow a natural order (e.g., `<h1>` then `<h2>`) |
| **Bottom of Main Content Area** | Starts with `<h1>` then moves to `<h3>` | Heading hierarchy is broken, confusing screen reader navigation | **Moderate** | 1.3.1 Info & Relationships | Change tags to follow a natural order |
| **Heading above "Beautiful Floor Plan" Page** | Page begins with `<h5>` then moves to `<h1>` | Heading levels skipped, disorienting for assistive technology users | **Moderate** | 1.3.1 Info & Relationships | Change tags to follow a natural order |
| **Heading Below "Beautiful Floor Plan" Title** | Jumps from `<h2>` to `<h5>` | Missing intermediate heading levels creates confusion | **Moderate** | 1.3.1 Info & Relationships | Change tags to follow a natural order |

---

## Evidence Artifacts

| Type | Filename | Description |
| :--- | :--- | :--- |
| Screenshot | https://drive.google.com/file/d/1ScJk7CPkvCFMyEZc2dL8k14rb86igyS7/view?usp=sharing | Carousel low contrast issue |
| Screenshot | https://drive.google.com/file/d/1gQAIq-s-Ly45mlX4Bq_TFQcnbivL-M7e/view?usp=sharing | Subheading contrast issue |
| Screenshot | https://drive.google.com/file/d/1C7SYjwl3-BXLETQLBVaX6Q4mpyJGamSB/view?usp=sharing | Media player contrast issue |
| Screenshot | https://drive.google.com/file/d/1k9AlGz5OIZX1lnNHNISedeuQ73QYfDsx/view?usp=sharing | Second subheading contrast issue |
| Screenshot | https://drive.google.com/file/d/1EeI-HtmOE9_JKNL-9qZZv7knbkoMXrki/view?usp=sharing| Focus link visibility issue |
| Screen Recording | https://drive.google.com/file/d/1IjLhjHVEU7HkEyF1PQVxubQWnpo9-vRq/view?usp=sharing | Screen reader skipping non-link text |
| Screen Recording | https://drive.google.com/file/d/1B83P9WkInXECThy1PR9WgE2mFwnIthRs/view?usp=sharing | News & Events link announced incorrectly |
| Screenshot | https://drive.google.com/file/d/1W2mMVqAnyhaL-4KrHQtxPm-VJj1hKk6L/view?usp=sharing | Heading order issue (h5 → h1) |
| Screenshot | https://drive.google.com/file/d/1OajG5FuitSLNLPicsbnrrubnT85N1iU8/view?usp=sharing | Heading order issue (h1 → h3) |
| Screenshot | https://drive.google.com/file/d/13ry-yr6PwA843uFlpABZSh1ZRt9MLoqL/view?usp=sharing | Heading order issue (h5 → h1) |
| Screenshot | https://drive.google.com/file/d/1Pw0HUpxL_EJoyPDVfUzBS8_meckvDKyK/view?usp=sharing | Heading order issue (h2 → h5) |

---

## Skills Demonstrated

- Manual accessibility testing with **NVDA** screen reader
- **WCAG 2.1** criteria identification (Level AA)
- Cross-browser testing (Chrome on Windows 11)
- Defect documentation with severity prioritization
- Clear, actionable remediation recommendations
- Heading structure and semantic HTML analysis
- Color contrast evaluation
- Keyboard navigation testing
- Screen reader compatibility testing

---

## How to Reproduce (Sample Critical Issue)

### Issue: Footer "Schedule a Tour" Link Not Keyboard Accessible

**Steps to Reproduce:**
1. Navigate to the test website
2. Press the `Tab` key repeatedly until reaching the page footer
3. Observe that the "Schedule a Tour" link never receives focus

**Expected Result:** The link should be reachable and activatable with the `Enter` key

**Observed Result:** Focus jumps from the previous element directly to the next, skipping this link entirely
