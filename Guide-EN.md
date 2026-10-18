# EFL Abstraction Layer (gfx) \- Complete Documentation

# 1\. General & Core Functions

* **`int gfx_init(int argc, char **argv)`**: Initializes the Elementary and Ecore libraries.  
* **`int gfx_run(void)`**: Starts the main application loop (`elm_run`).  
* **`int gfx_exit(void)`**: Triggers the Ecore main loop quit and Elementary exit.  
* **`int gfx_shutdown(void)`**: Cleans up and shuts down Elementary and Ecore resources.

# 2\. Window Functions

* **`Evas_Object *gfx_object_add_feature_window(const char *name, const char *title)`**: Creates a new standard feature window.  
* **`Evas_Object *gfx_object_add_standard_window(Evas_Object *parent, const char *name, Elm_Win_Type type)`**: Adds a standard window with the specified parent and type.  
* **`int gfx_window_set_title(Evas_Object *object, const char *title)`**: Sets the title of the window.  
* **`int gfx_window_set_autodel(Evas_Object *object, Eina_Bool autodel)`**: Sets whether the window automatically deletes itself when closed.  
* **`int gfx_window_set_center(Evas_Object *object, Eina_Bool h, Eina_Bool v)`**: Centers the window horizontally and/or vertically on the screen.  
* **`int gfx_window_set_minsize(Evas_Object *object, int w, int h)`**: Sets the minimum size base of the window.  
* **`int gfx_window_set_fullscreen(Evas_Object *object, Eina_Bool full)`**: Sets or unsets the window fullscreen mode.  
* **`int gfx_window_set_active(Evas_Object *object)`**: Activates the window (brings to front / focuses).  
* **`int gfx_window_set_iconified(Evas_Object *object, Eina_Bool iconified)`**: Iconifies (minimizes) or restores the window.  
* **`int gfx_window_set_sticky(Evas_Object *object, Eina_Bool sticky)`**: Makes the window sticky across all workspaces.  
* **`int gfx_window_proportion_scale(Evas_Object *object, Evas_Object *subobject)`**: Adds a resize subobject to the window.  
* **`void gfx_window_set_autohide(Evas_Object *object, Eina_Bool autohide)`**: Sets the window to auto-hide when the close button is clicked.

# 3\. Widget Addition Functions

* **`Evas_Object *gfx_object_add_button(Evas_Object *parent)`**: Adds a button widget.  
* **`Evas_Object *gfx_object_add_checkbutton(Evas_Object *parent)`**: Adds a check button widget.  
* **`Evas_Object *gfx_object_add_radiobutton(Evas_Object *parent)`**: Adds a radio button widget.  
* **`Evas_Object *gfx_object_add_entry(Evas_Object *parent)`**: Adds a text entry widget.  
* **`Evas_Object *gfx_object_add_slider(Evas_Object *parent)`**: Adds a slider widget.  
* **`Evas_Object *gfx_object_add_spinner(Evas_Object *parent)`**: Adds a spinner widget.  
* **`Evas_Object *gfx_object_add_combobox(Evas_Object *parent)`**: Adds a combobox widget.  
* **`Evas_Object *gfx_object_add_label(Evas_Object *parent)`**: Adds a text label widget.  
* **`Evas_Object *gfx_object_add_icon(Evas_Object *parent)`**: Adds an icon widget.  
* **`Evas_Object *gfx_object_add_image(Evas_Object *parent)`**: Adds an image widget.  
* **`Evas_Object *gfx_object_add_progressbar(Evas_Object *parent)`**: Adds a progress bar widget.  
* **`Evas_Object *gfx_object_add_bubble(Evas_Object *parent)`**: Adds a bubble widget.  
* **`Evas_Object *gfx_object_add_clock(Evas_Object *parent)`**: Adds a clock widget.  
* **`Evas_Object *gfx_object_add_calendar(Evas_Object *parent)`**: Adds a calendar widget.  
* **`Evas_Object *gfx_object_add_separator(Evas_Object *parent)`**: Adds a separator line widget.  
* **`Evas_Object *gfx_object_add_popup(Evas_Object *parent)`**: Adds a popup widget.

# 4\. Box Functions

