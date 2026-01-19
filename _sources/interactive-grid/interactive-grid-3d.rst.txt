.. _class_InteractiveGrid3D:

InteractiveGrid3D
=================

**Inherits:** `Node3D <https://docs.godotengine.org/en/stable/classes/class_node3d.html>`__ **<** `Node <https://docs.godotengine.org/en/stable/classes/class_node.html>`__ **<** `Object <https://docs.godotengine.org/en/stable/classes/class_object.html>`__

.. only:: not i18n

  .. Note:: GitHub repository: https://github.com/antoinecharruel/interactive_grid_gdextension.


.. rst-class:: classref-introduction-group

Description
-----------

InteractiveGrid is a Godot GDExtension that allows player interaction with a 3D grid, including cell selection, pathfinding, and hover highlights.

* Select individual cells.
* Detect obstacles (collision mask configurable from the editor).
* Align cells with the floor (collision mask configurable from the editor).
* Hide distant cells to focus on the relevant area.
* Calculate paths from a global position to selected cells using AStar2D.
* Choose movement type: 4 directions, 6 directions, 8 directions, directly from the editor.
* Customize the grid from the editor: grid size, cell size, mesh, colors, and shaders.
* High performance using MultiMeshInstance3D for efficient rendering of multiple cells.

.. rst-class:: classref-properties-group

Properties
----------

.. csv-table::
   :file: ./data/ig3d_properties.csv
   :header-rows: 0

.. rst-class:: classref-reftable-group

Methods
-------

.. csv-table::
   :file: ./data/ig3d_methods.csv
   :header-rows: 0


.. rst-class:: classref-section-separator

Enumerations
------------

.. _class_InteractiveGrid3D_enum_layout:

**enum Layout**

- LAYOUT_SQUARE = 0
- LAYOUT_HEXAGONAL = 1

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_enum_movement:

**enum Movement**

- MOVEMENT_FOUR_DIRECTIONS = 0
- MOVEMENT_SIX_DIRECTIONS = 1
- MOVEMENT_EIGHT_DIRECTIONS = 2

.. rst-class:: classref-item-separator

.. rst-class:: classref-descriptions-group

Property Descriptions
---------------------

.. _class_interactivegrid3d_property_accessible_color:

Mesh **accessible_color**

.. rst-class:: classref-property-setget

- void **set_accessible_color** (value: Color)
- Color **get_accessible_color** ()

Color used to indicate that the cell is accessible.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_cell_mesh:

Mesh **cell_mesh**

.. rst-class:: classref-property-setget

- void **set_cell_mesh** (value: Mesh)
- Mesh **get_cell_mesh** ()

The Mesh resource for the grid.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_cell_rotation:

Vector3 **cell_rotation**

.. rst-class:: classref-property-setget

- void **set_cell_rotation** (value: int)
- Mesh **get_cell_rotation** ()

Rotation of the cell in 3D space.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_cell_shape:

Shape3D **cell_shape**

.. rst-class:: classref-property-setget

- void **set_cell_shape** (value: Shape3D)
- Shape3D **get_cell_shape** ()

The Shape3D resource for the cell, used for obstacle detection and for detecting objects that have a collision shape on the same layer as a CustomCellData.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_cell_shape_offset:

Shape3D **cell_shape_offset**

.. rst-class:: classref-property-setget

- void **set_cell_shape_offset** (value: Vector3)
- Shape3D **get_cell_shape_offset** ()

Offset of the cell shape relative to the cell origin.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_cell_size:

Vector2D **cell_size** = ``Vector2(1, 1)``

.. rst-class:: classref-property-setget

- void **set_cell_size** (value: Vector2D)
- Vector2D **get_cell_size** ()

Size of each grid cell.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_columns:

int **cell_columns** = ``9``

.. rst-class:: classref-property-setget

- void **set_cell_columns** (value: int)
- int **get_cell_columns** ()

Number of columns in the grid.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_custom_cells_data:

Array **custom_cells_data** = ``[]``

.. rst-class:: classref-property-setget

