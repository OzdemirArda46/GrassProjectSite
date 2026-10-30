# GrassFX Project Information and Syntax Analysis

## 1. General Information and Version History
* **Project Context:** GrassFX is a sub-project within the GrassProject ecosystem.
* **Purpose:** To facilitate easy GUI (Graphical User Interface) and application development.
* **Supported Operating System:** GNU/Linux
* **Programming Language:** C

### Version History
* **GrassFX 0.01:** September 17, 2026
* **GrassFX 0.02:** September 20, 2026
* **GrassFX 0.03:** September 27, 2026
* **GrassFX 0.1:** October 18, 2026
* **GrassFX 0.2:** October 30, 2026

---

## 2. Rules and Syntax Structure

### Rules
* **Naming Style:** `snake_case` is used throughout the library.
* **Library Prefix:** Must always be at the very beginning of the function name.
* **Feature (Modifier):** Located at the very end of the function name.
* **Action (Verb):** Always placed to the left of the feature.
* **Readability:** Function signatures must be clear and intuitive.
* **Featureless Cases:** If no specific feature is needed, the action may be placed at the end.
* **General Functions:** May consist of only the library prefix and an action.

### Syntax Breakdown & Example Analysis
**Example function:** `gfx_object_add_button(Evas_Object *parent);`

**Element Breakdown:**
* `gfx`: Library prefix
* `object`: Target object
* `add`: Action
* `button`: Feature / specific widget type
* `Evas_Object *parent`: Function parameter

---

# GrassFX Library API Documentation

This document details all function signatures, descriptions, and parameter specifications for the **GrassFX** abstraction layer based on EFL (Enlightenment Foundation Libraries).

---

## 1. Common Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `void` | `gfx_init(int argc, char **argv)` | Initializes the GrassFX library and its dependencies, parses command line arguments. | **argc:** Command-line argument count (0 or greater).<br>**argv:** Command-line argument array (NULL or char** array). |
| `void` | `gfx_run(void)` | Launches the main GUI event loop and blocks until the application terminates. | *Takes no parameters.* |
| `void` | `gfx_exit(void)` | Sends an exit signal to the running graphic loop and begins termination. | *Takes no parameters.* |
| `void` | `gfx_shutdown(void)` | Shuts down the library and releases all allocated system resources. | *Takes no parameters.* |

---

## 2. Window Management Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Evas_Object *` | `gfx_object_add_feature_window(const char *name, const char *title)` | Creates a new main application window pre-configured with essential features. | **name:** Internal identifier (valid non-empty string).<br>**title:** Window title text (valid string or empty string). |
| `Evas_Object *` | `gfx_object_add_standard_window(Evas_Object *parent, const char *name, Elm_Win_Type type)` | Creates a standard Elementary window object of the specified type. | **parent:** Parent window pointer (Evas_Object* or NULL for standalone).<br>**name:** Window name (valid string).<br>**type:** Window type (ELM_WIN_BASIC, ELM_WIN_DIALOG, etc.). |
| `void` | `gfx_window_set_title(Evas_Object *object, const char *title)` | Updates the title text displayed on the window bar. | **object:** Valid window object (Evas_Object*).<br>**title:** Title string to display (const char* or NULL). |
| `void` | `gfx_window_set_autodel(Evas_Object *object, Eina_Bool autodel)` | Configures whether the window is automatically deleted from memory upon close. | **object:** Valid window object (Evas_Object*).<br>**autodel:** Auto-delete flag (EINA_TRUE or EINA_FALSE). |
| `void` | `gfx_window_set_center(Evas_Object *object, Eina_Bool h, Eina_Bool v)` | Centers the window on screen horizontally and/or vertically. | **object:** Valid window object (Evas_Object*).<br>**h:** Center horizontally (EINA_TRUE/EINA_FALSE).<br>**v:** Center vertically (EINA_TRUE/EINA_FALSE). |
| `void` | `gfx_window_set_minsize(Evas_Object *object, int w, int h)` | Restricts the minimum pixel dimensions allowed for the window. | **object:** Valid window object (Evas_Object*).<br>**w:** Minimum width in pixels (0 or greater).<br>**h:** Minimum height in pixels (0 or greater). |
| `void` | `gfx_window_set_fullscreen(Evas_Object *object, Eina_Bool full)` | Toggles window fullscreen mode on or off. | **object:** Valid window object (Evas_Object*).<br>**full:** Fullscreen toggle (EINA_TRUE enables, EINA_FALSE disables). |
| `void` | `gfx_window_set_active(Evas_Object *object)` | Sets the window as active at the system level and shifts focus to it. | **object:** Target window object (Evas_Object*). |
| `void` | `gfx_window_set_iconified(Evas_Object *object, Eina_Bool iconified)` | Minimizes the window to system tray/icon state or restores it. | **object:** Valid window object (Evas_Object*).<br>**iconified:** Minimize toggle (EINA_TRUE minimizes, EINA_FALSE restores). |
| `void` | `gfx_window_set_sticky(Evas_Object *object, Eina_Bool sticky)` | Makes the window sticky across all virtual desktops. | **object:** Valid window object (Evas_Object*).<br>**sticky:** Sticky toggle (EINA_TRUE fixes on all desktops, EINA_FALSE binds to single). |
| `void` | `gfx_window_proportion_scale(Evas_Object *object, Evas_Object *subobject)` | Rescales a child object proportionally based on the window aspect ratio. | **object:** Parent window (Evas_Object*).<br>**subobject:** Child component to scale (Evas_Object*). |
| `void` | `gfx_window_set_autohide(Evas_Object *object, Eina_Bool autohide)` | Hides the window instead of destroying it when a close event occurs. | **object:** Valid window object (Evas_Object*).<br>**autohide:** Auto-hide flag (EINA_TRUE or EINA_FALSE). |
| `void` | `gfx_window_set_borderless(Evas_Object *object, Eina_Bool borderless)` | Hides or shows window borders and title bar. | **object:** Valid window object (Evas_Object*).<br>**borderless:** Borderless mode (EINA_TRUE borderless, EINA_FALSE standard frame). |
| `Eina_Bool` | `gfx_window_get_borderless(const Evas_Object *object)` | Queries whether the window is currently in borderless mode. | **object:** Window to inspect (const Evas_Object*). |
| `void` | `gfx_window_set_shaped(Evas_Object *object, Eina_Bool shaped)` | Configures custom shaped drawing based on transparent pixels. | **object:** Valid window object (Evas_Object*).<br>**shaped:** Shaped window mode (EINA_TRUE/EINA_FALSE). |
| `Eina_Bool` | `gfx_window_get_shaped(const Evas_Object *object)` | Returns whether the window is in shaped mode. | **object:** Window to inspect (const Evas_Object*). |
| `void` | `gfx_window_set_alpha(Evas_Object *object, Eina_Bool alpha)` | Enables or disables alpha channel transparency for the canvas. | **object:** Valid window object (Evas_Object*).<br>**alpha:** Alpha channel state (EINA_TRUE enables transparency, EINA_FALSE disables). |
| `Eina_Bool` | `gfx_window_get_alpha(const Evas_Object *object)` | Returns whether alpha channel transparency is enabled for the window. | **object:** Window to inspect (const Evas_Object*). |