* **`Evas_Object *gfx_object_add_box(Evas_Object *parent)`**: Creates a box layout container.  
* **`void gfx_box_set_horizontal(Evas_Object *object, Eina_Bool horizontal)`**: Sets box orientation (horizontal or vertical).  
* **`Eina_Bool gfx_box_get_horizontal(const Evas_Object *object)`**: Returns whether the box is horizontal.  
* **`void gfx_box_pack_start(Evas_Object *object, Evas_Object *child)`**: Packs an element at the start of the box.  
* **`void gfx_box_pack_end(Evas_Object *object, Evas_Object *child)`**: Packs an element at the end of the box.  
* **`void gfx_box_pack_before(Evas_Object *object, Evas_Object *child, Evas_Object *before)`**: Packs an element before another specified element in the box.  
* **`void gfx_box_pack_after(Evas_Object *object, Evas_Object *child, Evas_Object *after)`**: Packs an element after another specified element in the box.  
* **`void gfx_box_unpack(Evas_Object *object, Evas_Object *child)`**: Unpacks an element from the box.  
* **`void gfx_box_unpack_all(Evas_Object *object)`**: Unpacks all elements from the box.  
* **`void gfx_box_set_homogeneous(Evas_Object *object, Eina_Bool homogeneous)`**: Sets whether all box elements are homogeneously sized.  
* **`Eina_Bool gfx_box_get_homogeneous(Evas_Object *object)`**: Returns whether the box is homogeneous.  
* **`void gfx_box_set_padding(Evas_Object *object, Evas_Coord horizontal, Evas_Coord vertical)`**: Sets horizontal and vertical padding between box items.  
* **`void gfx_box_get_padding(Evas_Object *object, Evas_Coord *horizontal, Evas_Coord *vertical)`**: Gets horizontal and vertical padding of the box.  
* **`void gfx_box_set_align(Evas_Object *object, double horizontal, double vertical)`**: Sets the alignment of box contents.  
* **`void gfx_box_get_align(Evas_Object *object, double *horizontal, double *vertical)`**: Gets the alignment values of box contents.  
* **`Eina_List *gfx_box_get_children(const Evas_Object *object)`**: Returns a list of all child objects in the box.

# 5\. Grid Functions

* **`Evas_Object *gfx_object_add_grid(Evas_Object *parent)`**: Creates a grid layout container.  
* **`void gfx_grid_set_size(Evas_Object *object, int w, int h)`**: Sets the virtual width and height size of the grid.  
* **`void gfx_grid_get_size(const Evas_Object *object, int *w, int *h)`**: Gets the virtual size of the grid.  
* **`void gfx_grid_add_pack(Evas_Object *object, Evas_Object *subobject, int x, int y, int w, int h)`**: Packs a subobject into the grid at specified virtual coordinates and size.  
* **`void gfx_grid_unpack(Evas_Object *object, Evas_Object *subobject)`**: Unpacks a subobject from the grid.  
* **`void gfx_grid_set_pack(Evas_Object *subobject, Evas_Coord x, Evas_Coord y, Evas_Coord w, Evas_Coord h)`**: Updates grid position and size parameters for a packed subobject.  
* **`void gfx_grid_get_pack(Evas_Object *subobject, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)`**: Retrieves grid positioning and size parameters for a packed subobject.  
* **`Eina_List *gfx_grid_get_children(const Evas_Object *object)`**: Returns a list of all child objects in the grid.  
* **`void gfx_grid_clear(Evas_Object *object, Eina_Bool clear)`**: Clears all objects from the grid.

# 6\. Table Functions

* **`Evas_Object *gfx_object_add_table(Evas_Object *parent)`**: Creates a table layout container.  
* **`void gfx_table_set_align(Evas_Object *object, double horizontal, double vertical)`**: Sets alignment for table contents.  
* **`void gfx_table_get_align(const Evas_Object *object, double *horizontal, double *vertical)`**: Gets alignment values for table contents.  
* **`Evas_Object *gfx_table_get_child(const Evas_Object *object, int col, int row)`**: Retrieves the child object at specified column and row.  
* **`void gfx_table_clear(Evas_Object *object, Eina_Bool clear)`**: Clears all objects from the table.  
* **`void gfx_table_set_homogeneous(Evas_Object *object, Eina_Bool homogeneous)`**: Sets whether table cells are homogeneously sized.  
* **`Eina_Bool gfx_table_get_homogeneous(const Evas_Object *object)`**: Returns whether table cells are homogeneous.  
* **`void gfx_table_pack(Evas_Object *object, Evas_Object *subobject, int col, int row, int colspan, int rowspan)`**: Packs a subobject into table cells with specified column, row, and spans.  
* **`void gfx_table_set_pack(Evas_Object *subobject, int col, int row, int colspan, int rowspan)`**: Updates cell placement and spans for a packed table subobject.  
* **`void gfx_table_get_pack(Evas_Object *subobject, int *col, int *row, int *colspan, int *rowspan)`**: Retrieves cell placement and span parameters for a table subobject.  
* **`void gfx_table_set_padding(Evas_Object *object, Evas_Coord horizontal, Evas_Coord vertical)`**: Sets padding between table cells.  
* **`void gfx_table_get_padding(Evas_Object *object, Evas_Coord *horizontal, Evas_Coord *vertical)`**: Gets padding between table cells.  
* **`void gfx_table_unpack(Evas_Object *object, Evas_Object *subobject)`**: Unpacks a subobject from the table.

