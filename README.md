
# Autocomplete widget in django

An alternative to RadioSelect, where all values are populated but hidden as a `ul > li` list in html. The user can
type in a textbox, and when the text matches one of the labels of the choices, the list item are displayed.

This avoids ajax.


## Setup

    pip install autocomplete_widget

Include these static files in your `<head>`

    <link rel="stylesheet" href="{% static 'django-autocomplete-widget.css' %}"/>
    <script src="{% static 'django-autocomplete-widget.js' %}"></script>

Django 'INSTALLED_APPS'

    INSTALLED_APPS = (
        # ...
        'autocomplete_widget',
        # ...
    )

A form:

    class TestForm(forms.Form):
        value = forms.ChoiceField(
            choices=[(5, 'Vijf'), (6, 'Zes'), (7, 'Zeven'), (18, 'Achttien'), (14, 'Veertien')],
            widget=AutocompleteSelect
        )

## Result

![Example widget][example]

[example]: example.png "Example widget"