---

## 3. Widget Addition Functions

All functions in this section attach the respective UI component to the given parent and return its object pointer:

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Evas_Object *` | `gfx_object_add_button(Evas_Object *parent)` | Creates a standard clickable UI button. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_checkbutton(Evas_Object *parent)` | Creates a two-state check box component (checked/unchecked). | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_radiobutton(Evas_Object *parent)` | Creates a radio button component for single-selection groups. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_entry(Evas_Object *parent)` | Creates a text input field for user entry. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_slider(Evas_Object *parent)` | Creates a slider bar for numerical value selection within a range. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_spinner(Evas_Object *parent)` | Creates a spinner input component with increment/decrement buttons. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_combobox(Evas_Object *parent)` | Creates a dropdown list (combo box) component. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_label(Evas_Object *parent)` | Creates a label component for displaying plain or formatted text. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_icon(Evas_Object *parent)` | Creates a standard icon object matching the system theme. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_image(Evas_Object *parent)` | Creates an image widget for loading and displaying graphics files. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_progressbar(Evas_Object *parent)` | Creates a progress bar component to indicate task status. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_bubble(Evas_Object *parent)` | Creates a speech/info bubble container widget. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_clock(Evas_Object *parent)` | Creates a clock widget displaying real-time clock and time. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_calendar(Evas_Object *parent)` | Creates a calendar component for date selection and viewing. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_separator(Evas_Object *parent)` | Adds a vertical or horizontal visual separator line between widgets. | **parent:** Parent object (valid Evas_Object*). |
| `Evas_Object *` | `gfx_object_add_popup(Evas_Object *parent)` | Creates a modal notification/alert window (popup) for user interaction. | **parent:** Parent object (valid Evas_Object*). |

---

## 4. Container and Layout Functions

### Box Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Evas_Object *` | `gfx_object_add_box(Evas_Object *parent)` | Creates a box container that arranges child elements in a single direction. | **parent:** Parent object pointer (valid Evas_Object*). |
| `void` | `gfx_box_set_horizontal(Evas_Object *object, Eina_Bool horizontal)` | Sets the box orientation to horizontal or vertical. | **object:** Box object (Evas_Object*).<br>**horizontal:** Orientation flag (EINA_TRUE horizontal, EINA_FALSE vertical). |
| `Eina_Bool` | `gfx_box_get_horizontal(const Evas_Object *object)` | Queries whether the box is in horizontal layout mode. | **object:** Box object (const Evas_Object*). |
| `void` | `gfx_box_pack_start(Evas_Object *object, Evas_Object *child)` | Packs a child object at the very beginning of the box. | **object:** Target box (Evas_Object*).<br>**child:** Child component to add (Evas_Object*). |
| `void` | `gfx_box_pack_end(Evas_Object *object, Evas_Object *child)` | Packs a child object at the very end of the box. | **object:** Target box (Evas_Object*).<br>**child:** Child component to add (Evas_Object*). |
| `void` | `gfx_box_pack_before(Evas_Object *object, Evas_Object *child, Evas_Object *before)` | Inserts a child object immediately before a specific reference object in the box. | **object:** Target box (Evas_Object*).<br>**child:** Object to insert (Evas_Object*).<br>**before:** Reference object in box (Evas_Object*). |
| `void` | `gfx_box_pack_after(Evas_Object *object, Evas_Object *child, Evas_Object *after)` | Inserts a child object immediately after a specific reference object in the box. | **object:** Target box (Evas_Object*).<br>**child:** Object to insert (Evas_Object*).<br>**after:** Reference object in box (Evas_Object*). |
| `void` | `gfx_box_unpack(Evas_Object *object, Evas_Object *child)` | Removes the specified child from the box without destroying it in memory. | **object:** Target box (Evas_Object*).<br>**child:** Child object to remove (Evas_Object*). |
| `void` | `gfx_box_unpack_all(Evas_Object *object)` | Removes all child components from the box. | **object:** Box to empty (Evas_Object*). |
| `void` | `gfx_box_set_homogeneous(Evas_Object *object, Eina_Bool homogeneous)` | Forces all elements in the box to occupy equal space or allows dynamic sizing. | **object:** Box object (Evas_Object*).<br>**homogeneous:** Homogeneous flag (EINA_TRUE equal space, EINA_FALSE dynamic). |
| `Eina_Bool` | `gfx_box_get_homogeneous(Evas_Object *object)` | Queries whether the box is in homogeneous layout mode. | **object:** Box object (Evas_Object*). |
| `void` | `gfx_box_set_padding(Evas_Object *object, Evas_Coord horizontal, Evas_Coord vertical)` | Sets horizontal and vertical spacing pixels between child elements. | **object:** Box object (Evas_Object*).<br>**horizontal:** Horizontal gap (Evas_Coord, 0 or greater).<br>**vertical:** Vertical gap (Evas_Coord, 0 or greater). |
| `void` | `gfx_box_get_padding(Evas_Object *object, Evas_Coord *horizontal, Evas_Coord *vertical)` | Reads the current element spacing values. | **object:** Box object (Evas_Object*).<br>**horizontal:** Pointer for horizontal gap (Evas_Coord* or NULL).<br>**vertical:** Pointer for vertical gap (Evas_Coord* or NULL). |
| `void` | `gfx_box_set_align(Evas_Object *object, double horizontal, double vertical)` | Sets alignment ratio of elements inside the box area. | **object:** Box object (Evas_Object*).<br>**horizontal:** Horizontal alignment (0.0 left, 0.5 center, 1.0 right).<br>**vertical:** Vertical alignment (0.0 top, 0.5 center, 1.0 bottom). |
| `void` | `gfx_box_get_align(Evas_Object *object, double *horizontal, double *vertical)` | Reads the alignment factors of the box. | **object:** Box object (Evas_Object*).<br>**horizontal:** Horizontal alignment pointer (double* or NULL).<br>**vertical:** Vertical alignment pointer (double* or NULL). |
| `Eina_List *` | `gfx_box_get_children(const Evas_Object *object)` | Returns a linked list of all child components in the box. | **object:** Box object (const Evas_Object*). |

