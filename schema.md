# Airtable schema

The two tables the n8n workflow writes to.

## Imported Jobs

| Field | Type | Source (Remotive API) |
|---|---|---|
| Job Title | Single line text | `title` |
| Company Name | Single line text | `company_name` |
| Category | Single line text | `category` |
| Employment Type | Single select: `full_time`, `part_time`, `contract`, `freelance`, `internship` | `job_type` |
| Candidate Required Location | Single line text | `candidate_required_location` |
| Publication Date | Single line text (YYYY-MM-DD) | `publication_date` (date part only) |
| Listing URL | URL | `url` |
| **Remotive Job ID** | Single line text | `id`, **the upsert match key** |
| Salary | Single line text | `salary`, or "Not specified" |
| Description | Long text | `description` with HTML removed, first 500 characters |
| Linked Client | Link to Clients | Set manually in Airtable, not by the workflow |

## Sync Log

| Field | Type | Example |
|---|---|---|
| Run Timestamp | Single line text | `2026-09-20 09:00` |
| Run Status | Single line text | `Success` / `Failed` |
| Message | Long text | `Import completed successfully. 27 job(s) processed…` |
| Jobs Processed | Number | `27` |
