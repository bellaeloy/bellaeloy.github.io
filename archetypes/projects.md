+++
title = "{{ replace .Name "-" " " | title }}"
date = {{ .Date }}
year = "{{ dateFormat "2006" .Date }}"
role = ""
location = ""
summary = "One or two sentences. This text shows on the project card and on the timeline."
cover = "/images/projects/{{ .Name }}.svg"
tools = []
tags = []
featured = false
[[links]]
name = "Repository"
icon = "fa-brands fa-github"
url = "#"
+++

Write the project here.