### Grid Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Evas_Object *` | `gfx_object_add_grid(Evas_Object *parent)` | Creates a virtual coordinate grid layout container. | **parent:** Parent object pointer (valid Evas_Object*). |
| `void` | `gfx_grid_set_size(Evas_Object *object, int w, int h)` | Defines virtual resolution boundaries for the grid (e.g., 100x100). | **object:** Grid object (Evas_Object*).<br>**w:** Virtual width unit (int greater than 0, default 100).<br>**h:** Virtual height unit (int greater than 0, default 100). |
| `void` | `gfx_grid_get_size(const Evas_Object *object, int *w, int *h)` | Reads defined virtual grid dimensions. | **object:** Grid object (const Evas_Object*).<br>**w, h:** Integer pointers to receive dimensions (int* or NULL). |
| `void` | `gfx_grid_add_pack(Evas_Object *object, Evas_Object *subobject, int x, int y, int w, int h)` | Adds a child to the grid and sets its virtual coordinates and dimensions. | **object:** Grid object (Evas_Object*).<br>**subobject:** Object to add (Evas_Object*).<br>**x, y:** Starting virtual coordinates (0 to grid width/height).<br>**w, h:** Virtual width and height span (greater than 0). |
| `void` | `gfx_grid_unpack(Evas_Object *object, Evas_Object *subobject)` | Removes a child object from the grid. | **object:** Grid object (Evas_Object*).<br>**subobject:** Object to remove (Evas_Object*). |
| `void` | `gfx_grid_set_pack(Evas_Object *subobject, Evas_Coord x, Evas_Coord y, Evas_Coord w, Evas_Coord h)` | Updates virtual layout for a child previously added to a grid. | **subobject:** Grid child object (Evas_Object*).<br>**x, y:** New virtual coordinates (Evas_Coord).<br>**w, h:** New virtual dimensions (Evas_Coord greater than 0). |
| `void` | `gfx_grid_get_pack(Evas_Object *subobject, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)` | Returns current virtual coordinates and dimensions of a grid child. | **subobject:** Child object (Evas_Object*).<br>**x, y, w, h:** Pointers to receive values (Evas_Coord* or NULL). |
| `Eina_List *` | `gfx_grid_get_children(const Evas_Object *object)` | Returns linked list of child components attached to the grid. | **object:** Grid object (const Evas_Object*). |
| `void` | `gfx_grid_clear(Evas_Object *object, Eina_Bool clear)` | Removes children from the grid and optionally deletes them from memory. | **object:** Grid object (Evas_Object*).<br>**clear:** Memory deletion flag (EINA_TRUE destroys objects, EINA_FALSE only removes). |

### Table Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Evas_Object *` | `gfx_object_add_table(Evas_Object *parent)` | Creates a row-and-column matrix layout container. | **parent:** Parent object pointer (valid Evas_Object*). |
| `void` | `gfx_table_set_align(Evas_Object *object, double horizontal, double vertical)` | Sets horizontal and vertical alignment ratios of the table within its parent. | **object:** Table object (Evas_Object*).<br>**horizontal:** Horizontal ratio (0.0 to 1.0).<br>**vertical:** Vertical ratio (0.0 to 1.0). |
| `void` | `gfx_table_get_align(const Evas_Object *object, double *horizontal, double *vertical)` | Reads table alignment ratios. | **object:** Table object (const Evas_Object*).<br>**horizontal, vertical:** Double pointers to receive values (double* or NULL). |
| `Evas_Object *` | `gfx_table_get_child(const Evas_Object *object, int col, int row)` | Returns child object located at specified column and row intersection. | **object:** Table object (const Evas_Object*).<br>**col:** Column index (0 or greater).<br>**row:** Row index (0 or greater). |
| `void` | `gfx_table_clear(Evas_Object *object, Eina_Bool clear)` | Removes all items from table and optionally deletes them. | **object:** Table object (Evas_Object*).<br>**clear:** Deletion flag (EINA_TRUE destroys objects, EINA_FALSE removes only). |
| `void` | `gfx_table_set_homogeneous(Evas_Object *object, Eina_Bool homogeneous)` | Forces all table cells to uniform width/height or allows dynamic sizing. | **object:** Table object (Evas_Object*).<br>**homogeneous:** Homogeneous flag (EINA_TRUE or EINA_FALSE). |
| `Eina_Bool` | `gfx_table_get_homogeneous(const Evas_Object *object)` | Queries whether table uses uniform cell sizing. | **object:** Table object (const Evas_Object*). |
| `void` | `gfx_table_pack(Evas_Object *object, Evas_Object *subobject, int col, int row, int colspan, int rowspan)` | Adds child to table at specified cell position with row/column span support. | **object:** Table object (Evas_Object*).<br>**subobject:** Object to add (Evas_Object*).<br>**col, row:** Column and row indices (0 or greater).<br>**colspan, rowspan:** Column and row span count (1 or greater). |
| `void` | `gfx_table_set_pack(Evas_Object *subobject, int col, int row, int colspan, int rowspan)` | Updates cell position and span area of an item in table. | **subobject:** Table child object (Evas_Object*).<br>**col, row:** New column and row (0 or greater).<br>**colspan, rowspan:** New span counts (1 or greater). |
| `void` | `gfx_table_get_pack(Evas_Object *subobject, int *col, int *row, int *colspan, int *rowspan)` | Reads cell position and span dimensions of a table child. | **subobject:** Child object (Evas_Object*).<br>**col, row, colspan, rowspan:** Pointers to receive integer values (int* or NULL). |
| `void` | `gfx_table_set_padding(Evas_Object *object, Evas_Coord horizontal, Evas_Coord vertical)` | Sets horizontal and vertical padding between table cells. | **object:** Table object (Evas_Object*).<br>**horizontal:** Horizontal gap (Evas_Coord, 0 or greater).<br>**vertical:** Vertical gap (Evas_Coord, 0 or greater). |
| `void` | `gfx_table_get_padding(Evas_Object *object, Evas_Coord *horizontal, Evas_Coord *vertical)` | Reads table cell padding values. | **object:** Table object (Evas_Object*).<br>**horizontal, vertical:** Pointers to receive values (Evas_Coord* or NULL). |
| `void` | `gfx_table_unpack(Evas_Object *object, Evas_Object *subobject)` | Removes child object from table. | **object:** Table object (Evas_Object*).<br>**subobject:** Object to remove (Evas_Object*). |

