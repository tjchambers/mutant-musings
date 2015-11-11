# Destroy EVERYTHING!

Unleash mutant on your Rails code and eventually it will find it's way to innocuous changes like the example the follows:

## Example

```
  def remove_existing_themes_for_themeset(themeset)
-  point_themes.where(theme_id: themeset.themes).destroy_all
+  point_themes.destroy_all
 end
-----------------------
  def remove_existing_themes_for_themeset(themeset)
-  point_themes.where(theme_id: themeset.themes).destroy_all
+  point_themes.where({}).destroy_all
 end
-----------------------
  def remove_existing_themes_for_themeset(themeset)
-  point_themes.where(theme_id: themeset.themes).destroy_all
+  point_themes.where(nil).destroy_all
 end
-----------------------
 def remove_existing_themes_for_themeset(themeset)
-  point_themes.where(theme_id: themeset.themes).destroy_all
+  point_themes.where(theme_id: self.themes).destroy_all
 end
```

## Remedy/Action

Wow - did that play havoc. Besides being sloooww. Make sure that you test for not only the HAPPY path, the one where everything you wanted destroyed got destroyed, but include tests to ensure that data that should NOT get destroyed is retained.

NB: the last substitution example shows the calling parameter being swapped for `self`. This ran validly because this particular class also itself had an association `themes` which allowed for `self.themes` to be valid.

## Takeaway

- Mutant will significantly alter the ActiveRecord method chains and hashes, even though it knows nothing in particular about Rails or ActiveRecord.
- Always test for data remaining the same, as well as for data being changed as desired.