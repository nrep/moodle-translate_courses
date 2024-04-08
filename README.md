This is a Moodle plugin that is used to translate course from English to Kinyarwanda and vice versa. 

# To Install it manually #
- Unzip the plugin in the your Moodle project's /local directory.
- Install the compulsory Moodle theme:
https://github.com/Digital-Umuganda/moodle-theme 
- And also, install the required cutom field: https://github.com/Digital-Umuganda/moodle-courseselect 

# To Enable it #
- Go to "Site Administration >> Plugins &gt;&gt; Local plugins &gt;&gt; AI Course translations" and enable it in its settings

# To Use it #
In order to use this plugin, you have to first install and enable the plugin. If you don't know how to install or how to enable the plugin, the instructions can be found at the beginning of this page.

After enabling the plugin, you can set the course content language, and enable or disable widget/popup translations that typically pops up when a user selects text from the course content. You can also set the target language for the widget/popup translations.

Let's take a look at how we are going to do that.

## Set the course content language ##
You can set the course content language using **one** of the following ways:
1. Open a course
2. Navigate to the course settings
3. Set the course's language
<div align="center"><img src="images/Set course content language via settings.png" style="width: 80%" /></div>

## Enable or disable widget/popup translations ##
You can enable or disable widget/popup translations using **one** of the following ways:
1. First, enable it in the settings: Go to "Site Administration >> Appearance &gt;&gt; Boost custom translation" and check the box that says "Enable widget"
<div align="center"><img src="images/Enable or disable widget via settings.png" style="width: 80%" /></div>
2. After that, on every course, you will find a toggle to switch on/off the widget in the current course. That navigation bar can only be accessed when you are on a course page.
<div align="center"><img src="images/Enable or disable widget using the navigation bar.png" style="width: 80%" /></div>

## Set the target language for the widget/popup translations ##
You can enable or disable widget/popup translations using **one** of the following ways:
1. You can set this in settings
<div align="center"><img src="images/Set target widget language via settings.png" style="width: 80%" /></div>
2. Or you can set it by changing the target language using the widget/popup.
<div align="center"><img src="images/Set target widget language using the widget.png" style="width: 80%" /></div>

**N.B**: Users with the 'filter/translations:edittranslations' capability will see an icon in the top right hand corner of the screen to enable the translator view of the course. At this point all translatable text will have an icon injected next to it to allow it to be translated.

# To migrate from filter_fulltranslate #
A CLI tool is available to migrate all translations across from the filter_fulltranslate.

It is recommended that you clean out any unwanted translations that may have been generated as follows:
````
delete from mdl_filter_fulltranslate where sourcetext like '%{mlang%';
````

You can then copy the translations from filter_fulltranslate into filter_translations as follows:
````
php cli/migrate_filter_fulltranslate.php --confirm
````

# To add translation span tags to existing data #
A CLI tool is available to automatically add span tags to existing data. Please use with extreme caution.

You can run the tool as follows which will show help text:
````
php cli/insert_spans.php
````

Author
------

The module has been written and is currently maintained by Andrew Hancox but now it is being maintained by Elvis Peace NDAHAYO RUGERO on behalf of [Digital Umuganda](https://digitalumuganda.com).

Useful links
------------

* [Original documentation](https://docs.moodle.org/311/en/Content_translation_plugin_set)
* [Bug tracker](https://github.com/Digital-Umuganda/moodle-filter_translations/issues)

License
-------

This program is free software: you can redistribute it and/or modify it under the
terms of the GNU General Public License as published by the Free Software Foundation,
either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE.  See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this
program. If not, see <http://www.gnu.org/licenses/>.