### Scroller Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Evas_Object *` | `gfx_object_add_scroller(Evas_Object *parent)` | Creates a scrollable container for content exceeding viewport bounds. | **parent:** Parent object pointer (valid Evas_Object*). |
| `void` | `gfx_scroller_set_policy(Evas_Object *object, Elm_Scroller_Policy policy_h, Elm_Scroller_Policy policy_v)` | Sets visibility policy for horizontal and vertical scrollbars. | **object:** Scroller object (Evas_Object*).<br>**policy_h, policy_v:** Scrollbar policies (ELM_SCROLLER_POLICY_AUTO, ALWAYS, OFF, etc.). |
| `void` | `gfx_scroller_get_policy(const Evas_Object *object, Elm_Scroller_Policy *policy_h, Elm_Scroller_Policy *policy_v)` | Reads current scrollbar visibility policies. | **object:** Scroller object (const Evas_Object*).<br>**policy_h, policy_v:** Pointers to receive policy values (Elm_Scroller_Policy* or NULL). |
| `void` | `gfx_scroller_set_region(Evas_Object *object, Evas_Coord x, Evas_Coord y, Evas_Coord w, Evas_Coord h)` | Scrolls/focuses view directly to specified coordinate and dimension area. | **object:** Scroller object (Evas_Object*).<br>**x, y:** Target coordinates (Evas_Coord, 0 or greater).<br>**w, h:** Target width and height (Evas_Coord, greater than 0). |
| `void` | `gfx_scroller_get_region(const Evas_Object *object, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)` | Returns coordinates and dimensions of currently visible content region. | **object:** Scroller object (const Evas_Object*).<br>**x, y, w, h:** Pointers for position and size (Evas_Coord* or NULL). |
| `void` | `gfx_scroller_get_position(const Evas_Object *object, Evas_Coord *x, Evas_Coord *y)` | Reads current scroll offset point in pixels. | **object:** Scroller object (const Evas_Object*).<br>**x, y:** Pointers to receive offset (Evas_Coord* or NULL). |
| `void` | `gfx_scroller_set_pagesize(Evas_Object *object, Evas_Coord w, Evas_Coord h)` | Sets page width/height step size for paging scroll mode. | **object:** Scroller object (Evas_Object*).<br>**w, h:** Page pixel size (Evas_Coord, 0 or greater). |
| `void` | `gfx_scroller_get_pagesize(const Evas_Object *object, Evas_Coord *w, Evas_Coord *h)` | Reads configured page size. | **object:** Scroller object (const Evas_Object*).<br>**w, h:** Pointers to receive page dimensions (Evas_Coord* or NULL). |
| `void` | `gfx_scroller_get_currentpage(const Evas_Object *object, int *hp, int *vp)` | Returns active horizontal and vertical page index numbers. | **object:** Scroller object (const Evas_Object*).<br>**hp, vp:** Pointers for page numbers (int*, 0 or greater, or NULL). |
| `void` | `gfx_scroller_show_page(Evas_Object *object, int hp, int vp)` | Automatically scrolls to specified page index. | **object:** Scroller object (Evas_Object*).<br>**hp, vp:** Target page indices (0 or greater). |
| `void` | `gfx_scroller_set_bounce(Evas_Object *object, Eina_Bool h_bounce, Eina_Bool v_bounce)` | Enables or disables bounce/elastic animation when reaching edges. | **object:** Scroller object (Evas_Object*).<br>**h_bounce, v_bounce:** Bounce effect flags (EINA_TRUE enabled, EINA_FALSE disabled). |
| `void` | `gfx_scroller_get_bounce(const Evas_Object *object, Eina_Bool *h_bounce, Eina_Bool *v_bounce)` | Reads bounce effect status flags. | **object:** Scroller object (const Evas_Object*).<br>**h_bounce, v_bounce:** Pointers to receive flags (Eina_Bool* or NULL). |

### Frame Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Evas_Object *` | `gfx_object_add_frame(Evas_Object *parent)` | Creates decorative frame widget with border and title. | **parent:** Parent object pointer (valid Evas_Object*). |
| `void` | `gfx_frame_set_autocollapse(Evas_Object *object, Eina_Bool autocollapse)` | Enables auto-collapsing/expanding frame when title is clicked. | **object:** Frame object (Evas_Object*).<br>**autocollapse:** Auto-collapse state (EINA_TRUE enabled, EINA_FALSE disabled). |
| `Eina_Bool` | `gfx_frame_get_autocollapse(const Evas_Object *object)` | Queries whether frame auto-collapse mode is active. | **object:** Frame object (const Evas_Object*). |
| `void` | `gfx_frame_set_collapse(Evas_Object *object, Eina_Bool collapse)` | Programmatically collapses or expands frame immediately. | **object:** Frame object (Evas_Object*).<br>**collapse:** Collapse flag (EINA_TRUE collapses, EINA_FALSE expands). |
| `Eina_Bool` | `gfx_frame_get_collapse(const Evas_Object *object)` | Returns whether frame is currently collapsed. | **object:** Frame object (const Evas_Object*). |

---

