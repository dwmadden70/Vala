# How to build from CLI with valac

valac -X -w -X '-DGETTEXT_PACKAGE="io.github.dwmadden70.Vala"' --pkg=gtk4 src/application.vala

# How to guide translators

/// TRANSLATORS: The first %s is search term, the second is the name of default browser
title = _("Search for %s in %s").printf (query, get_default_browser_name ());
