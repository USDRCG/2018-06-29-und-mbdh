---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "dc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc")
venue: "USD Wegner Health Science Information Center"        # brief name of host site without address (e.g., "Euphoric State University")
address: "1400 W. 22nd St.,  Room L15 (Lower Level), Sioux Falls SD 57105"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
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
eventbrite:  46715948660     # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
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
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% endif %}

{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges
  on. They should have a few specific software packages installed (listed
  <a href="#setup">below</a>). They are also required to abide by
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %} 
 SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>

{% if page.carpentry == "swc" %} 
<p>Please be sure to complete these surveys before and after the workshop.</p>
<p><a href="{{ site.swc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.swc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif page.carpentry == "dc" %}
  <p>Please be sure to complete these surveys before and after the workshop.</p>
<p><a href="{{ site.dc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.dc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif page.carpentry == "lc" %}
<p>Ask your instructor about pre- and post-workshop Survey details.</p>
{% endif %}


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