## 5. Object Management & State

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `void` | `gfx_object_set_text(Evas_Object *object, const char *text)` | Sets default text content of any UI object. | **object:** Target object (Evas_Object*).<br>**text:** Text string to set (const char* or NULL). |
| `const char *` | `gfx_object_get_text(const Evas_Object *object)` | Returns current default text content of object. | **object:** Object to inspect (const Evas_Object*). |
| `void` | `gfx_object_set_content(Evas_Object *object, Evas_Object *content)` | Attaches another object into primary content area of container. | **object:** Container object (Evas_Object*).<br>**content:** Content object (Evas_Object* or NULL to empty). |
| `Evas_Object *` | `gfx_object_get_content(const Evas_Object *object)` | Returns object attached to primary content area of container. | **object:** Container object (const Evas_Object*). |
| `void` | `gfx_image_set_file(Evas_Object *object, const char *file, const char *group)` | Assigns image or Edje file from disk to image object. | **object:** Image object (Evas_Object*).<br>**file:** File path string.<br>**group:** Edje group name (const char* or NULL for standard images). |
| `void` | `gfx_icon_set_standard(Evas_Object *object, const char *name)` | Assigns freedesktop system standard icon name to icon object. | **object:** Icon object (Evas_Object*).<br>**name:** Standard icon name (e.g., "home", "folder", "close"). |
| `void` | `gfx_object_set_parttext(Evas_Object *object, const char *part, const char *text)` | Sets text on named part within object's Edje theme. | **object:** Target object (Evas_Object*).<br>**part:** Part name (e.g., "elm.text", "elm.guide").<br>**text:** Text to set (const char* or NULL). |
| `void` | `gfx_object_set_partcontent(Evas_Object *object, const char *part, Evas_Object *content)` | Places child object into named swallow part of object theme. | **object:** Target object (Evas_Object*).<br>**part:** Part name (e.g., "elm.swallow.icon", "elm.swallow.content").<br>**content:** Object to insert (Evas_Object* or NULL to empty). |
| `void` | `gfx_set_policy(unsigned int policy, int value)` | Configures general Elementary global policy rules (exit behavior, etc.). | **policy:** Policy type (ELM_POLICY_QUIT, etc.).<br>**value:** Policy value (ELM_POLICY_QUIT_LAST_WINDOW_CLOSED, etc.). |
| `void` | `gfx_object_set_disabled(Evas_Object *object, Eina_Bool disabled)` | Disables user interaction for widget or re-enables it. | **object:** Target object (Evas_Object*).<br>**disabled:** Lock state (EINA_TRUE disables, EINA_FALSE enables). |

### Entry and State Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `void` | `gfx_entry_set_text(Evas_Object *object, const char *text)` | Updates text contained in entry input field. | **object:** Entry object (Evas_Object*).<br>**text:** Text string to enter (const char* or NULL). |
| `const char *` | `gfx_entry_get_text(const Evas_Object *object)` | Returns current text in entry input box. | **object:** Entry object (const Evas_Object*). |
| `void` | `gfx_entry_set_singleline(Evas_Object *object, Eina_Bool single_line)` | Sets entry field to single-line mode or allows multi-line entry. | **object:** Entry object (Evas_Object*).<br>**single_line:** Single-line flag (EINA_TRUE single line, EINA_FALSE multi-line). |
| `void` | `gfx_entry_set_password(Evas_Object *object, Eina_Bool password)` | Enables password masking mode using asterisks or dots. | **object:** Entry object (Evas_Object*).<br>**password:** Password mode flag (EINA_TRUE masks, EINA_FALSE shows text). |
| `void` | `gfx_check_set_state(Evas_Object *object, Eina_Bool checked)` | Changes check state of checkbox widget. | **object:** Check object (Evas_Object*).<br>**checked:** State flag (EINA_TRUE checked, EINA_FALSE unchecked). |
| `Eina_Bool` | `gfx_check_get_state(const Evas_Object *object)` | Returns whether checkbox is currently checked. | **object:** Check object (const Evas_Object*). |
| `void` | `gfx_radio_set_statevalue(Evas_Object *object, int value)` | Sets integer state value represented when radio button is selected. | **object:** Radio object (Evas_Object*).<br>**value:** Integer state ID for button. |
| `void` | `gfx_radio_set_value(Evas_Object *object, int value)` | Sets current active value of radio button group to specified value. | **object:** Radio object (Evas_Object*).<br>**value:** State value to select. |
| `int` | `gfx_radio_get_value(const Evas_Object *object)` | Returns state value of currently selected radio button in group. | **object:** Radio object (const Evas_Object*). |
| `void` | `gfx_radio_add_group(Evas_Object *object, Evas_Object *group)` | Binds radio button to logical group created by another radio button. | **object:** Radio object joining group (Evas_Object*).<br>**group:** Group leader radio object (Evas_Object*). |
| `void` | `gfx_radio_set_pointervalue(Evas_Object *object, int *valuep)` | Binds radio selection directly to memory address of C integer variable. | **object:** Radio object (Evas_Object*).<br>**valuep:** Pointer to integer variable to keep in sync (int* or NULL). |
| `void` | `gfx_slider_set_minmax(Evas_Object *object, double min, double max)` | Defines minimum and maximum bound values selectable on slider. | **object:** Slider object (Evas_Object*).<br>**min, max:** Range bounds (double, min must be less than max). |
| `void` | `gfx_slider_set_unitformat(Evas_Object *object, const char *format)` | Sets printf-compatible formatting string for value display on slider. | **object:** Slider object (Evas_Object*).<br>**format:** Format string (e.g., "%1.2f %%", "%d"). |
| `void` | `gfx_slider_set_value(Evas_Object *object, double value)` | Updates current numeric value and indicator position of slider. | **object:** Slider object (Evas_Object*).<br>**value:** Value to set (double between min and max). |
| `double` | `gfx_slider_get_value(const Evas_Object *object)` | Returns current value of slider. | **object:** Slider object (const Evas_Object*). |

### Genlist Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Elm_Object_Item *` | `gfx_genlist_add_item(Evas_Object *object, const Elm_Genlist_Item_Class *itc, const void *data, Elm_Object_Item *parent, Elm_Genlist_Item_Type type, Evas_Smart_Cb func, const void *func_data)` | Adds new dynamic item to Genlist (generic list) component. | **object:** Genlist object (Evas_Object*).<br>**itc:** Item class definition.<br>**data:** Custom user data pointer attached to item.<br>**parent:** Parent item for tree structure (NULL for root).<br>**type:** Item type (ELM_GENLIST_ITEM_NONE, TREE, GROUP, etc.).<br>**func:** Selection callback function (Evas_Smart_Cb or NULL).<br>**func_data:** User data passed to callback (const void* or NULL). |
| `void` | `gfx_genlist_clear(Evas_Object *object)` | Clears all items from list and frees memory. | **object:** Genlist object (Evas_Object*). |
| `Elm_Genlist_Item_Class *` | `gfx_genlist_add_itemclass(void)` | Allocates and initializes new Genlist item class structure. | *Takes no parameters.* |
| `void` | `gfx_genlist_free_itemclass(Elm_Genlist_Item_Class *itemclass)` | Frees previously allocated Genlist item class structure from memory. | **itemclass:** Item class pointer to free (Elm_Genlist_Item_Class*). |