# 7\. Scroller Functions

* **`Evas_Object *gfx_object_add_scroller(Evas_Object *parent)`**: Creates a scroller container.  
* **`void gfx_scroller_set_policy(Evas_Object *object, Elm_Scroller_Policy policy_h, Elm_Scroller_Policy policy_v)`**: Sets horizontal and vertical scrollbar visibility policies.  
* **`void gfx_scroller_get_policy(const Evas_Object *object, Elm_Scroller_Policy *policy_h, Elm_Scroller_Policy *policy_v)`**: Gets horizontal and vertical scrollbar visibility policies.  
* **`void gfx_scroller_set_region(Evas_Object *object, Evas_Coord x, Evas_Coord y, Evas_Coord w, Evas_Coord h)`**: Sets the visible region coordinates and dimension within the scroller.  
* **`void gfx_scroller_get_region(const Evas_Object *object, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)`**: Gets visible region coordinates and dimensions from the scroller.  
* **`void gfx_scroller_get_position(const Evas_Object *object, Evas_Coord *x, Evas_Coord *y)`**: Gets current scroll position coordinates.  
* **`void gfx_scroller_set_pagesize(Evas_Object *object, Evas_Coord w, Evas_Coord h)`**: Sets page size for page-based scrolling.  
* **`void gfx_scroller_get_pagesize(const Evas_Object *object, Evas_Coord *w, Evas_Coord *h)`**: Gets page size dimensions.  
* **`void gfx_scroller_get_currentpage(const Evas_Object *object, int *hp, int *vp)`**: Gets current active horizontal and vertical page indices.  
* **`void gfx_scroller_show_page(Evas_Object *object, int hp, int vp)`**: Scrolls to specified horizontal and vertical page indices.  
* **`void gfx_scroller_set_bounce(Evas_Object *object, Eina_Bool h_bounce, Eina_Bool v_bounce)`**: Enables or disables bouncing effect at scroll boundaries.  
* **`void gfx_scroller_get_bounce(const Evas_Object *object, Eina_Bool *h_bounce, Eina_Bool *v_bounce)`**: Gets bouncing effect status.

# 8\. Frame Functions

* **`Evas_Object *gfx_object_add_frame(Evas_Object *parent)`**: Creates a framed container.  
* **`void gfx_frame_set_autocollapse(Evas_Object *object, Eina_Bool autocollapse)`**: Sets auto-collapse feature on frame.  
* **`Eina_Bool gfx_frame_get_autocollapse(const Evas_Object *object)`**: Returns whether auto-collapse is enabled.  
* **`void gfx_frame_set_collapse(Evas_Object *object, Eina_Bool collapse)`**: Collapses or expands the frame.  
* **`Eina_Bool gfx_frame_get_collapse(const Evas_Object *object)`**: Returns whether the frame is collapsed.

# 9\. Object Management Functions

