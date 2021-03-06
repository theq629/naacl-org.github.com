naacl-org.github.com
================

new NAACL website using Jekyll on github hosting and layout coded using twitter bootstrap css (v2.1)

contact Anoop Sarkar for details

General Information
-------------------

1. The standard way to add information to the website is to first clone the repository from github (git clone git@github.com:naacl-org/naacl-org.github.com.git) and then add the files, remembering to git add, commit and then push to github.com all your additions.
2. When adding links to material within the website do not use the full URL with naacl.org or naacl-org.github.com. Instead use "{{ site.baseurl }}" as part of the href which is automatically set to the base URL, e.g. "{{ site.baseurl }}/about/index.html" would be a href link to the contents of "about/index.textile" in the raw jekyll source.
3. Put images for new posts into the images directory. Remember to git add, commit and push the files to the github repo.

Adding Posts
------------

1. Adding a new file in the _posts directory adds a new post after you git add the file and git commit and push it to github.com
2. The file can be in textile or markdown or simply html format. You must add the header information (just copy and edit the header from another post).

Links under Navigation side bar
-------------------

1. The basic layout of the site is defined in _layouts/default.html
2. The Navigation side bar is generated using the following code in default.html:
              <li class="nav-header">Navigation</li>
              {% assign pages_list = site.pages %}
              {% assign group = 'navigation' %}
              {% include pages_list %}
3. All pages which have 'group: "navigation"' included in their header information (see, e.g., about/index.textile) are automatically included in the above Navigation links for the website.

Adding a new set of Officers
-----------------

1. Copy the previous years officers file to the new year, e.g. copy officers-2012.textile to officers-2013.textile
2. Edit the previous year file to remove the line 'group: "navigation"', e.g. remove this line from officers-2012.textile
3. Keep the line 'group: "navigation"' in the new file, e.g. keep this line in officers-2013.textile
4. The list of previous years for all the officers is stored in the file _includes/officers_year_list -- Change this file to add the new year.
5. If the number of years grows too large, edit the file _includes/officers_year_list to add a limit: change '{% for year in (2000..2012) %}' to '{% for year in (2000..2012) limit:5 %}'

Adding new minutes for board meetings 
-------------------

1. All the minutes are stored in the minutes directory.
2. Create a new directory for the new year, e.g. minutes/2013 and then add the files as in previous years.
3. You can add as many supplementary files (PDF or otherwise) as you need but then you should create a new index.textile in that year that has a listing of all the files.
3. You *must* then change minutes/index.textile and add the new year to the loop that creates the index: {% for year in (2000..2012) %}

Adding a new Summer School CFP
-------------------

1. All the JHU summer school material is in the summerschool directory.
2. Just copy the last year file to a new one, e.g. copy the contents of summerschool/2012 to summerschool/2013 and then edit the files with the new information.
3. You *must* then change summerschool/index.textile and add the new year to the loop that creates the index: {% for year in (2011..2012) reversed %}

Changing index.html
-------------------

1. The central view of index.html is a div called the "hero" unit or can be an "alert" unit 
2. To advertise an upcoming conference you can copy and use the NAACL 2012 hero unit in _includes/naacl2012_hero_div
3. To use the NAACL poster image instead you can copy and use the default alert unit in _includes/default_alert_div

