---
title: Sync Architecture Overview
slug: architecture
description: How the bidirectional sync engine works under the hood
sidebar_label: Guides
sidebar_position: 2
tags:
  - guide
  - reference
date: "2026-02-06"
---

## Overview

The sync engine operates as an external CLI tool that runs before Docusaurus builds. It reads from a Notion database and writes markdown files to your docs directory — and vice versa.

## Data Flow

The bidirectional sync follows this flow:

1. Sync engine checks both Notion and Git for changes since last sync
2. Pages changed only on one side are synced normally
3. Pages changed on both sides trigger conflict resolution
4. All changes and conflicts are logged for auditability

---

## Key Design Decisions

**Page-level sync**: The unit of sync is one Notion page = one markdown file. When a page changes, the entire page is re-synced rather than attempting block-level diffing.

**Incremental by default**: Only pages that have changed since the last sync are processed. Full re-sync is available as a flag.

> The sync tool writes .md/.mdx files to a configurable output directory. Docusaurus processes them as regular docs — no custom plugins required.