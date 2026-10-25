**# AWS S3 Static Website**



**A static website hosted on \*\*AWS S3\*\* using Static Website Hosting and a public-read bucket policy. This is my first AWS cloud project.**



**## What I Built**

**I took a free real-estate website template (\*\*Villa\*\*, from TemplateMo) and hosted it on Amazon S3, so it runs without any server.**



**## Tools Used**

**- AWS S3 (static website hosting)**

**- S3 bucket policy (JSON)**

**- HTML / CSS / JavaScript template**



**## Project Details**

**| Item | Value |**

**|---|---|**

**| Bucket name | `amzn-s3-villa` |**

**| Region | Asia Pacific (Mumbai) `ap-south-1` |**

**| Index document | `index.html` |**

**| Access | Public read (`s3:GetObject` only) |**



**## Steps**

**1. Created an S3 bucket named `amzn-s3-villa` in the Mumbai region.**

**2. Turned off \*\*Block Public Access\*\* for this bucket (on purpose, because it's a public website).**

**3. Uploaded the template files: `index.html`, `assets/`, and `vendor/`.**

**4. Enabled \*\*Static website hosting\*\* and set `index.html` as the index document.**

**5. Added a bucket policy that allows public read access.**

**6. Opened the bucket website endpoint to test the site.**



**## Bucket Policy**

**The policy is in \[`bucket-policy.json`](bucket-policy.json). It only allows `s3:GetObject`, so visitors can read the website files but cannot upload, change, or delete anything.**



**## Screenshots**



**\*\*Live website\*\***



**!\[Live website](screenshots/1-live-site.png)**



**\*\*Uploaded objects in the bucket\*\***



**!\[Bucket objects](screenshots/2-objects.png)**



**\*\*Bucket policy\*\***



**!\[Bucket policy](screenshots/3-bucket-policy.png)**



**## Problem I Faced**

**After setting up hosting, the site showed a \*\*403 Forbidden (AccessDenied)\*\* error.**



**\*\*Cause:\*\* Public access was still blocked and the bucket policy was not correctly allowing public reads.**



**\*\*Fix:\*\* I turned off Block Public Access for the bucket, added the correct bucket policy with my bucket name and `/\*` at the end of the resource, and used the \*\*static website endpoint\*\* instead of the normal object URL. After that, the site loaded.**



**## Security Notes**

**- Public access on S3 is a common cloud security mistake, so I enabled it only because this is a public website with no sensitive data.**

**- The policy follows least privilege: `s3:GetObject` only.**

**- No AWS access keys, credentials, or account details are stored in this repository.**

**- The S3 website endpoint uses HTTP, not HTTPS. HTTPS needs CloudFront (see next improvements).**

**- After testing, the bucket can be emptied and deleted so public storage isn't left open.**



**## What I Learned**

**- How S3 static website hosting works**

**- How bucket policies and Block Public Access control access**

**- How to troubleshoot a 403 AccessDenied error**

**- Why least-privilege permissions matter in cloud security**



**## Next Improvements**

**- Add \*\*CloudFront\*\* for HTTPS and faster loading**

**- Use a custom domain with \*\*Route 53\*\***

**- Auto-deploy updates from GitHub to S3 using \*\*GitHub Actions\*\***

**- Keep the bucket private and let only CloudFront read from it (Origin Access Control)**



**## Credits**

**Website template: \*\*Villa\*\* from \[TemplateMo](https://templatemo.com). Template credit and license belong to TemplateMo; please check their license terms before reusing it.**



**## Author**

**\*\*Sumit Jadhav\*\***

**Cybersecurity student | CTF player | Learning Cloud Security \& DevSecOps**

**YouTube: \[@officialhackwithsumit](https://www.youtube.com/@officialhackwithsumit)**

**LinkedIn: www.linkedin.com/in/sumit-jadhav-67090b2a6 | YouTube: www.youtube.com/@officialhackwithsumit**



