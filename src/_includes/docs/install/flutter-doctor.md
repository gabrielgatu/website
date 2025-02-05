## Check your development setup

{% include docs/help-link.md location='win-doctor' %}

{% assign devos = include.devos %}
{% assign target = include.target %}
{% assign compiler = include.compiler %}

{% case devos %}
{% when 'Windows' -%}
   {% assign terminal='PowerShell' %}
   {% assign prompt='C:\>' %}
{% when "macOS" -%}
   {% assign terminal='your Terminal' %}
   {% assign prompt='$' %}
{% else -%}
   {% assign terminal='a shell' %}
   {% assign prompt='$' %}
{% endcase -%}
{% case target %}
{% when 'macOS','Windows','Linux' %}
{% assign work-target = target | append: ' desktop' %}
{% when 'desktop' %}
{% assign work-target = devos | append: ' desktop' %}
{% else %}
{% assign work-target = target | append: ' on ' | append: devos %}
{% endcase %}

### Run Flutter doctor

The `flutter doctor` command validates that all components of a
complete Flutter development environment for {{devos}}.

1. Open {{terminal}}.

1. To verify your installation of all the components,
   run the following command.

   ```terminal
   {{prompt}} flutter doctor
   ```

As you chose to develop for {{target}},
you do not need _all_ components.
If you followed this guide, the result of your command should resemble:

{% include docs/install/flutter-doctor-success.md config=include.config -%}

### Troubleshoot Flutter doctor issues

When the `flutter doctor` command returns an error, it could be for Flutter,
VS Code, {{compiler}}, the connected device, or network resources.

If the `flutter doctor` command returns an error for any of these components,
run it again with the verbose flag.

```terminal
{{prompt}} flutter doctor -v
```

Check the output for other software you might need to install
or further tasks to perform.

If you change the configuration of your Flutter SDK or its related components,
run `flutter doctor` again to verify the installation.

## Start developing {{work-target}} apps on Flutter

Congratulations!
Now that you have installed all prerequisites and the Flutter SDK,
you should be able to start developing Flutter apps for {{work-target}}.
