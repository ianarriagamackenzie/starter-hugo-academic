---
title: 'Summix: A method for detecting and adjusting for population structure in genetic summary data'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin
  - Gregory Matesi
  - Samuel Chen
  - Alexandria Ronco
  - Katie M. Marker
  - Jordan R. Hall
  - Ryan Scherenberg
  - Mobin Khajeh-Sharafabadi
  - Yinfei Wu
  - Christopher R. Gignoux
  - Megan Null
  - Audrey E. Hendricks

# Author notes (optional)
author_notes:
  - '1st Author'

date: '2021-07-01T00:00:00Z'
doi: '10.1016/j.ajhg.2021.05.016'

# Schedule page publish date (NOT publication's date).
publishDate: '2022-05-01T00:00:00Z'

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ['2']

# Publication name and optional abbreviated publication name.
publication: In *American Journal of Human Genetics*
publication_short: In *AJHG*

abstract: "Publicly available genetic summary data have high utility in research and the clinic, including prioritizing putative causal variants, polygenic scoring, and leveraging common controls. However, summarizing individual-level data can mask population structure, resulting in confounding, reduced power, and incorrect prioritization of putative causal variants. This limits the utility of publicly available data, especially for understudied or admixed populations where additional research and resources are most needed. Although several methods exist to estimate ancestry in individual-level data, methods to estimate ancestry proportions in summary data are lacking. Here, we present Summix, a method to efficiently deconvolute ancestry and provide ancestry-adjusted allele frequencies (AFs) from summary data. Using continental reference ancestry, African (AFR), non-Finnish European (EUR), East Asian (EAS), Indigenous American (IAM), South Asian (SAS), we obtain accurate and precise estimates (within 0.1%) for all simulation scenarios. We apply Summix to gnomAD v.2.1 exome and genome groups and subgroups, finding heterogeneous continental ancestry for several groups, including African/African American (~84% AFR, ~14% EUR) and American/Latinx (~4% AFR, ~5% EAS, ~43% EUR, ~46% IAM). Compared to the unadjusted gnomAD AFs, Summix's ancestry-adjusted AFs more closely match respective African and Latinx reference samples. Even on modern, dense panels of summary statistics, Summix yields results in seconds, allowing for estimation of confidence intervals via block bootstrap. Given an accompanying R package, Summix increases the utility and equity of public genetic resources, empowering novel research opportunities."

# Summary. An optional shortened abstract.
summary: Summix is method to efficiently deconvolute ancestry and provide ancestry-adjusted allele frequencies from summary data.

tags: [genetics, ancestry, inference, summary statistics, population stratification]

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ''
url_code: 'https://github.com/hendriau/Summix_manuscript'
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: 'Summix_Slides.pdf'
url_source: 'https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8322937/'
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Gradient Descent Ancestry Estimation'
  focal_point: ''
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---