- void **set_custom_cells_data** (value: Array)
- Array **get_custom_cells_data** ()

List of CustomCellData used to add additional states, behaviors, or visual effects to specific grid cells. Each CustomCellData can be applied via a collision mask or through GDScript, and is accessible in shader scripts via the INSTANCE_CUSTOM alpha channel.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_floor_collision_masks:

int **floor_collision_masks** = ``16384``

.. rst-class:: classref-property-setget

- void **set_floor_collision_masks** (value: int)
- int **get_floor_collision_masks** ()

Collision masks used to detect the floor.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_hovered_color:

Color **hovered_color** = ``Color(1, 0.84313726, 0, 1)``

.. rst-class:: classref-property-setget

- void **set_hovered_color** (value: Color)
- int **get_hovered_color** ()

Color used when the cell is hovered over.

.. rst-class:: classref-item-separator

.. _class_InteractiveGrid3D_property_layout:

Layout **layout** = ``0``

.. rst-class:: classref-property-setget

- void **set_layout** (value: Layout)
- Color **get_layout** ()

Grid layout type (LAYOUT_SQUARE, LAYOUT_HEXAGONAL).

.. rst-class:: classref-item-separator

.. _class_InteractiveGrid3D_property_material_override:

Material **material_override**

.. rst-class:: classref-property-setget

- void **set_material_override** (value: Material)
- Color **get_material_override** ()

Optional material override for the grid. Assign a custom ShaderMaterial to visually modify grid cells.

.. rst-class:: classref-item-separator

.. _class_InteractiveGrid3D_property_movement:

Movement **movement** = ``0``

.. rst-class:: classref-property-setget

- void **set_movement** (value: Movement)
- Color **get_movement** ()

Type of movement on the grid for pathfinding: 4, 6, or 8 directions.

.. rst-class:: classref-item-separator

.. _class_InteractiveGrid3D_property_obstacles_collision_masks:

int **obstacles_collision_masks** = ``8192``

.. rst-class:: classref-property-setget

- void **get_obstacles_collision_masks** (value: int)
- int **set_obstacles_collision_masks** ()

Collision masks used to detect obstacles on the grid.

.. rst-class:: classref-item-separator

.. _class_InteractiveGrid3D_property_path_color:

int **path_color** = ``Color(0.5647059, 0.93333334, 0.5647059, 1)``

.. rst-class:: classref-property-setget

- void **get_path_color** (value: bool)
- bool **set_path_color** ()

Color used to display the path.

.. rst-class:: classref-item-separator

.. _class_InteractiveGrid3D_property_print_execution_time_enabled:

bool **print_execution_time_enabled** = ``Color(0.5647059, 0.93333334, 0.5647059, 1)``

.. rst-class:: classref-property-setget

- void **set_print_execution_time_enabled** (value: bool)
- bool **get_print_execution_time_enabled** ()

Enable printing execution time of grid operations for debugging.

.. rst-class:: classref-item-separator

.. _class_InteractiveGrid3D_property_print_logs_enabled:

bool **print_logs_enabled** = ``Color(0.5647059, 0.93333334, 0.5647059, 1)``

.. rst-class:: classref-property-setget

- void **set_print_logs_enabled** (value: int)
- int **get_print_logs_enabled** ()

Enable printing debug logs related to grid operations.

.. rst-class:: classref-item-separator

.. _class_InteractiveGrid3D_property_rows:

int **rows** = ``9``

.. rst-class:: classref-property-setget

- void **set_rows** (value: int)
- int **get_rows** ()

Number of rows in the grid.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_selected_color:

Color **selected_color** = ``Color(0.8784314, 1, 1, 1)``

.. rst-class:: classref-property-setget

- void **set_selected_color** (value: Color)
- Color **get_selected_color** ()

Color used to indicate the currently selected cell.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_unaccessible_color:

Color **unaccessible_color** = ``Color(0.8039216, 0.36078432, 0.36078432, 1)``

.. rst-class:: classref-property-setget

- void **set_unaccessible_color** (value: Color)
- Color **get_unaccessible_color** ()