* **`void gfx_object_set_text(Evas_Object *object, const char *text)`**: Sets text content of the object.  
* **`const char *gfx_object_get_text(const Evas_Object *object)`**: Returns text content of the object.  
* **`void gfx_object_set_content(Evas_Object *object, Evas_Object *content)`**: Sets content subobject inside the parent object.  
* **`Evas_Object *gfx_object_get_content(const Evas_Object *object)`**: Returns content subobject.  
* **`Eina_Bool gfx_image_set_file(Evas_Object *object, const char *file, const char *group)`**: Sets image file path and optional group key for an image object.  
* **`Eina_Bool gfx_icon_set_standard(Evas_Object *object, const char *name)`**: Sets standard system icon name for an icon object.  
* **`void gfx_object_set_parttext(Evas_Object *object, const char *part, const char *text)`**: Sets text for a specific named part of the object.  
* **`void gfx_object_set_partcontent(Evas_Object *object, const char *part, Evas_Object *content)`**: Sets content for a specific named part of the object.  
* **`Eina_Bool gfx_set_policy(unsigned int policy, int value)`**: Sets global Elementary policy.  
* **`void gfx_object_set_disabled(Evas_Object *object, Eina_Bool disabled)`**: Disables or enables an object.

# 10\. Entry and State Functions

* **`void gfx_entry_set_text(Evas_Object *object, const char *text)`**: Sets text in entry widget.  
* **`const char *gfx_entry_get_text(const Evas_Object *object)`**: Gets text from entry widget.  
* **`void gfx_entry_set_singleline(Evas_Object *object, Eina_Bool single_line)`**: Sets entry widget to single-line or multi-line mode.  
* **`void gfx_entry_set_password(Evas_Object *object, Eina_Bool password)`**: Sets entry widget to password mode (masked text).  
* **`void gfx_check_set_state(Evas_Object *object, Eina_Bool checked)`**: Sets checked state of checkbox widget.  
* **`Eina_Bool gfx_check_get_state(const Evas_Object *object)`**: Returns checked state of checkbox widget.  
* **`void gfx_radio_set_statevalue(Evas_Object *object, int value)`**: Sets integer state value represented by radio button.  
* **`void gfx_radio_set_value(Evas_Object *object, int value)`**: Sets active value of radio button group.  
* **`int gfx_radio_get_value(const Evas_Object *object)`**: Gets current active value of radio button group.  
* **`void gfx_radio_add_group(Evas_Object *object, Evas_Object *group)`**: Adds radio button to specified radio group.  
* **`void gfx_slider_set_minmax(Evas_Object *object, double min, double max)`**: Sets minimum and maximum range values for slider widget.  
* **`void gfx_slider_set_unitformat(Evas_Object *object, const char *format)`**: Sets display unit format string for slider value.  
* **`void gfx_slider_set_value(Evas_Object *object, double value)`**: Sets current value of slider widget.  
* **`double gfx_slider_get_value(const Evas_Object *object)`**: Gets current value of slider widget.

# 11\. Genlist Functions

* **`Elm_Object_Item *gfx_genlist_add_item(Evas_Object *object, const Elm_Genlist_Item_Class *itemclass, const void *data, Elm_Object_Item *parent, Elm_Genlist_Item_Type flags, Evas_Smart_Cb function, const void *function_data)`**: Appends an item to genlist widget.  
* **`void gfx_genlist_clear(Evas_Object *object)`**: Clears all items from genlist widget.  
* **`Elm_Genlist_Item_Class *gfx_genlist_add_itemclass(void)`**: Allocates and returns new genlist item class.  
* **`void gfx_genlist_free_itemclass(Elm_Genlist_Item_Class *itemclass)`**: Frees allocated genlist item class.

# 12\. Background Functions

* **`Evas_Object *gfx_object_add_background(Evas_Object *parent)`**: Creates a background widget.  
* **`Eina_Bool gfx_background_set_file(Evas_Object *object, const char *file, const char *group)`**: Sets image file or Edje group for background widget.  
* **`void gfx_background_get_file(const Evas_Object *object, const char **file, const char **group)`**: Gets image file and group information from background widget.  
* **`void gfx_background_set_option(Evas_Object *object, Elm_Bg_Option option)`**: Sets display option (tiled, centered, scaled, etc.) for background widget.  
* **`Elm_Bg_Option gfx_background_get_option(const Evas_Object *object)`**: Gets display option setting of background widget.  
* **`void gfx_background_set_color(Evas_Object *object, int r, int g, int b)`**: Sets solid RGB color for background widget.  
* **`void gfx_background_get_color(const Evas_Object *object, int *r, int *g, int *b)`**: Gets solid RGB color values of background widget.  
* **`void gfx_background_set_loadsize(Evas_Object *object, int w, int h)`**: Sets load size limits for background image to save memory.

# 13\. Canvas and Basic Object Management