### Background Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Evas_Object *` | `gfx_object_add_background(Evas_Object *parent)` | Creates colored or image background widget for windows or containers. | **parent:** Parent object pointer (valid Evas_Object*). |
| `void` | `gfx_background_set_file(Evas_Object *object, const char *file, const char *group)` | Loads image or Edje theme file for background. | **object:** Background object (Evas_Object*).<br>**file:** File path string.<br>**group:** Edje group name (const char* or NULL for plain images). |
| `void` | `gfx_background_get_file(const Evas_Object *object, const char **file, const char **group)` | Returns file path and group name used in background. | **object:** Background object (const Evas_Object*).<br>**file, group:** String pointer addresses to receive values (const char** or NULL). |
| `void` | `gfx_background_set_option(Evas_Object *object, Elm_Bg_Option option)` | Sets background image layout/scaling mode (center, tile, scale, stretch). | **object:** Background object (Evas_Object*).<br>**option:** Layout mode (ELM_BG_OPTION_CENTER, SCALE, STRETCH, TILE, etc.). |
| `Elm_Bg_Option` | `gfx_background_get_option(const Evas_Object *object)` | Returns current layout/scaling option of background. | **object:** Background object (const Evas_Object*). |
| `void` | `gfx_background_set_color(Evas_Object *object, int r, int g, int b)` | Assigns solid RGB color fill to background. | **object:** Background object (Evas_Object*).<br>**r, g, b:** Red, green, blue values (each integer 0 to 255). |
| `void` | `gfx_background_get_color(const Evas_Object *object, int *r, int *g, int *b)` | Reads current RGB color components of background. | **object:** Background object (const Evas_Object*).<br>**r, g, b:** Integer pointers to receive values (int* or NULL). |
| `void` | `gfx_background_set_loadsize(Evas_Object *object, int w, int h)` | Configures load resolution of image into memory for performance optimization. | **object:** Background object (Evas_Object*).<br>**w, h:** Loading resolution width and height in pixels (0 or greater). |

### Menu Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Evas_Object *` | `gfx_object_add_menu(Evas_Object *parent)` | Creates popup/context menu container object. | **parent:** Parent object pointer (valid Evas_Object*). |
| `Elm_Object_Item *` | `gfx_menu_add_item(Evas_Object *object, Elm_Object_Item *parent, const char *icon, const char *label, Evas_Smart_Cb func, const void *data)` | Adds new clickable item to menu or submenu. | **object:** Menu object (Evas_Object*).<br>**parent:** Parent menu item (Elm_Object_Item* or NULL for main menu).<br>**icon:** Icon name (const char* or NULL).<br>**label:** Display text (const char*).<br>**func:** Click callback function (Evas_Smart_Cb or NULL).<br>**data:** User data passed to callback (const void* or NULL). |
| `void` | `gfx_menu_add_separator(Evas_Object *object, Elm_Object_Item *parent)` | Adds horizontal separator line between menu items. | **object:** Menu object (Evas_Object*).<br>**parent:** Parent submenu item (Elm_Object_Item* or NULL for root). |
| `Elm_Object_Item *` | `gfx_menu_add_submenu(Evas_Object *object, Elm_Object_Item *parent, const char *icon, const char *label)` | Creates submenu branch expanding on hover/click. | **object:** Menu object (Evas_Object*).<br>**parent:** Parent menu item (Elm_Object_Item* or NULL for root).<br>**icon:** Icon name (const char* or NULL).<br>**label:** Submenu title (const char*). |
| `void` | `gfx_menu_move(Evas_Object *object, Evas_Coord x, Evas_Coord y)` | Moves menu to specified pixel coordinates on screen. | **object:** Menu object (Evas_Object*).<br>**x, y:** Target screen pixel coordinates (Evas_Coord). |
| `void` | `gfx_menu_close(Evas_Object *object)` | Closes and hides open menu. | **object:** Menu object (Evas_Object*). |
| `Elm_Object_Item *` | `gfx_menu_get_selected(const Evas_Object *object)` | Returns currently selected active item in menu. | **object:** Menu object (const Evas_Object*). |
| `const Eina_List *` | `gfx_menu_get_items(const Evas_Object *object)` | Returns linked list of all root-level items in menu. | **object:** Menu object (const Evas_Object*). |
| `Evas_Object *` | `gfx_menu_get_itemobject(const Elm_Object_Item *item)` | Returns underlying Evas_Object graphics object of a menu item. | **item:** Menu item pointer (const Elm_Object_Item*). |
| `void` | `gfx_menu_set_itemselected(Elm_Object_Item *item, Eina_Bool selected)` | Sets highlighted/selected state of menu item. | **item:** Menu item (Elm_Object_Item*).<br>**selected:** Selection state (EINA_TRUE or EINA_FALSE). |
| `Eina_Bool` | `gfx_menu_get_itemdisabled(const Elm_Object_Item *item)` | Queries whether menu item is disabled. | **item:** Menu item (const Elm_Object_Item*). |
| `void` | `gfx_menu_set_itemicon(Elm_Object_Item *item, const char *icon)` | Changes icon graphic displayed on left of menu item. | **item:** Menu item (Elm_Object_Item*).<br>**icon:** Icon name or file path (const char* or NULL to remove). |
| `const char *` | `gfx_menu_get_itemicon(const Elm_Object_Item *item)` | Returns icon name of menu item. | **item:** Menu item (const Elm_Object_Item*). |
| `void` | `gfx_menu_set_itemlabel(Elm_Object_Item *item, const char *label)` | Updates text label of menu item. | **item:** Menu item (Elm_Object_Item*).<br>**label:** New text (const char* or NULL). |
| `const char *` | `gfx_menu_get_itemlabel(const Elm_Object_Item *item)` | Returns text label of menu item. | **item:** Menu item (const Elm_Object_Item*). |
| `Eina_Bool` | `gfx_menu_get_itemselected(const Elm_Object_Item *item)` | Checks whether menu item is selected. | **item:** Menu item (const Elm_Object_Item*). |
| `Elm_Object_Item *` | `gfx_menu_get_itemparent(const Elm_Object_Item *item)` | Returns parent menu item of a submenu item. | **item:** Menu item (const Elm_Object_Item*). |
| `const Eina_List *` | `gfx_menu_get_subitems(const Elm_Object_Item *item)` | Returns list of all sub-items under a menu item. | **item:** Menu item (const Elm_Object_Item*). |
| `void` | `gfx_menu_del_item(Elm_Object_Item *item)` | Removes specified item from menu and frees memory. | **item:** Menu item to delete (Elm_Object_Item*). |

