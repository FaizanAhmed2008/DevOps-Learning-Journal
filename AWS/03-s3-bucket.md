# AWS S3 (Simple Storage Service)

## Key Concepts
- **S3 Bucket**: Object storage container for files, media, backups, and static content.
- **Objects**: Individual files stored in buckets (consists of key, data, and metadata).
- **Globally Unique Name**: Bucket names must be unique across all AWS accounts globally.
- **Storage Classes**:
  - **Standard**: Frequently accessed data.
  - **Intelligent-Tiering**: Automatic cost optimization.
  - **Standard-IA**: Infrequently accessed data (lower cost, retrieval fee).
  - **Glacier / Glacier Deep Archive**: Low-cost long-term archival.

## Commands (AWS CLI)
- List all buckets:
  - `aws s3 ls`
- List contents of a bucket:
  - `aws s3 ls s3://<bucket-name>`
- Create a bucket:
  - `aws s3 mb s3://<bucket-name>`
- Upload a file to bucket:
  - `aws s3 cp <filename> s3://<bucket-name>/`
- Sync local directory with bucket:
  - `aws s3 sync ./<local-folder> s3://<bucket-name>/`
- Delete a file:
  - `aws s3 rm s3://<bucket-name>/<filename>`
- Delete a bucket:
  - `aws s3 rb s3://<bucket-name>`

## Notes
- **Versioning**: Protects against accidental deletion by keeping past object revisions.
- **Static Website Hosting**: Serve static HTML/CSS/JS web pages directly from a bucket.
- **Security**: Public access is blocked by default; access is managed via Bucket Policies and IAM.