* **`Evas *gfx_object_get_evas(const Evas_Object *object)`**: Returns Evas canvas handle associated with object.  
* **`void gfx_object_show(Evas_Object *object)`**: Makes object visible on canvas.  
* **`void gfx_object_hide(Evas_Object *object)`**: Hides object on canvas.  
* **`void gfx_object_del(Evas_Object *object)`**: Deletes object from canvas and frees resources.  
* **`void gfx_object_raise(Evas_Object *object)`**: Raises object to top of layer stacking order.  
* **`void gfx_object_lower(Evas_Object *object)`**: Lowers object to bottom of layer stacking order.  
* **`void gfx_object_set_size_hintweight(Evas_Object *object, double x, double y)`**: Sets size hint weight expansion parameters.  
* **`void gfx_object_set_size_hintalign(Evas_Object *object, double x, double y)`**: Sets size hint alignment parameters.

# 14\. Geometry, Position and Color

* **`void gfx_object_move(Evas_Object *object, Evas_Coord x, Evas_Coord y)`**: Moves object to specified canvas coordinates.  
* **`void gfx_object_resize(Evas_Object *object, Evas_Coord w, Evas_Coord h)`**: Resizes object dimensions on canvas.  
* **`void gfx_object_get_geometry(Evas_Object *object, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)`**: Gets coordinates and dimension geometry of object.  
* **`void gfx_object_set_color(Evas_Object *object, int r, int g, int b, int a)`**: Sets RGBA color and premultiplied alpha values of object.  
* **`void gfx_object_get_color(const Evas_Object *object, int *r, int *g, int *b, int *a)`**: Gets RGBA color values of object.

# 15\. Object Creation / Factory

* **`Evas_Object *gfx_object_add_rectangle(Evas *canvas)`**: Creates a raw rectangle object on canvas.  
* **`Evas_Object *gfx_object_add_rawimage(Evas *canvas)`**: Creates a raw image object on canvas.  
* **`Evas_Object *gfx_object_add_text(Evas *canvas)`**: Creates a raw string text object on canvas.  
* **`Evas_Object *gfx_object_add_textblock(Evas *canvas)`**: Creates a formatted textblock object on canvas.

# 16\. Image Operations

* **`void gfx_object_set_imagefile(Evas_Object *object, const char *file, const char *key)`**: Sets file path and key for raw Evas image object.  
* **`void gfx_object_set_imagefilled(Evas_Object *object, Eina_Bool filled)`**: Sets whether raw image automatically fills object area.  
* **`void gfx_object_set_imagesize(Evas_Object *object, int w, int h)`**: Manually sets raw pixel buffer dimensions of image object.  
* **`void gfx_object_get_imagesize(Evas_Object *object, int *w, int *h)`**: Gets raw pixel buffer dimensions of image object.

# 17\. Text Operations

* **`Eina_Bool gfx_object_set_textfont(Evas_Object *object, const char *font, Evas_Font_Size size)`**: Sets font name and point size for raw Evas text object.  
* **`void gfx_object_set_rawtext(Evas_Object *object, const char *text)`**: Sets text string for raw Evas text object.  
* **`const char *gfx_object_get_rawtext(const Evas_Object *object)`**: Gets text string from raw Evas text object.  
* **`Eina_Bool gfx_object_set_textblockmarkup(Evas_Object *object, const char *text)`**: Sets markup/HTML formatted text on Evas textblock object.

# 18\. Events and Interaction

* **`void gfx_object_add_eventcallback(Evas_Object *object, Evas_Callback_Type type, Evas_Object_Event_Cb func, const void *data)`**: Registers Evas-level event callback (e.g., mouse down, move) on object.  
* **`void gfx_object_add_smartcallback(Evas_Object *object, const char *event, Evas_Smart_Cb func, const void *data)`**: Registers Elementary smart event callback (e.g., "clicked", "changed") on widget.  
* **`void gfx_object_set_focus(Evas_Object *object, Eina_Bool focus)`**: Sets or removes keyboard focus for object.

# 19\. Cropping / Masking

* **`void gfx_object_set_clip(Evas_Object *object, Evas_Object *clip)`**: Clips/masks object to geometry of clipper object.  
* **`void gfx_object_unset_clip(Evas_Object *object)`**: Removes clip/mask object binding.

# 20\. Ecore Initialization & Shutdown

* **`int gfx_ecore_init(void)`**: Initializes Ecore subsystem independently.  
* **`int gfx_ecore_shutdown(void)`**: Shuts down Ecore subsystem.

