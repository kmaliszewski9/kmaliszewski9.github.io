---
layout: post
title: "Rust's supergrowth"
date: 2026-11-02 12:00:00 +0100
categories: rust
---
The number of accounts pushing code to Rust projects [grew 162%](https://github.blog/news-insights/octoverse/octoverse-commits-pushes-reach-new-highs-in-2026-as-developers-build-with-agents/) from Sep 2025 to Sep 2026. By this measure, it is the fastest-growing major language.

![ai_prs_by_language]({{ BASE_PATH }}/assets/rust-growth/ai-prs-by-language.png)

For comparison, [in 2022](https://github.blog/news-insights/research/octoverse-2022-10-years-of-tracking-open-source/) that growth was about 50%.

Also, this year Rust [entered the top 10](https://www.infoworld.com/article/4193406/rust-language-rises-to-top-10-in-tiobe-popularity-index.html) of the [TIOBE index](https://www.tiobe.com/tiobe-index/), surpassing Go.

Sure, memory-safety pressure, Linux adoption and big-tech backing already gave Rust steady growth, but 2026 is its strongest year so far. The year, the industry stopped writing code by hand.

That makes sense. Agents flip Rust's old tradeoff. Its safety and performance came at the cost of lower productivity and a steep learning curve. When a machine does the writing, these costs are mostly gone. Also, arguably it is a pretty well suited language for agents. 

What does it mean?

If CI/CD is already painful, Rust compilation will push it even harder. A build of a mid-sized workspace takes minutes. Caching `target/` in CI is a project of its own. Rust is (in)famous for its insane build times and output sizes.

With all the ongoing rewrites, some edge cases are probably still waiting to be discovered. Remember Cloudflare's [outage](https://blog.cloudflare.com/18-november-2025-outage/) last year? Innocent `unwrap()` in their new Rust proxy took a large part of the internet down for hours. Ubuntu’s rewrite of coreutils shipped a `date -r` [bug](https://www.omgubuntu.co.uk/2025/10/ubuntu-25-10-rust-coreutils-date-bug) that quietly stopped automatic security updates on 25.10. 

Many teams will own Rust they can't really read or debug. I know, reading the code is going out of fashion, but the compiler still cannot verify intent. At least for now. 

On the bright side, it could also mean that we will have more secure and performant software. At Google, memory-safety bugs [fell from 76% of Android vulnerabilities in 2019 to under 20% in 2025](https://blog.google/security/rust-in-android-move-fast-fix-things/). Rust code there shows about 1000x lower memory-safety vulnerability density than C and C++.

It's the outcome I want to believe in, at a time when critical vulnerabilities land almost daily.

We may be shifting from languages designed for humans to write toward languages designed for humans to verify, and Rust is simply the first to benefit.
