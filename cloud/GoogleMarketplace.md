# Requirements for Google Cloud Marketplace 


If you want to offer products on Google Cloud Marketplace, you must meet the following listing requirements.

Note: If you make changes to your product or organization that affect your compliance with these listing requirements or invalidate documentation that you provided to Google during onboarding, you must notify Google and submit your product for re-review and re-approval.
Requirements for your organization

- Your organization must join Partner Advantage.

Note: If you aren't yet a Google partner, learn more and sign up at the Join Google Cloud Partner Advantage page.
After your organization has joined Partner Advantage, you get access to Partner Hub.
- Your organization must be incorporated in one of the supported regions.
- Your organization must have at least US$1,000,000 in annual revenue.
- Your organization must have a Cloud Marketplace vendor account and payment profile in good standing.

# Requirements for your product

- Your product must be production-ready (not alpha or beta) to be publicly listed and sold through Cloud Marketplace.
- Your product must not include professional services sold through Cloud Marketplace.
- Your product must not include known vulnerabilities, viruses, spyware, Trojan horses, or other malicious code of any kind.
Note: Google offers a standard revenue share for products you sell through Cloud Marketplace that meet all of the listed requirements and pass a business case review during Google's internal product validation process. If your product doesn't meet the requirements, or doesn't pass the business case review, but you want to proceed with offering that product through Cloud Marketplace, Google might offer you an adjusted revenue share.

# Additional requirements for software as a service (SaaS) products

You must verify to Google Cloud through an approval process during onboarding that you host your product primarily on Google Cloud. The following patterns are common approved use cases:

- Pattern 1: Your entire product, and all of its supporting components, run entirely on Google Cloud.
- Pattern 2: Your product's compute or data plane runs on Google Cloud, but smaller control planes or support infrastructure, such as logging, run on-premises or on another cloud. In this case, your Google Cloud-hosted compute or data plane must be the resource whose consumption increases the fastest when your users increase their consumption.
- Pattern 3: Your backup, replication, or data recovery (DR) product replicates data to Google Cloud by default, while the product's control plane can run on-premises or on other clouds.
- Pattern 4: Your product's migration tooling has Google Cloud as its only destination for migration, but can run on-premises or on another cloud as a migration source.
- Pattern 5: Your product's compute or data plane runs on Google Cloud. Your product's monitoring or security agents can run on-premises or on another cloud, but they must send data to a Google Cloud-hosted environment for storage and analysis.

# Operational requirements

- You must ensure that your products on Cloud Marketplace have the same capabilities and features as any versions of those products that you offer outside of Cloud Marketplace.
If you identify any critical security issues related to your products on Cloud Marketplace, you must update your products to resolve the issues.
- Your organization must be willing to commit resources to create and maintain the products that you list in Cloud Marketplace, and provide timely support to your customers.

https://cloud.google.com/marketplace/docs/partners/get-started#requirements
