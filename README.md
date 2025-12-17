# RadioFlux - Content Moderation & Configuration

This repository contains the content moderation configuration files for the **RadioFlux** mobile application. It serves as a transparent and publicly auditable system for managing filtered radio stations.

## Purpose

RadioFlux is a radio streaming application that aggregates stations from the [RadioBrowser](https://www.radio-browser.info/) community database. To ensure compliance with [Google Play Developer Program Policies](https://play.google.com/about/developer-content-policy/) and provide a safe listening experience, certain stations may be filtered based on the following criteria:

- **Hate Speech**: Content promoting hatred, violence, or discrimination
- **Illegal Content**: Content violating applicable laws and regulations
- **Copyright Violations**: Unauthorized distribution of copyrighted material
- **Adult Content**: Explicit content not suitable for general audiences

## How to Report a Station

If you encounter a radio station in the RadioFlux app that you believe violates content policies, you can report it by:

1. **Opening an Issue** on this repository: [Create New Issue](../../issues/new)
2. Include the following information:
   - Station name
   - Station UUID (if available, found in the app's station details)
   - Stream URL (if known)
   - Reason for the report
   - Any supporting evidence or description

All reports will be reviewed and processed in a timely manner.

## Blacklist File Structure

The `blacklist.json` file contains the list of filtered stations with the following structure:

```json
{
  "version": "1.0.0",
  "lastUpdated": "2025-12-17T00:00:00Z",
  "stations": [
    {
      "id": "radiobrowser-station-uuid",
      "reason": "reason_code",
      "addedDate": "YYYY-MM-DD",
      "note": "Optional description"
    }
  ],
  "urls": [
    {
      "pattern": "http://stream-url-to-block.com/stream",
      "reason": "reason_code",
      "addedDate": "YYYY-MM-DD",
      "note": "Optional description"
    }
  ]
}
```

### Fields Description

| Field | Description |
|-------|-------------|
| `version` | Semantic version of the blacklist format |
| `lastUpdated` | ISO 8601 timestamp of last modification |
| `stations` | Array of stations blocked by RadioBrowser UUID |
| `urls` | Array of stream URLs blocked by pattern matching |
| `reason` | Code indicating the violation type |
| `addedDate` | Date when the entry was added |
| `note` | Optional human-readable explanation |

### Reason Codes

| Code | Description |
|------|-------------|
| `hate_speech` | Content promoting hatred or violence |
| `illegal_content` | Content violating laws and regulations |
| `copyright_violation` | Unauthorized copyrighted material |
| `adult_content` | Explicit adult content |

## Transparency

This repository is public to ensure transparency in our moderation practices. Users and developers can:

- View the complete list of filtered stations
- Understand the reasons for each filtering decision
- Contribute by reporting problematic content
- Appeal decisions by opening an issue

## License

This configuration repository is maintained by the RadioFlux development team.

---

*Last updated: December 2025*
