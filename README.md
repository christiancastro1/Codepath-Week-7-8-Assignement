# Project 7 - WordPress Pentesting

Time spent: **7** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. Title: WordPress <= 4.2.2 - Authenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.3 
  - [ ] GIF Walkthrough:  <img src='https://media.giphy.com/media/hVseBMhH4nm6sEOxlM/giphy.gif' width='' alt='Video Walkthrough' />
  - [ ] Steps to recreate: 
    - Sign in as admin
    - create new post
    - switch from visual to text
    - input affected source code 
    - go to site and hover the newly made post
    Results: Pop up message comes up
  - [ ] Affected source code:  
        `<a href="[caption code=">]</a><a title=" onmouseover=alert('test')">link</a>`
  
    - [References]
       - https://wpvulndb.com/vulnerabilities/8111
       - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5622
       - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5623
       - https://wordpress.org/news/2015/07/wordpress-4-2-3/
       - https://twitter.com/klikkioy/status/624264122570526720
       - https://klikki.fi/adv/wordpress3.html

    
2.Title: WordPress  4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [ ] Summary: 
    - Vulnerability types: XSS (CVE-2017-6817)
    - Tested in version: 4.2
    - Fixed in version: 4.2.13 
  - [ ] GIF Walkthrough:
    <img src='https://media.giphy.com/media/YQHbaMZV4IUQJufOnF/giphy.gif' width='' alt='Video Walkthrough' />
  - [ ] Steps to recreate: 
      - Sign in as admin 
      - Create a new post
      - Switch from visual to text in the editing section
      - Write affecte source code in post
      - Finish posting.
      - Go to your site.
      Results: XSS alert is shown
  - [ ] Affected source code:
      `[embed src='https://www.youtube.com/embed/dQw4w9WgXcQ\x3csvg onload=alert("exploit!")\x3e'][/embed]`
    
       - [References]
           - https://wpvulndb.com/vulnerabilities/8768
           - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-6817
           - https://wordpress.org/news/2017/03/wordpress-4-7-3-security-and-maintenance-release/
           - https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8
           - https://blog.sucuri.net/2017/03/stored-xss-in-wordpress-core.html
    
    
    
3.  Authenticated Shortcode Tags Cross-Site Scripting
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.5
  - [ ] GIF Walkthrough: <img src='https://media.giphy.com/media/XF4wO4rQeWpn53Y1mD/giphy.gif' width='' alt='Video Walkthrough' />
  - [ ] Steps to recreate: 
     - Sign in as admin
     - Got to dashboard
     - switch from visual to text
     - post and view
     - hover new post 
  - [ ] Affected source code: `TEST!!![caption width="1" caption='<a href="' ">]</a><a href="http://onMouseOver='alert(1)'">Click me</a>`
    - [References]
      - https://wpvulndb.com/vulnerabilities/8186
      - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5714
      - https://wordpress.org/news/2015/09/wordpress-4-3-1/
      - http://blog.checkpoint.com/2015/09/15/finding-vulnerabilities-in-core-wordpress-a-bug-hunters-trilogy-part-iii-ultimatum/
      - http://blog.knownsec.com/2015/09/wordpress-vulnerability-analysis-cve-2015-5714-cve-2015-5715/
 

4. Nav Menu Title Cross-Site Scripting (XSS)
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.4
  - [ ] GIF Walkthrough: <img src='https://media.giphy.com/media/jtcfDGY2EStQIYx4Mx/giphy.gif' width='' alt='Video Walkthrough' />
  - [ ] Steps to recreate:
      - Sign in as admin
      - Go to dashbaord
      - click on Appereance -> Menu 
      - Create a new menu, in the navation label input affected code from below. 
      - Wait a few seconds and pop up comes up
  - [ ] Affected source code:
     `Home<script>alert("Christian is awesome");</script>)`
    - [References]
       - https://wpvulndb.com/vulnerabilities/8132
       - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5733
       - https://core.trac.wordpress.org/changeset/33541
 

    ## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [Gify](https://giphy.com/).

## Notes
Setting up wp and khalid linux were the most challenging, other than that example were easily reproduced with the references that wpscan returns

## License

    Copyright [2019] [chri]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
