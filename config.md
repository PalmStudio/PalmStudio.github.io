<!--
Add here global page variables to use throughout your website.
-->
+++
author = "Remi Vezy & Raphael Perez"
mintoclevel = 2

# Add here files or directories that should be ignored by Franklin, otherwise
# these files might be copied and, if markdown, processed by Franklin which
# you might not want. Indicate directories by ending the name with a `/`.
# Base files such as LICENSE.md and README.md are ignored by default.
ignore = ["node_modules/"]

# RSS (the website_{title, descr, url} must be defined to get RSS)
generate_rss = true
website_title = "PalmStudio website"
website_descr = "Website for the PalmStudio research project"
website_url   = "https://palmstudio.github.io/"
+++

<!--
Add here global latex commands to use throughout your pages.
-->
\newcommand{\R}{\mathbb R}
\newcommand{\scal}[1]{\langle #1 \rangle}
\newcommand{\note}[1]{@@note @@title 📝 Note@@ @@content #1 @@ @@}
\newcommand{\warning}[1]{@@warning @@title 🔥 Warning!@@ @@content #1 @@ @@}
\newcommand{\tip}[1]{@@tip @@title 🌴 Tip@@ @@content #1 @@ @@}
<!-- To use note, warning and tip, just do the following: -->
<!-- \note{This is a note}
\warning{This is a warning}
\tip{This is a tip} -->

\newcommand{\badge}[3]{
~~~
<a target="_blank" href="!#3"><img src="!#2" style="padding:0;max-height:1.0em;width:auto;text-align:justify;display:inline-block;position:relative;vertical-align:top" alt="#1"/></a>
~~~
}

\newcommand{\badgegithub}[1]{
~~~
<a target="_blank" href="!#1"><img src="/assets/github_badge.svg" style="padding:0;max-height:1.0em;width:auto;text-align:justify;display:inline-block;position:relative;vertical-align:top;" alt="Github link"/></a>
~~~
}

\newcommand{\badgealfresco}[1]{
~~~
<a target="_blank" href="!#1"><img src="/assets/Alfresco_logo.svg" style="padding:0;max-height:1.0em;width:auto;text-align:justify;display:inline-block;position:relative;vertical-align:top" alt="Alfresco link"/></a>
~~~
}
