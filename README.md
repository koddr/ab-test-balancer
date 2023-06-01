# ab-test-balancer – An intelligent lead balancer for A/B tests

[![Go version][go_version_img]][go_dev_url]
[![Go report][go_report_img]][go_report_url]
![Code coverage][go_code_coverage_img]
[![Wiki][wiki_img]][wiki_url]
[![License][license_img]][license_url]

The **ab-test-balancer** project provides an intelligent lead balancer for 
any A/B marketing tests with analytics of client behavior on your landing pages.

Features:

- 100% **free** and **open source**
- One domain address for **many** different landing pages in A/B tests
- Smart gathering **full client details** for in-depth analytics (clicks,
  User-Agent, IP, ...)
- Balancing incoming leads per landing page based **only on your** rules
- Easy BI integration by **automatic generated** REST API
- Fast deploying to your server in **isolated** container

## ⚡️ Quick start

First, fork this repository, `git clone` and go to the project folder.

Prepare your configuration file. You could use any of a popular format 
(JSON, YAML, TOML or HCL), file structure must be the same.

For example, `./config.json`:

```json
{
  "type": "round-robin",
  "default": {
    "domain": "example.com",
    "url_path": ["main", "sales"],
    "get_params": null,
    "utm": null,
    "is_https": true
  },
  "landings": [
    {
      "domain": "example.com",
      "url_path": ["test", "1", "sales"],
      "get_params": [
        {"marketing_id": "123456-abc"},
        {"other_id": "abc-654321"}
      ],
      "utm": {
        "utm_source": "ab-test-balancer",
        "utm_medium": "landing",
        "utm_campaign": "test-1_sales",
        "utm_content": "NOW_DATE",
        "utm_term": "sale"
      },
      "is_https": true,
      "leads_count": 10000
    }
  ]
}
```

> 💡 Note: See the repository's [Wiki][wiki_url] page to understand the full
> structure of the config file.

Next, build your own container:

```console
docker build
```

And just run container:

```console
docker run
```

Done! 🎉 Your tasks have been executed.

## ✨ Usage

Basic usage and full code examples of all functions of the `ab-test-balancer` 
package, you can find on the [pkg.go.dev][go_dev_url] page.

## 💡 Motivation

...

## 🏆 A win-win cooperation

And now, I invite you to participate in this project! Let's work **together** to
create the **most useful** tool for developers on the web today.

- [Issues][repo_issues_url]: ask questions and submit your features.
- [Pull requests][repo_pull_request_url]: send your improvements to the current.

Your PRs & issues are welcome! Thank you 😘

## ⚠️ License

[`ab-test-balancer`][repo_url] is free and open-source software licensed 
under the [Apache 2.0 License][license_url], created and supported with 🩵 
for people and robots by [Vic Shóstak][author].

[go_version_img]: https://img.shields.io/badge/Go-1.20+-00ADD8?style=for-the-badge&logo=go
[go_report_img]: https://img.shields.io/badge/Go_report-A+-success?style=for-the-badge&logo=none
[go_report_url]: https://goreportcard.com/report/github.com/koddr/ab-test-balancer
[go_code_coverage_img]: https://img.shields.io/badge/code_coverage-0%25-success?style=for-the-badge&logo=none
[go_dev_url]: https://pkg.go.dev/github.com/koddr/ab-test-balancer
[wiki_img]: https://img.shields.io/badge/docs-wiki_page-blue?style=for-the-badge&logo=none
[wiki_url]: https://github.com/koddr/ab-test-balancer/wiki
[license_img]: https://img.shields.io/badge/license-Apache_2.0-red?style=for-the-badge&logo=none
[license_url]: https://github.com/koddr/ab-test-balancer/blob/main/LICENSE
[repo_url]: https://github.com/koddr/ab-test-balancer
[repo_issues_url]: https://github.com/koddr/ab-test-balancer/issues
[repo_pull_request_url]: https://github.com/koddr/ab-test-balancer/pulls
[author]: https://github.com/koddr