---

## 6. Evas Canvas and Graphics Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `Evas *` | `gfx_object_get_evas(const Evas_Object *object)` | Returns pointer to main Evas drawing canvas of object. | **object:** Graphic object (const Evas_Object*). |
| `void` | `gfx_object_show(Evas_Object *object)` | Makes graphic object visible and enables rendering on canvas. | **object:** Object to show (Evas_Object*). |
| `void` | `gfx_object_hide(Evas_Object *object)` | Hides graphic object (stops rendering). | **object:** Object to hide (Evas_Object*). |
| `void` | `gfx_object_del(Evas_Object *object)` | Removes object from canvas and frees memory resources. | **object:** Object to delete (Evas_Object*). |
| `void` | `gfx_object_raise(Evas_Object *object)` | Raises object layer hierarchy (Z-order) to top level. | **object:** Object to raise (Evas_Object*). |
| `void` | `gfx_object_lower(Evas_Object *object)` | Lowers object layer hierarchy to back/bottom level. | **object:** Object to lower (Evas_Object*). |
| `void` | `gfx_object_set_size_hintweight(Evas_Object *object, double x, double y)` | Defines extra space expansion weight inside container layouts. | **object:** Target object (Evas_Object*).<br>**x, y:** Expansion weight (0.0 fixed size, 1.0 full expansion or EVAS_HINT_EXPAND). |
| `void` | `gfx_object_set_size_hintalign(Evas_Object *object, double x, double y)` | Defines alignment and fill behavior hint inside container cell. | **object:** Target object (Evas_Object*).<br>**x, y:** Alignment ratio (0.0 left/top, 0.5 center, 1.0 right/bottom, -1.0 or EVAS_HINT_FILL). |
| `void` | `gfx_object_move(Evas_Object *object, Evas_Coord x, Evas_Coord y)` | Moves object to absolute pixel coordinates on canvas. | **object:** Object to move (Evas_Object*).<br>**x, y:** Canvas coordinates (Evas_Coord). |
| `void` | `gfx_object_resize(Evas_Object *object, Evas_Coord w, Evas_Coord h)` | Sets pixel width and height dimensions of object. | **object:** Object to resize (Evas_Object*).<br>**w, h:** Width and height (Evas_Coord, 0 or greater). |
| `void` | `gfx_object_get_geometry(Evas_Object *object, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)` | Reads absolute position coordinates and pixel dimensions at once. | **object:** Target object (Evas_Object*).<br>**x, y, w, h:** Pointers to receive coordinates and size (Evas_Coord* or NULL). |
| `void` | `gfx_object_set_color(Evas_Object *object, int r, int g, int b, int a)` | Sets premultiplied RGBA color and alpha transparency. | **object:** Object to color (Evas_Object*).<br>**r, g, b, a:** Color and alpha components (integers 0 to 255; r, g, b must be less than or equal to a). |
| `void` | `gfx_object_get_color(const Evas_Object *object, int *r, int *g, int *b, int *a)` | Reads current RGBA color and alpha values of object. | **object:** Object to inspect (const Evas_Object*).<br>**r, g, b, a:** Integer pointers to receive values (int* or NULL). |
| `void` | `gfx_object_set_minsize(Evas_Object *object, Evas_Coord w, Evas_Coord h)` | Hints layout engine that object must maintain at least these pixel dimensions. | **object:** Target object (Evas_Object*).<br>**w, h:** Minimum dimensions (Evas_Coord, 0 or greater). |
| `void` | `gfx_object_set_maxsize(Evas_Object *object, Evas_Coord w, Evas_Coord h)` | Hints layout engine that object should not exceed these pixel dimensions. | **object:** Target object (Evas_Object*).<br>**w, h:** Maximum dimensions (Evas_Coord, 0 or greater, or -1 for unlimited). |
| `Evas_Object *` | `gfx_object_add_rectangle(Evas *canvas)` | Creates basic colored rectangle primitive shape on canvas. | **canvas:** Canvas pointer (valid Evas*). |
| `Evas_Object *` | `gfx_object_add_rawimage(Evas *canvas)` | Allocates raw image object directly at Evas level. | **canvas:** Canvas pointer (valid Evas*). |
| `Evas_Object *` | `gfx_object_add_text(Evas *canvas)` | Creates single-line plain text object on canvas. | **canvas:** Canvas pointer (valid Evas*). |
| `Evas_Object *` | `gfx_object_add_textblock(Evas *canvas)` | Creates rich-text formatted multi-line textblock object. | **canvas:** Canvas pointer (valid Evas*). |
| `void` | `gfx_object_set_imagefile(Evas_Object *object, const char *file, const char *key)` | Binds graphic file to Evas raw image object by path and key. | **object:** Evas image object (Evas_Object*).<br>**file:** File path string.<br>**key:** File sub-key/group (const char* or NULL). |
| `void` | `gfx_object_set_imagefilled(Evas_Object *object, Eina_Bool filled)` | Enables automatic stretching/filling of image to object bounds. | **object:** Evas image object (Evas_Object*).<br>**filled:** Auto-fill flag (EINA_TRUE enabled, EINA_FALSE disabled). |
| `void` | `gfx_object_set_textfont(Evas_Object *object, const char *font, Evas_Font_Size size)` | Sets font family and point size for Evas text object. | **object:** Text object (Evas_Object*).<br>**font:** Font family name (e.g., "Sans", "Arial").<br>**size:** Font point size (greater than 0). |
| `void` | `gfx_object_set_rawtext(Evas_Object *object, const char *text)` | Sets raw string displayed by Evas text object. | **object:** Text object (Evas_Object*).<br>**text:** Text string (const char* or NULL). |
| `void` | `gfx_object_add_eventcallback(Evas_Object *object, Evas_Callback_Type type, Evas_Event_Cb func, const void *data)` | Attaches listener for low-level Evas input events (mouse click, move, key press). | **object:** Target object (Evas_Object*).<br>**type:** Event type (EVAS_CALLBACK_MOUSE_DOWN, MOUSE_UP, KEY_DOWN, etc.).<br>**func:** Event callback function.<br>**data:** User data pointer (const void* or NULL). |
| `void` | `gfx_object_add_smartcallback(Evas_Object *object, const char *event, Evas_Smart_Cb func, const void *data)` | Attaches listener for high-level widget smart events (e.g., "clicked", "changed"). | **object:** Target widget object (Evas_Object*).<br>**event:** Smart signal name (e.g., "clicked", "selected", "changed").<br>**func:** Callback function.<br>**data:** User data pointer (const void* or NULL). |
| `void` | `gfx_object_set_focus(Evas_Object *object, Eina_Bool focus)` | Grants keyboard focus to object or removes focus. | **object:** Target object (Evas_Object*).<br>**focus:** Focus flag (EINA_TRUE focuses, EINA_FALSE unfocuses). |
| `void` | `gfx_object_set_clip(Evas_Object *object, Evas_Object *clip)` | Clips visibility and alpha bounds of object using another masking object. | **object:** Object to clip (Evas_Object*).<br>**clip:** Masking object (Evas_Object*). |
| `void` | `gfx_object_unset_clip(Evas_Object *object)` | Removes clipping mask from object, restoring original boundaries. | **object:** Object to unclip (Evas_Object*). |

