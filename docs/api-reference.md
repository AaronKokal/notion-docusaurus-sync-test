---
title: Configuration API Reference
slug: api-reference
description: Complete reference for all configuration options
sidebar_label: API Reference
sidebar_position: 3
tags:
  - reference
  - api
date: "2026-02-06"
---

## SyncConfig Options

The following table describes all available configuration options:

| Option | Type | Description |
| --- | --- | --- |
| notionToken | string | Notion integration secret token |
| databaseId | string | ID of the Notion database to sync |
| conflictStrategy | string | latest-wins | notion-wins | git-wins |

## Conflict Strategies

1. **`latest-wins`** — Compares timestamps, the most recent edit takes precedence
2. **`notion-wins`** — Notion content always overwrites Git
3. **`git-wins`** — Git content always overwrites Notion

> The default strategy is latest-wins, which is suitable for most use cases where only one person edits at a time.