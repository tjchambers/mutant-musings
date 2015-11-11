# De fault of the Find_by

If you use ActiveRecord at all you are quite familiar with find_by. In the exmaple that follows I used a find_by on an ActiveRecord association. By default those associations do some filtering. Unfortunately the filtering left me finding the *same* first record I would have found without the filter I added. So when mutated the results were indistinguishable. And indistinguishable is not a good testing outcome.


## Example

```
def summary_analytic(aa)
-  subclass_analytics.find_by(assessment: aa)
+  subclass_analytics.find_by(nil)
 end
-----------------------
def summary_analytic(aa)
-  subclass_analytics.find_by(assessment: aa)
+  subclass_analytics.find_by({})
 end
```

## Remedy/Action

Make certain that your tests use data that REQUIRES the application of all filters, and that the data that would result without the filter is NOT the same as with it. This is a basic testing practice, but when mutating code this means the difference between an alive mutation and a killed one.


## Takeaway

- Watch you data specifications for avoiding common data by default.
- Ensure your ActiveRecord where and find_by hashes have data that would be excluded, and .where.not have data that would otherwise be included.