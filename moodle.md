process to a componente

create an output backend file with class function to search data as
C:\laragon\www\moodle\theme\prodam\classes\output\categories.php
<?php
// File: C:\laragon\www\moodle\theme\prodam\classes\output\categories.php
// This file is part of Moodle - http://moodle.org/
//
// Moodle is free software: you can redistribute it and/or modify
// it under the terms of the GNU General Public License as published by
// the Free Software Foundation, either version 3 of the License, or
// (at your option) any later version.
//
// Moodle is distributed in the hope that it will be useful,
// but WITHOUT ANY WARRANTY; without even the implied warranty of
// MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
// GNU General Public License for more details.
//
// You should have received a copy of the GNU General Public License
// along with Moodle.  If not, see <http://www.gnu.org/licenses/>.

/**
 * Categories renderable class.
 *
 * @package    theme_prodam
 * @copyright  2025 vic Tavares - pwdbyv1c
 * @license    http://www.gnu.org/copyleft/gpl.html GNU GPL v3 or later
 */

namespace theme_prodam\output;

use moodle_url;
use context_coursecat;
use renderable;
use templatable;
use renderer_base;

defined('MOODLE_INTERNAL') || die;

/**
 * Class categories
 *
 * A renderable class for fetching and displaying course categories.
 * It is freely displayed on the start page even for non-logged-in users.
 */
class categories implements renderable, templatable
{





    /**
     * Mapping category names for icon that has not a field in the table
    */
    private function get_category_icon($categoryName)
    {
        $iconMap = [
            'educação' => 'fa fa-graduation-cap',
            'educacao' => 'fa fa-graduation-cap',
            'trânsito' => 'fa fa-car',
            'transito' => 'fa fa-car',
            'finanças' => 'bi bi-cash-stack',
            'financas' => 'bi bi-cash-stack',
            'web' => 'bi bi-globe',
            'programação' => 'bi bi-code-slash',
            'programacao' => 'bi bi-code-slash',
            'design' => 'bi bi-palette',
            'tecnologia' => 'bi bi-cpu',
            'conectividade' => 'bi bi-diagram-3'
        ];

        // Normalize name to compare (remove special characters and convert to lowercase)
        $normalizedName = $this->normalize_string($categoryName);
        
        return $iconMap[$normalizedName] ?? 'bi bi-folder';
    }


     /**
     * Normalize string to compaction  (remove special characters and convert to lowercase)
     */
    private function normalize_string($string)
    {
        $string = mb_strtolower($string, 'UTF-8');
        $string = preg_replace('/[áàãâä]/u', 'a', $string);
        $string = preg_replace('/[éèêë]/u', 'e', $string);
        $string = preg_replace('/[íìîï]/u', 'i', $string);
        $string = preg_replace('/[óòõôö]/u', 'o', $string);
        $string = preg_replace('/[úùûü]/u', 'u', $string);
        $string = preg_replace('/[ç]/u', 'c', $string);
        $string = preg_replace('/[^a-z0-9]/u', '', $string);
        
        return $string;
    }



    /**
     * Export data for the Mustache template.
     *
     * @param renderer_base $output The renderer base object.
     * @return array Data for the template.
     */ public function export_for_template(renderer_base $output): array
    {
        global $DB, $CFG;

        $sql = "SELECT *
                 FROM {course_categories}
                WHERE visible = 1
                ORDER BY sortorder ASC";

        $categories = $DB->get_records_sql($sql);

        $categoriesdata = [];
        foreach ($categories as $category) {
            $context = context_coursecat::instance($category->id);
            $categoryName = strip_tags(format_string($category->name, true, ['context' => $context]));
            
            $categoriesdata[] = [
                'id' => $category->id,
                'name' => $categoryName,
                'description' => shorten_text(strip_tags(format_text($category->description, FORMAT_HTML, ['context' => $context])), 100),
                'url' => (new moodle_url('/course/index.php', ['categoryid' => $category->id]))->out(false),
                'icon' => $this->get_category_icon($categoryName) // Adiciona o ícone
            ];
        }

        return [
            'categories' => array_values($categoriesdata),
            'hascategories' => !empty($categoriesdata),
            'count' => count($categoriesdata)
        ];
    }
}






##################################################################################################################


make an html file like to render data comes from backend php

C:\laragon\www\moodle\theme\prodam\templates\components\featured-categories.mustache
<main id="main-featured-categories" class="main-featured-categories">
  <div class="container p-0 border-0">
    <div class="row m-0">
      <div class="col-12">
        <div class="featured-categories-container text-center" aria-label="Tópicos disponíveis">

          <!-- Título -->
          <div class="featured-categories-title">
            <span class="green-arrow">></span>
            {{#str}}explore, theme_prodam{{/str}}
            <span class="green-dot">•</span>
          </div>

          <span class="featured-categories-subtitle d-block">
            {{#str}}takealookatthecategories, theme_prodam{{/str}}
          </span>

          <!-- Grid de categorias: 8 cards por página (2 linhas de 4) -->
          <div class="featured-categories-grid row justify-content-center gx-4">

{{#hascategories}}
  {{#categories}}
    <div class="col-6 col-lg-3">
      <div class="featured-topic-grid-shadow">
        <a href="{{url}}" class="featured-topic-card" data-categoryid="{{id}}">
          <div class="topic-icon-container">
            <i class="{{icon}} topic-icon"></i>
          </div>
          <p class="topic-name">{{name}}</p>
          <p class="topic-name">{{id}}</p>
        </a>
      </div>
    </div>
  {{/categories}}
{{/hascategories}}

            {{^hascategories}}
              <div class="col-12">
                <div class="no-categories">
                  <p>Nenhuma categoria disponível.</p>
                </div>
              </div>
            {{/hascategories}}

          </div>

          <!-- Botões de paginação -->
          <div class="pagination-controls mt-4">
            {{#haspreviouspage}}
              <a href="?page={{previouspage}}" class="btn-pagination btn-prev">
                <i class="bi bi-arrow-left-short"></i> Anterior
              </a>
            {{/haspreviouspage}}

            {{#hasnextpage}}
              <a href="?page={{nextpage}}" class="btn-pagination btn-next">
                Próxima <i class="bi bi-arrow-right-short"></i>
              </a>
            {{/hasnextpage}}
          </div>

        </div>
      </div>
    </div>
  </div>
</main>





##################################################################################################################

Create function:
C:\laragon\www\moodle\theme\prodam\classes\output\core_renderer.php
 public function render_categories() {
        $categories = new categories();
        return $this->render_from_template('theme_prodam/components/featured-categories', $categories->export_for_template($this));
    }


Tehe functio is responsable to 
Instantiates a categories object (which contains course category data)
Renders this data using a custom Mustache template
Returns the generated HTML for display in the theme

Why is it needed?
This function is needed because:
Allows you to customize the display of course categories
Separates rendering logic from templates
Follows the Moodle rendering standard
Facilitates theme maintenance and customization



##################################################################################################################

Render it in
 C:\laragon\www\moodle\theme\prodam\templates\drawers.mustache
with the call
{{{ output.render_categories }}}


its possivel to call {{{ output.render_categories }}} in any other template file just inserting {{{ output.render_categories }}}

.
