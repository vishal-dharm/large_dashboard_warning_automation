# Large Dashboard Warning Automation

## Overview

This repository contains a script which shows how to add a warning text tile to all dashboards with more than 25 queries.

## Background

One of the biggest contributors to poor dashboard and, in general, Looker performance is large dashboards. There is no hard and fast rule about the number, since the design of a single element impacts its memory consumption based on a few factors (covered later on this page). However, avoid creating dashboards with 25 or more queries. Keep dashboard performance slick by creating navigation links between dashboards or by [creating links to custom URLs](https://cloud.google.com/looker/docs/reference/param-field-link) to create a curated navigation from dashboard to dashboard. You can also try concatenating similar measures into the same single value visualization to avoid many single tile visualizations ([ref](https://cloud.google.com/looker/docs/best-practices/considerations-when-building-performant-dashboards)).

## Automation

To automate this process, you can put this script in a [Cloud Function](https://cloud.google.com/functions) and trigger it at the desired cadence with [Cloud Scheduler](https://cloud.google.com/scheduler).

## Caveats

Before running this script on your production Looker instance, you should strongly consider adding error handling and retry logic.
