---
title: Getting Started with Notion Sync
slug: getting-started
description: Learn how to set up and use the Notion-Docusaurus sync tool
sidebar_label: Tutorials
sidebar_position: 1
tags:
  - getting-started
  - tutorial
date: "2026-02-06"
---

## Introduction

NOTION T173: Should WIN with notion-wins even though Git was edited more recently.

### Prerequisites

- Node.js 20 or later
- A Notion integration token
- A Docusaurus project (v3 recommended)

## Installation

Install the sync tool via npm:

```bash
npm install notion-docusaurus-sync
```

## Configuration

Create a configuration file in your project root:

```typescript
// sync.config.ts
export default {
  notionToken: process.env.NOTION_TOKEN,
  databaseId: "your-database-id",
  outputDir: "./docs",
  conflictStrategy: "latest-wins",
};
```

:::tip

Tip: Store your Notion token in a .env file and never commit it to version control.

:::

## T169 Notion Should Lose (v3)

NOTION v7: Should be overwritten by git-wins.