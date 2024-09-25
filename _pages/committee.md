---
title: "The Committee"
layout: splash
permalink: /committee/
date: 2022-02-28
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/commitee_header.jpg
  caption: "Sports Fair 2022"

---
<!-- TODO: put all grid instances where they belong... -->
<!-- this grid is used for the docs and committee loop -->
<style>

.grid-container_committee {
  /**
   * User input values.
   */
  --grid-layout-gap: 3em;
  --grid-column-count: 3;
  --grid-item--min-width: 300px;

  /**
   * Calculated values.
   */
  --gap-count: calc(var(--grid-column-count) - 1);
  --total-gap-width: calc(var(--gap-count) * var(--grid-layout-gap));
  --grid-item--max-width: calc((100% - var(--total-gap-width)) / var(--grid-column-count));

  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(max(var(--grid-item--min-width), var(--grid-item--max-width)), 1fr));
  column-gap: 3em;
}

.grid-item_committee {
  padding: 10px;
  text-align: center;
}
</style>

<!-- # Committee

 -->

<div class="grid-container_committee">  
  {% for role in site.data.committee %} <!-- for each committee position... -->
    {% for member in role[1] %} <!-- for each committee member in said role... -->
      <div class="grid-item_committee">
      {% include committee-profile.html %}
      </div>
    {% endfor %}
  {% endfor %}
</div>



# Policy Documents

Documents governing how the club is run may be found below.
{% assign doc_path = site.url | append: site.baseurl | append: "/assets/docs" %}
<div class="grid-container_committee">
  <div class="grid-item_committee"><a href="{{ doc_path }}/CU Powerlifting Club Constitution 2024-25.pdf" class="btn btn--primary btn--block btn--large">Constitution</a></div>
  <div class="grid-item_committee"><a href="{{ doc_path }}/CU Powerlifting Club Code of Conduct 2022-23.pdf" class="btn btn--primary btn--block btn--large">Code of Conduct</a></div>
  <div class="grid-item_committee"><a href="{{ doc_path }}/CU Powerlifting Club Safety Statement 2024-25.pdf" class="btn btn--primary btn--block btn--large">Safety Statement</a></div>
  <div class="grid-item_committee"><a href="{{ doc_path }}/CU Powerlifting Club Welfare Policy 2024-25.pdf" class="btn btn--primary btn--block btn--large">Welfare Policy</a></div>
  <div class="grid-item_committee"><a href="{{ doc_path }}/CU Powerlifting Club Privacy Notice Statement 2021-22.pdf" class="btn btn--primary btn--block btn--large">Privacy Notice</a></div>
  <div class="grid-item_committee"><a href="{{ doc_path }}/CU Powerlifting Committee Job Descriptions.pdf" class="btn btn--primary btn--block btn--large">Committee Roles</a></div>
</div>

&nbsp;

# Previous Committees

{% assign archive=true %}
{% for year in site.data.ex-committees %}
## {{ year[0] }}

<div class="grid-container_committee">  
  {% for role in year[1] %} <!-- for each committee position... -->
    {% for member in role[1] %} <!-- for each committee member in said role... -->
      <div class="grid-item_committee">
      {% include committee-profile.html %}
      </div>
    {% endfor %}
  {% endfor %}
</div>

{% endfor %}