Color used to indicate that the cell is not accessible or blocked.

.. rst-class:: classref-item-separator

.. _class_interactivegrid3d_property_unreachable_color:

Color **unreachable_color** = ``Color(0.8039216, 0.36078432, 0.36078432, 1)``

.. rst-class:: classref-property-setget

- void **set_unreachable_color** (value: Color)
- Color **get_unreachable_color** ()

Color used to indicate that the cell is not reachable.

.. rst-class:: classref-item-separator
.. _methods:

Method Descriptions
-------------------

.. _class_InteractiveGrid3D_method_add_custom_cell_data:

.. rst-class:: classref-method

void **add_custom_cell_data** (cell_index: int, custom_data_name: String) :ref:`🔗<class_InteractiveGrid3D_method_add_custom_cell_data>`

Adds custom data to a specific cell.

   - Applies the associated layer mask to the cell.

   - If a custom color is defined, it is applied to the cell.

.. code-block:: gdscript

   var neighbors: Array = interactive_grid_3d.get_neighbors(pawn_current_cell_index)
		
   for neighbor_index in neighbors:
      interactive_grid_3d.add_custom_cell_data(neighbor_index, "CFL_NEIGHBORS")

   interactive_grid_3d.add_custom_cell_data(pawn_current_cell_index, "CFL_PLAYER")

   interactive_grid_3d.update_custom_data()

.. only:: not i18n

  .. note:: You must first define a ``CustomCellData`` resource in the editor inside the ``Custom Cells Data`` array property.
            
            This allows the layer mask to be used inside a GDShader for visual effects or cell-based rendering logic.

.. code-block:: glsl
   :force:

   // interractive_grid.gdshader

   shader_type spatial;
   render_mode unshaded, cull_disabled, depth_draw_opaque;

   varying vec4 instance_c;
   varying vec4 instance_c_default;
   varying float alpha;

   // Default cell flags:
   const int CFL_ACCESSIBLE = 1 << 0;
   const int CFL_REACHABLE = 1 << 1;
   const int CFL_IN_VOID = 1 << 2;
   const int CFL_HOVERED = 1 << 3;
   const int CFL_SELECTED  = 1 << 4;
   const int CFL_PATH = 1 << 5;
   const int CFL_VISIBLE = 1 << 6;

   // Custom cell data:
   const int CFL_PLAYER = 1 << 7;
   const int CFL_NEIGHBORS = 1 << 9;
   const int CFL_TRAP = 1 << 10;
   const int CFL_PULSE = 1 << 8;

   vec3 pulse_color(vec3 base_color, float speed, float min_val, float max_val) {
      float center = (min_val + max_val) * 0.5;
      float range  = (max_val - min_val) * 0.5;
      return base_color * (sin(TIME * speed) * range + center);
   }

   void vertex() {
      instance_c = INSTANCE_CUSTOM;
      int cell_flag = int(instance_c.a);
      alpha = 0.5;
      
      if ((cell_flag & CFL_ACCESSIBLE) == 0) {
         alpha = 0.20;
      }

      if ((cell_flag & CFL_NEIGHBORS) != 0
         && (cell_flag & CFL_PATH) == 0
         && (cell_flag & CFL_TRAP) == 0)
         {
            if ((cell_flag & CFL_ACCESSIBLE) != 0) {
               alpha = 0.40;
               instance_c.r = 0.2;
               instance_c.g = 0.5;
               instance_c.b = 1.0;
            }
         }
      
      if ((cell_flag & CFL_PATH) != 0) {
         VERTEX.y += sin(TIME * 4.0 + VERTEX.x * 2.0) * 0.2;
      }
      
      if ((cell_flag & CFL_HOVERED) != 0) {
         VERTEX.y += sin(TIME * 4.0) * 0.2;
      }
      
      if ((cell_flag & CFL_TRAP) != 0) {
         VERTEX.y += sin(TIME * 4.0 + VERTEX.x * 2.0) * 0.2;
      }
      
      if ((cell_flag & CFL_PULSE) != 0) {
         instance_c.rgb = pulse_color(vec3(instance_c.rgb), 4.0, 0.3, 0.8);
      }
      
      if ((cell_flag & CFL_VISIBLE) == 0) {
         alpha = 0.0; // invisible
      }
      
      if ((cell_flag & CFL_REACHABLE) == 0) {
         alpha = 0.0; // invisible
      }
      
      if ((cell_flag & CFL_IN_VOID) != 0) {
         alpha = 0.0; // invisible
      }
   }

   void fragment() {
      if (alpha == 0.0) {
         discard;
      }
      ALBEDO = instance_c.rgb;
      EMISSION = instance_c.rgb;
      ALPHA = alpha;
   }

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_center:

