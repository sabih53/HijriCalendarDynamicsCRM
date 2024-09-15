

# Hijri Date Picker for Dynamics CRM

A custom Hijri (Islamic) Date Picker control designed for Microsoft Dynamics CRM. This control allows users to select dates in the Hijri calendar and integrates seamlessly with Dynamics CRM forms via CRM Web Resources.

## Features

- **Hijri Calendar Integration**: Displays a fully functional Hijri calendar for selecting dates.
- **Bootstrap Powered UI**: Utilizes Bootstrap for a responsive and aesthetically pleasing design.
- **Moment.js**: Supports date manipulation and formatting through the powerful Moment.js library.
- **Customizable Date Format**: Offers flexibility in configuring date formats.
- **Clear and Today Buttons**: Provides options to clear the date field or quickly select today’s date.
- **CRM Integration**: Easily binds the selected date to CRM fields using `Xrm.Page` methods.

## Setup Instructions

### Prerequisites

1. Microsoft Dynamics CRM.
2. A valid CRM environment to upload web resources.
3. Basic understanding of Dynamics CRM customizations.

### Step 1: Clone or Download

Clone the repository or download the necessary files to your local machine.

```bash
git clone https://github.com/yourusername/hijri-date-picker.git
```

### Step 2: Upload Web Resources

1. Log into Dynamics CRM as a system administrator.
2. Navigate to **Settings** > **Customizations** > **Customize the System**.
3. Go to **Web Resources** and create a new Web Resource.
4. Upload the following files:
    - `DatePickerControl.html`: Main HTML file that renders the date picker.
    - `bootstrap-hijri-datetimepickermin.js`: JavaScript library for the Hijri Date Picker.
    - `moment.min.js`: Moment.js library for date formatting.
    - `jquery.min.js`: jQuery library for DOM manipulation.
    - `bootstrap.min.css`: Bootstrap CSS for styling.
    - `bootstrap-datetimepicker.min.css`: Hijri DatePicker CSS for styling.
    - **Note**: Ensure you upload the `ClientGlobalContext.js.aspx` from CRM to access form fields.

### Step 3: Embed the Web Resource

1. Open the form in CRM where you want to display the Hijri Date Picker.
2. Add the **Web Resource** (e.g., `DatePickerControl.html`) to the form.
3. Set appropriate dimensions (e.g., 300px width and 150px height).

### Step 4: Configure Field Binding

1. In `DatePickerControl.html`, update the following line to bind the selected date to your CRM field:
   ```javascript
   Xrm.Page.getAttribute("your_field_name").setValue(selectedDate);
   ```
   Replace `"your_field_name"` with the actual field schema name from CRM.

2. Ensure that you have included the reference to `ClientGlobalContext.js.aspx` in your HTML file:
   ```html
   <script type="text/javascript" src="../ClientGlobalContext.js.aspx"></script>
   ```

### Step 5: Save and Publish

Once the web resources and form changes are complete, save the form and publish the customizations.

## File Structure

- **DatePickerControl.html**: The main file that renders the Hijri Date Picker and handles interactions with CRM fields.
- **LoaderWait.html**: A utility file for loading animations.
- **bootstrap.min.css**: Bootstrap framework for styling.
- **bootstrap-datetimepicker.min.css**: Additional styles specific to the Hijri Date Picker.
- **jquery.min.js**: jQuery library for DOM manipulation.
- **moment.min.js**: Moment.js library for date parsing and manipulation.
- **bootstrap-hijri-datetimepickermin.js**: The Hijri Date Picker library that enables Hijri calendar functionality.

## Dependencies

The Hijri Date Picker requires the following libraries:

- **jQuery**: Used for DOM manipulation and event handling.
- **Bootstrap**: A popular CSS framework for responsive design.
- **Moment.js**: A powerful date manipulation library.
- **Hijri-DateTimePicker**: Extension of Bootstrap's DatePicker that supports Hijri calendar.

### Example Code

Here’s an example of how the Hijri Date Picker can be initialized in **DatePickerControl.html**:

```html
<script>
    $(function () {
        $('#hijri-date-input').hijriDatePicker({
            hijri: true,
            format: 'YYYY-MM-DD',
            showClear: true,
            showTodayButton: true
        });
    });
</script>
```

## Customization

You can customize the format of the date, add additional buttons, or modify the behavior by adjusting the following options in the script initialization:

- `format`: Controls the display format (e.g., `YYYY-MM-DD`).
- `showClear`: Enables a clear button to remove the selected date.
- `showTodayButton`: Enables a button to select today's date.

## Contributions

Contributions are welcome! Please submit pull requests for any features or bug fixes you’d like to add.

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.

