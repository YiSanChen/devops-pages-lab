# DevOps Pages Lab: Low-Risk Release Pipeline (O-Level)

This repository serves as a demonstration of static site publishing using GitHub Pages, coupled with an automated CI/CD pipeline built with GitHub Actions to integrate a real-time activity log. This design aims to achieve the "Low-Risk Release" objective by ensuring the publicly deployed artifact is always synchronized with the latest source code activity.

## ⚙️ Automated Pipeline Mechanism (O-Level Documentation)

This section documents the CI/CD configuration used for automated content generation and controlled deployment synchronization.

## 1. Automated Content Generation (E-Level Core)

Workflow: .github/workflows/activity-log.yml

Action: Uses TheDanniCraft/activity-log@v1 to fetch recent GitHub events from the YiSanChen profile.

Injection Point: The log is automatically inserted into the designated placeholder block (<!--START_SECTION:activity-->) within this README.md file.

## 2. Deployment Synchronization & Scheduling (O-Level Hygiene & Rationale)

Controlled Triggering: The workflow trigger on: push has been removed to prevent execution on every source code change. This maintains clean repository hygiene by separating code commits from content generation.

Scheduling Rationale: The workflow is scheduled to run twice daily (8:00 AM and 8:00 PM UTC). This frequency is chosen to maintain activity log freshness without over-consuming build resources.

Low-Risk Deployment: The automated content is rendered on the Live URL via Jekyll's inclusion of this README.md in index.md, making the public site a direct, near real-time reflection of the repository's state.

## 🎯 專案活動紀錄 (Auto-Generated)

<!--START_SECTION:activity-->

<!--END_SECTION:activity-->

(The content between the activity markers is automatically updated by the GitHub Action.)