void **center** (center_position: Vector3) :ref:`🔗<class_InteractiveGrid3D_method_center>`

   Centers the grid around the given ``global position`` and rebuilds its layout.

.. only:: not i18n

  .. note:: This operation repositions all cells, realigns them with the environment,
            rescans obstacles and custom data, and refreshes A* navigation.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_clear_all_custom_cell_data:

void **clear_all_custom_cell_data** (cell_index: int) :ref:`🔗<class_InteractiveGrid3D_method_clear_all_custom_cell_data>`

   Resets the cell's ``custom_flags`` and removes any ``custom_color``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_clear_custom_cell_data:

void **clear_custom_cell_data** (cell_index: int, custom_data_name: String, clear_custom_color: bool) :ref:`🔗<class_InteractiveGrid3D_method_clear_custom_cell_data>`

   Resets the custom data of a given cell.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_compute_unreachable_cells:

void **compute_unreachable_cells** (start_cell_index: int) :ref:`🔗<class_InteractiveGrid3D_method_compute_unreachable_cells>`

   Iterates over all grid cells and marks as ``unreachable`` those cells
   that cannot be reached from the specified ``start_cell``.

   Updates the visual representation by applying ``unreachable_color`` to the cells.

.. only:: not i18n

  .. note:: ``Unreachable`` cells are not automatically marked as ``unaccessible``, allowing gameplay features
            such as teleportation.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_get_cell_global_position:

Vector3 **get_cell_global_position** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_get_cell_global_position>`

   Returns the ``global_position`` of the cell identified by ``index``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_get_cell_global_transform:

Transform3D **get_cell_global_transform** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_get_cell_global_transform>`

   Returns the ``global Transform3D`` of the cell identified by ``index``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_get_cell_index_from_global_position:

int **get_cell_index_from_global_position** (global_position: Vector3) const :ref:`🔗<class_InteractiveGrid3D_method_get_cell_index_from_global_position>`

   Returns the ``index`` of the grid cell that is closest to the supplied world position.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_get_cell_transform:

Transform3D **get_cell_transform** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_get_cell_transform>`

   Returns the ``local Transform3D`` of the cell identified by ``index``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_get_center_global_position:

Vector3 **get_center_global_position** (global_position: Vector3) const :ref:`🔗<class_InteractiveGrid3D_method_get_center_global_position>`

   Returns the ``global_position`` of the center of the grid.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_get_latest_selected:

PackedInt64Array **get_latest_selected** (global_position: Vector3) const :ref:`🔗<class_InteractiveGrid3D_method_get_latest_selected>`

   Returns the most recently ``selected_cell``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_get_neighbors:

Array **get_neighbors** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_get_neighbors>`

   Returns the indices of neighboring cells for the specified grid cell.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_get_path:

