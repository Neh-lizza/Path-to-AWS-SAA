THE PATH TO AWS ASSOCIATE
Static website project for Amazon S3 (clay design system rebrand + blog)

FILES
- index.html: homepage (field notes, roadmap, projects, blog preview, journal, about)
- blog.html: blog index with search and topic filters
- styles.css: shared design system (colours, type, buttons, cards, header/footer)
- script.js: mobile navigation, article search, category filters, scroll-in animation
- article.css: long-form article layout
- extras.css: learning path, journal, and blog page styles
- articles/s3-static-website.html: S3 hosting tutorial
- articles/networking-cidr.html: CIDR and subnetting primer
- articles/cloud-fundamentals.html: cloud computing primer
- articles/iam-roles-vs-users.html: blog post on IAM
- articles/scps-explained.html: blog post on SCPs and Control Tower
- articles/security-groups-vs-nacls.html: blog post on VPC firewalls
- learning-path.html: structured study roadmap
- journal.html: honest learning journal template

DESIGN TOKENS
Colours, fonts, and shadows live in :root at the top of styles.css
(--marine, --red, --butter, --stone, --clay). Fonts: Fredoka, Figtree, DM Mono (Google Fonts).

ADD A BLOG POST
1. Copy any file in articles/ and rename it.
2. Replace the title, description, and body text.
3. Copy one <article class="article-card"> block in blog.html and update the link,
   data-category (fundamentals, networking, storage, security) and data-search keywords.
4. Upload the changed files to your S3 bucket.

PREVIEW LOCALLY
1. Extract the ZIP file.
2. From the project folder run: python -m http.server 8000
3. Open http://localhost:8000

DEPLOY TO AMAZON S3
1. Create a dedicated S3 bucket with a globally unique name.
2. Upload all project files and folders while preserving the folder structure.
3. In bucket Properties, enable Static website hosting and set index.html as the index document.
4. If using the direct S3 website endpoint, configure public read access only after reviewing the security implications and current AWS documentation. Never grant public write access.
5. Open the website endpoint shown in the Static website hosting section.
6. Test navigation, article links, CSS, search, and filters.
7. Delete the lab bucket when you no longer need it, after confirming it contains no needed files.

IMPORTANT SECURITY NOTE
Direct S3 static website endpoints use HTTP, not HTTPS. For a production site that needs HTTPS, prefer CloudFront with a private S3 origin and Origin Access Control. Account-level or organization-level policies can prevent public access. Never put credentials, private data, or secrets in a public bucket.

Official documentation:
https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html
https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html
https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/GettingStarted.SimpleDistribution.html

CONTENT NOTE
This is a starter learning blog. Update articles as your understanding grows. The journal page is explicitly a template and does not claim completed study sessions or achievements.
