<!--
   Licensed to the Apache Software Foundation (ASF) under one or more
   contributor license agreements.  See the NOTICE file distributed with
   this work for additional information regarding copyright ownership.
   The ASF licenses this file to You under the Apache License, Version 2.0
   (the "License"); you may not use this file except in compliance with
   the License.  You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
-->
# Apache NiFi Hugo Website

This is the proposed source code for the new website of [Apache NiFi](https://nifi.apache.org/), hosted at:

    https://nifi.apache.org/

This initial repo is the minimal amount of changes necessary to deploy the current repo [apache/nifi-site](https://github.com/apache/nifi-site) in the [Hugo Framework](https://gohugo.io).

## Instructions
- Setup your environment (python,homebrew,hugo)
    `brew install hugo`
- Clone repo
    `git clone <this repo>`
- run hugo server
    `hugo server`
- view website
    http://127.0.0.1:1313/

## Hugo Conversion Notes

### Site Conversion
  - issues with {{assets}}
    - !! ASSETS folder is missing in the repo but files are on the live site (I did wget for missing files)
    - !! need a solution to fix variable or full find replace to /assets

### Page Conversion
  - renamed all .hbs to html
  - !! issues with &amp;amp; !! 


### NiFi Asci Docs
  - !! Need to handle nifi-docs from main site
          `<iframe src="docs/nifi-docs/index.html"></iframe>` in docs.html
    - some of this process is in place on the airflow site including building multi versions
    - ?? take a look at what is done in jena to link to apache/jena repo ??

### MiNiFi
  - ?? sub folder index pages needed to be __index ??
  - !! issue with site reloading /minifi/index.html to /minifi/ (blank page)
    - solved by adding slug to front matter
  - !! menu links stay relative to /minifi/ when in this subpage