PackedInt64Array **get_neighbors** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_get_path>`

   Computes a ``path`` between two cells on the grid using A* pathfinding.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_get_selected_cells:

Array **get_selected_cells** () :ref:`🔗<class_InteractiveGrid3D_method_get_selected_cells>`

   Returns an array of all cells currently marked as ``selected``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_get_size:

int **get_size** () const :ref:`🔗<class_InteractiveGrid3D_method_get_size>`

   Returns the total ``number`` of cells in the grid.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_has_custom_cell_data:

bool **has_custom_cell_data** (cell_index: int, custom_data_name: String) const :ref:`🔗<class_InteractiveGrid3D_method_get_size>`

   Checks if a specific cell has the given ``CustomCellData`` applied.
   Returns ``true`` if the cell's flags include the full layer mask of the specified ``CustomCellData``, otherwise returns ``false``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_hide_distant_cells:

void **hide_distant_cells** (start_cell_index: int, distance: float) const :ref:`🔗<class_InteractiveGrid3D_method_hide_distant_cells>`

   Iterates over all grid cells and hides those located farther than the specified distance from the ``start_cell``. Marks them as ``unaccessible``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_highlight_on_hover:

void **highlight_on_hover** (global_position: Vector3) :ref:`🔗<class_InteractiveGrid3D_method_highlight_on_hover>`

   Updates the hover highlight state based on the specified ``global_position``. 
   Identifies the corresponding cell, clears any previous hover, and applies the hover color unless the cell is already selected.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_highlight_path:

void **highlight_path** (path: PackedInt64Array) :ref:`🔗<class_InteractiveGrid3D_method_highlight_path>`

   Highlights a given path on the grid by changing the color of each cell along the path to the predefined path color.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_is_cell_accessible:

bool **is_cell_accessible** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_is_cell_accessible>`

   Returns ``true`` if the cell at the specified index is currently marked as ``accessible``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_is_cell_hovered:

bool **is_cell_hovered** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_is_cell_hovered>`

   Returns ``true`` if the cell at the specified index is currently marked as hovered.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_is_cell_reachable:

bool **is_cell_reachable** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_is_cell_reachable>`

   Returns ``true`` if the cell at the specified index is currently marked as unreachable.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_is_cell_selected:

bool **is_cell_selected** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_is_cell_selected>`

   Returns ``true`` if the cell at the specified index is currently marked as ``selected``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_is_cell_visible:

bool **is_cell_visible** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_is_cell_visible>`

   Returns ``true`` if the cell at the specified index is currently marked as ``visible``.

.. rst-class:: classref-item-separator

.. _class_InteractiveGrid3D_method_is_grid_created:

bool **is_grid_created** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_is_grid_created>`

   Checks if the grid has been created.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_is_hover_enabled:

bool **is_hover_enabled** (cell_index: int) const :ref:`🔗<class_InteractiveGrid3D_method_is_hover_enabled>`

   Checks whether hover functionality is currently disabled.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_reset_cells_state:

void **reset_cells_state** () :ref:`🔗<class_InteractiveGrid3D_method_reset_cells_state>`

   Clears all ``CustomCellData``, resets ``cell_flags``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_select_cell:

void **select_cell** (cell_index: int) :ref:`🔗<class_InteractiveGrid3D_method_select_cell>`

   Selects a grid cell based on a ``cell_index``.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_set_cell_accessible:

void **set_cell_accessible** (cell_index: int, is_accessible: bool) :ref:`🔗<class_InteractiveGrid3D_method_set_cell_accessible>`

   Sets whether a specific cell is ``accessible`` or not.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_set_cell_color:

void **set_cell_color** (cell_index: int, color: Color) :ref:`🔗<class_InteractiveGrid3D_method_set_cell_color>`

   Sets the ``color`` of a specific cell.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_set_cell_reachable:

void **set_cell_reachable** (cell_index: int, set_cell_reachable: bool) :ref:`🔗<class_InteractiveGrid3D_method_set_cell_reachable>`

   Sets whether a given grid cell is ``unreachable``.

.. rst-class:: classref-item-separator

.. _class_InteractiveGrid3D_method_set_hover_enabled:

void **set_hover_enabled** (enabled: bool) :ref:`🔗<class_InteractiveGrid3D_method_set_hover_enabled>`

   Enables or disables hover functionality.

.. rst-class:: classref-item-separator

----

.. _class_InteractiveGrid3D_method_update_custom_data:

void **update_custom_data** () :ref:`🔗<class_InteractiveGrid3D_method_update_custom_data>`

   Refreshes ``custom_cell_flags``, colors, and A* configuration based on the current ``CellCustomData``.

.. rst-class:: classref-item-separator

----