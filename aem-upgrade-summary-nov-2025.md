---
title: "What's New in AEM? A Summary of the Latest Updates (November 2025)"
description: "Stay current with the latest AEM updates. This summary covers AEM as a Cloud Service, AEM 6.5 Standard, and AEM 6.5 LTS releases from November 2025, including Java 21 support, accessibility improvements, and security enhancements."
pubDate: 2024-11-26T00:00:00.000Z
author: "Infiniumtek Team"
category: "AEM"
tags: ["aem", "aem-6.5", "aem-cloud", "updates", "releases"]
draft: false
---

**By Infinium Technologies** *Read Time: ~5 Minutes*

Keeping your digital experience platform up to date is critical for security, performance, and access to the latest features. It is important to note that **AEM 6.5 Standard** and **AEM 6.5 LTS** follow different release cadences and feature sets.

Here is your quick digest of the latest updates for each platform.

---

## 1. AEM as a Cloud Service (Release 2025.11.0)
**Release Date:** November 20, 2025

The cloud platform continues its monthly innovation cadence with significant updates to its foundation and Forms capabilities.

### **Key Infrastructure & Foundation Changes**
* **Java 21 Runtime Upgrade:** Stage and Production environments have been upgraded to **Java 21**. Note that **Java 11 support is being deprecated**; support will end in late January 2025.
* **Log Configuration Enforcement:** Custom log configurations will be ignored starting **December 10, 2025**.

### **New Features & Betas**
* **Forms Enhancements:** Includes "Template Locking" for brand consistency, in-browser XDP file editing, and better content overflow support.
* **Beta Programs:** New betas for **Edge Computing** (executing JavaScript at the CDN layer) and **AI Answers** (RAG-powered search).

[**Read the AEM Cloud Service Release Notes**](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current?lang=en)

---

## 2. AEM 6.5 Standard (Service Pack 24)
**Version:** 6.5.24.0
**Release Date:** November 26, 2025

For customers on the **Standard** release track, Service Pack 24 brings a massive wave of stability fixes, specifically targeting accessibility compliance and backend security.

### **Update Highlights**
* **Accessibility & Usability Overhaul (Sites):** This release includes extensive updates to ensure WCAG 2.1 compliance.
    * **Keyboard Navigation:** Full keyboard support has been restored for critical UI elements, including the "Switch display format" dialog, ContextHub buttons, and the Filters rail.
    * **Assistive Technology:** Improved screen reader announcements for search results, loading states, and side rails to ensure a seamless authoring experience for all users.
    * **Responsive Fixes:** UI elements now remain fully visible and usable at high zoom levels (400%) and on small viewports (320px).
* **Assets & Workflow Stability:**
    * **Sorting Fixes:** Resolved critical issues where sorting folders by "Modification Date" in Card View would fail, making it difficult to locate recently modified assets.
    * **Sync Accuracy:** Fixed a synchronization bug where assets from a remote DAM would incorrectly display a "Not Published" status on the local Sites instance.
* **Forms Security & Infrastructure:**
    * **Struts Upgrade:** The underlying Struts library has been upgraded to **version 6.x**, addressing multiple security vulnerabilities and ensuring smoother performance.
    * **Upgrade Stability:** Patched JSP compilation errors that were blocking users from upgrading to newer Service Packs.

[**Read the AEM 6.5 Release Notes**](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/release-notes/release-notes?lang=en)

---

## 3. AEM 6.5 LTS (Long Term Support)
**Current Version:** LTS Service Pack 1 (6.5.LTS.SP1)
**Release Date:** August 28, 2025

**Note:** The LTS track does *not* consume the standard Service Pack 24. Instead, it operates on a separate, stabilized baseline. The current active release is **LTS Service Pack 1**, which introduces major infrastructure modernizations.

### **LTS Update Highlights**
* **Native Java 21 & 17 Support:** AEM 6.5 LTS SP1 brings full support for **Java 21** (and Java 17), offering significant performance improvements (ZGC garbage collection, faster startup) and long-term security compliance.
* **Modernized Codebase & Security:** This release removes legacy dependencies to reduce vulnerabilities.
    * **Library Removals:** The **Guava** library and **Commons Collections 3.x** have been removed from the baseline. Custom code relying on these must be refactored to use standard Java APIs or updated libraries.
    * **Upgraded Stack:** Includes updates to the **Jetty** servlet engine and **Jackson** libraries to meet modern security standards.
* **Stability Baseline:** LTS SP1 consolidates the stability fixes from AEM 6.5 Service Pack 22, serving as the new "master" baseline for future LTS patches.
* **Next Scheduled Update:** The next major LTS update (LTS Service Pack 2) is currently targeted for **February 2026**.

[**Read the AEM 6.5 LTS Release Notes**](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/release-notes/release-notes?lang=en)

---

## Need Help Navigating These Updates?

Whether you need to clarify your upgrade path between Standard and LTS, migrate to the Cloud, or optimize your platform's performance, **Infinium Technologies** is here to assist.

Our team specializes in Adobe Experience Manager solutions tailored to your business needs.

* **Explore our Expertise:** [**AEM Services**](https://infiniumtek.com/services/aem/)
* **Get in Touch:** [**Contact Us**](https://infiniumtek.com/contact/)