---

## 7. Ecore System and Event Loop Functions

| Return Type | Function Prototype | Description | Parameters and Valid Values |
| :--- | :--- | :--- | :--- |
| `int` | `gfx_ecore_init(void)` | Initializes Ecore event loop and timer modules (returns reference count). | *Takes no parameters.* |
| `int` | `gfx_ecore_shutdown(void)` | Shuts down Ecore module and cleans up system resources. | *Takes no parameters.* |
| `void` | `gfx_start_mainloop(void)` | Starts main Ecore event loop to process events. | *Takes no parameters.* |
| `void` | `gfx_quit_mainloop(void)` | Stops main Ecore loop and returns control flow. | *Takes no parameters.* |
| `double` | `gfx_get_looptime(void)` | Returns current iteration start timestamp of main loop in seconds. | *Takes no parameters.* |
| `Ecore_Timer *` | `gfx_add_timer(double in, Ecore_Task_Cb func, const void *data)` | Registers timer triggered periodically at specified second interval. | **in:** Trigger interval in seconds (double, greater than 0.0).<br>**func:** Task function to invoke.<br>**data:** User data passed to task (const void* or NULL). |
| `void *` | `gfx_del_timer(Ecore_Timer *timer)` | Cancels running timer and returns associated user data. | **timer:** Timer object to delete (valid Ecore_Timer*). |
| `void` | `gfx_timer_set_interval(Ecore_Timer *timer, double in)` | Updates period interval of an existing timer. | **timer:** Timer object (Ecore_Timer*).<br>**in:** New interval in seconds (double, greater than 0.0). |
| `Ecore_Idler *` | `gfx_add_idler(Ecore_Task_Cb func, const void *data)` | Registers task to run when main event loop is idle. | **func:** Idle task function.<br>**data:** User data pointer (const void* or NULL). |
| `void *` | `gfx_del_idler(Ecore_Idler *idler)` | Deletes registered idler task and returns user data. | **idler:** Idler task object to delete (Ecore_Idler*). |
| `Ecore_Poller *` | `gfx_add_poller(Ecore_Poller_Type type, int interval, Ecore_Task_Cb func, const void *data)` | Registers poller to poll system state at tick frequencies. | **type:** Poller type (ECORE_POLLER_CORE, etc.).<br>**interval:** Tick frequency (power of 2: 1, 2, 4, 8; integer 1 or greater).<br>**func:** Function to invoke.<br>**data:** User data pointer (const void* or NULL). |
| `void *` | `gfx_del_poller(Ecore_Poller *poller)` | Removes registered poller object and returns user data. | **poller:** Poller object to delete (Ecore_Poller*). |
| `Ecore_Thread *` | `gfx_run_thread(Ecore_Thread_Cb func_heavy, Ecore_Thread_Cb func_end, Ecore_Thread_Cb func_cancel, const void *data)` | Offloads heavy computation to background thread to prevent UI freezing. | **func_heavy:** Heavy worker task function.<br>**func_end:** Completion function called on main thread (or NULL).<br>**func_cancel:** Cancellation function (or NULL).<br>**data:** Data pointer passed to thread (const void* or NULL). |
| `Ecore_Thread *` | `gfx_thread_run_feedback(Ecore_Thread_Heavy_Cb func_heavy, Ecore_Thread_Notify_Cb func_notify, Ecore_Thread_Cb func_end, Ecore_Thread_Cb func_cancel, const void *data, Eina_Bool try_no_queue)` | Launches background worker thread that can send progress notifications back to main thread. | **func_heavy:** Heavy task function.<br>**func_notify:** Feedback notification function (or NULL).<br>**func_end:** Completion function (or NULL).<br>**func_cancel:** Cancellation function (or NULL).<br>**data:** Shared data pointer.<br>**try_no_queue:** Immediate execution flag without queuing (EINA_TRUE or EINA_FALSE). |
| `Ecore_Exe *` | `gfx_execute_run(const char *exe_cmd, const void *data)` | Executes external program or shell command at system level. | **exe_cmd:** Command string to execute.<br>**data:** Data pointer bound to process (const void* or NULL). |
| `int` | `gfx_execute_terminate(Ecore_Exe *exe)` | Sends graceful termination signal (SIGTERM) to external process. | **exe:** Process object (valid Ecore_Exe*). |
| `int` | `gfx_execute_kill(Ecore_Exe *exe)` | Forcefully kills external process immediately using SIGKILL signal. | **exe:** Process object (valid Ecore_Exe*). |
| `Ecore_Fd_Handler *` | `gfx_add_fdhandler(int fd, Ecore_Fd_Handler_Flags flags, Ecore_Fd_Cb func, const void *data, Ecore_Fd_Cb buf_func, const void *buf_data)` | Listens to file descriptor (socket, file, pipe) for I/O events in main loop. | **fd:** File descriptor integer (0 or greater).<br>**flags:** Monitoring flags (ECORE_FD_READ, WRITE, ERROR, etc.).<br>**func:** I/O event callback function.<br>**data, buf_func, buf_data:** Additional callbacks and user data pointers (or NULL). |
| `Ecore_Event_Handler *` | `gfx_add_eventhandler(int type, Ecore_Event_Cb func, const void *data)` | Registers handler to catch system or custom Ecore event types. | **type:** Event type ID (integer greater than 0 generated by ecore_event_type_new()).<br>**func:** Handler function called when event triggers.<br>**data:** User data pointer (const void* or NULL). |