# 21\. Main Loop Functions

* **`void gfx_start_mainloop(void)`**: Begins Ecore main event loop.  
* **`void gfx_quit_mainloop(void)`**: Quits Ecore main event loop.  
* **`double gfx_get_looptime(void)`**: Returns current main loop timestamp in seconds.

# 22\. Timer Functions

* **`Ecore_Timer *gfx_add_timer(double in_seconds, Ecore_Task_Cb func, const void *data)`**: Adds a periodic timer executing at specified interval.  
* **`void gfx_del_timer(Ecore_Timer *timer)`**: Deletes and cancels timer.  
* **`void gfx_timer_set_interval(Ecore_Timer *timer, double in_seconds)`**: Updates timer execution interval.  
* **`double gfx_timer_get_interval(const Ecore_Timer *timer)`**: Returns timer execution interval in seconds.  
* **`void gfx_timer_delay(Ecore_Timer *timer, double add)`**: Delays next timer execution by specified seconds.  
* **`void gfx_timer_freeze(Ecore_Timer *timer)`**: Freezes/pauses timer.  
* **`void gfx_timer_thaw(Ecore_Timer *timer)`**: Thaws/resumes frozen timer.

# 23\. Idler Functions

* **`Ecore_Idler *gfx_add_idler(Ecore_Task_Cb func, const void *data)`**: Adds task callback executed when main loop is idle.  
* **`void *gfx_del_idler(Ecore_Idler *idler)`**: Deletes idle task callback.

# 24\. Poller Functions

* **`Ecore_Poller *gfx_add_poller(Ecore_Poller_Type type, int interval, Ecore_Task_Cb func, const void *data)`**: Adds poller executing at regular polling ticks.  
* **`void *gfx_del_poller(Ecore_Poller *poller)`**: Deletes poller task.

# 25\. Thread Functions

* **`Ecore_Thread *gfx_run_thread(Ecore_Thread_Cb func_blocking, Ecore_Thread_Cb func_end, Ecore_Thread_Cb func_cancel, const void *data)`**: Runs blocking task function in background thread.  
* **`Ecore_Thread *gfx_thread_run_feedback(Ecore_Thread_Cb func_heavy, Ecore_Thread_Notify_Cb func_notify, Ecore_Thread_Cb func_end, Ecore_Thread_Cb func_cancel, const void *data, Eina_Bool try_no_queue)`**: Runs background thread capable of sending progress notification callbacks to main thread.  
* **`Eina_Bool gfx_thread_cancel(Ecore_Thread *th)`**: Sends cancellation signal to running thread.  
* **`void gfx_thread_add_localdata(Ecore_Thread *th, const char *key, void *value, Eina_Free_Cb cb, Eina_Bool direct)`**: Binds thread-local key-value data.

# 26\. Process Execution Functions

* **`Ecore_Exe *gfx_execute_run(const char *exe_command, const void *data)`**: Spawns and executes external system command in background.  
* **`Ecore_Exe *gfx_execute_run_cb(const char *exe_command, Ecore_Exe_Cb func, const void *data)`**: Spawns external command with process communication callback.  
* **`void gfx_execute_terminate(Ecore_Exe *exe)`**: Sends SIGTERM signal to spawned process.  
* **`void gfx_execute_kill(Ecore_Exe *exe)`**: Sends SIGKILL signal to forcibly terminate spawned process.  
* **`pid_t gfx_execute_get_pid(const Ecore_Exe *exe)`**: Returns Process ID (PID) of spawned process.  
* **`void gfx_execute_free(Ecore_Exe *exe)`**: Frees process handle object.

# 27\. File Descriptor Handler Functions

* **`Ecore_Fd_Handler *gfx_add_fdhandler(int fd, Ecore_Fd_Handler_Flags flags, Ecore_Fd_Cb func, const void *data, Ecore_Fd_Cb bufd_func, const void *bufd_data)`**: Adds handler listening for read/write events on file descriptor (socket, pipe, etc.).  
* **`void *gfx_del_fdhandler(Ecore_Fd_Handler *fd_handler)`**: Deletes file descriptor handler.

# 28\. Event Handler Functions

* **`Ecore_Event_Handler *gfx_add_eventhandler(int type, Ecore_Event_Handler_Cb func, const void *data)`**: Adds handler listening for specific Ecore event type.
