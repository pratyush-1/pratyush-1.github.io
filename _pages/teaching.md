---
layout: page
permalink: /teaching/
title: Teaching
description:
nav: true
nav_order: 5
---

<!-- pages/teaching.md -->
<!-- pages/teaching.md -->
<div class="teaching">
  {%- assign sorted_years = site.data.teaching | sort: "year" | reverse -%}
  {%- for year_entry in sorted_years -%}
    <a id="{{ year_entry.year }}" href=".#{{ year_entry.year }}">
      <h2 class="year">{{ year_entry.year }}</h2>
    </a>
    <div class="row row-cols-1 row-cols-md-2">
      {%- for course in year_entry.courses -%}
        <div class="col mb-4">
          <div class="card h-100">
            <div class="card-body">
              <h5 class="card-title">{{ course.title }}</h5>
              <h6 class="card-subtitle mb-2 text-muted">{{ course.code }}</h6>
              <p class="card-text course-description">{{ course.description | truncate: 100 }}</p>

              <!-- Read More Button -->
              <a href="#" class="read-more" data-toggle="modal" data-target="#modal-{{ course.code }}">Read More</a>

              <!-- Slides Button -->
              <a href="{{ course.url }}" class="btn btn-secondary ml-2" target="_blank">Slides</a>

              <!-- Linktree Button -->
              <a href="{{ course.linktree }}" class="btn btn-success ml-2" target="_blank">Linktree</a>
            </div>
          </div>
        </div>

        <!-- Modal -->
        <div class="modal fade" id="modal-{{ course.code }}" tabindex="-1" role="dialog" aria-labelledby="modal-{{ course.code }}-label" aria-hidden="true">
          <div class="modal-dialog modal-dialog-centered" role="document">
            <div class="modal-content" style="background-color: var(--bg-color, #fff); color: var(--text-color, #000);">
              <div class="modal-header" style="border-bottom-color: var(--border-color, #dee2e6);">
                <h5 class="modal-title" id="modal-{{ course.code }}-label" style="color: var(--text-color, #000);">{{ course.title }}</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close" style="color: var(--text-color, #000);">
                  <span aria-hidden="true">&times;</span>
                </button>
              </div>
              <div class="modal-body" style="color: var(--text-color, #000);">
                {{ course.description }}
              </div>
            </div>
          </div>
        </div>
      {%- endfor -%}
    </div>
  {%- endfor -%}
</div>