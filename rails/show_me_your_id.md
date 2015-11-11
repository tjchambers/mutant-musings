# Show me your ID

ActiveRecord can be very helpful in filling in id numbers to connect your associated models. And I found lots of places where specifying the #id method was unnecessary.

## Example

```
def pre_process(rec, _)
   if rec.assessment_id.blank?
-    rec.assessment_id = @importer.topmost_aa.id
+    rec.assessment_id = @importer.topmost_aa
   end
 end

```

## Remedy/Action

Just don't do it! Leave out the code and you'll be just fine. That is assuming of course that you have a validation constraint in your model, integrity constraint in the database, or you happen to have put a direct expectation on the field in question in your specs.

## Takeaway

- Less code to maintain is less code to fail
