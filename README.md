# dbt_macros
The apply_meta_as_tags_modified macro is the modified version of the Montreal Analytics [apply_meta_as_tags](https://github.com/Montreal-Analytics/dbt-snowflake-utils/blob/0.5.0/macros/apply_meta_as_tags.sql) macro. Instead of creating the tags in each model's schema, this macro creates all tags in a separate database called `governance` and in a schema called `tags`. This can be changed in the macro based on your specific names:

```
--modified part, change names accordingly
{%- set tag_database = 'governance' -%}
{%- set tag_schema = 'tags' -%}
{%- set tag_schema_full = tag_database+'.'+tag_schema -%}
```
