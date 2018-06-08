---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "dc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc")
venue: "Wegner Health Science Information Center"        # brief name of host site without address (e.g., "Euphoric State University")
address: "1400 W. 22nd St., Suite 100, Sioux Falls SD 57105"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "43.533524, -96.742792"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "June 29-30, 2018"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "8:30 am - 4:30 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2018-06-29      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2018-06-30        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Rebecca Lowdon", "Doug Jennewein"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Aaron Bergstrom", "Carrie Brown", "Joseph Madison"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["joseph.madison@coyotes.usd.edu, doug.jennewein@usd.edu"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: "http://pad.software-carpentry.org/2018-06-29-und-mbdh"  # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% comment %}

<hr/>


{% comment %}
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

{% if page.carpentry == "swc" %}
  {% include sc/schedule.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/schedule.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/schedule.html %}
{% endif %}

{% comment %}
  Collaborative Notes

  If you want to use an Etherpad, go to

      http://pad.software-carpentry.org/2018-06-29-site

  where '2018-06-29-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

<h2 id="setup">Setup</h2>

<p>
To participate in a Data Carpentry workshop, you will need working copies of the 
described software. Please make sure to install everything (or at least to download 
the installers) before the start of your workshop. Participants should bring and use 
their own laptops to insure the proper setup of tools for an efficient workflow 
once you leave the workshop.
<p>
<strong>Mac users</strong>
<ul>
	<li><a href="https://www.java.com/en/download/">Java</a></li> 
	<li><a href="https://filezilla-project.org/download.php?show_all=1">Filezilla</a></li> 
	<li><a href="http://software.broadinstitute.org/software/igv/download">Integrative Genomics Viewer (IGV)</a></li> 
        <li><a href="https://www.rstudio.com/products/rstudio/download/#download"> RStudio</a></li>
</ul>
</p>
<p>
<strong>Windows users</strong>
<ul>
	<li><a href="http://www.putty.org/">Putty</a> Download putty.exe.</li>
	<li><a href="https://www.java.com/en/download/">Java</a></li> 
	<li><a href="https://filezilla-project.org/download.php?show_all=1">Filezilla</a></li> 
	<li><a href="http://software.broadinstitute.org/software/igv/download">Integrative Genomics Viewer (IGV)</a></li> 
        <li><a href="https://www.rstudio.com/products/rstudio/download/#download"> RStudio </a></li>
</ul>
</p>

<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "https://github.com/swcarpentry/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>
<hr/>
