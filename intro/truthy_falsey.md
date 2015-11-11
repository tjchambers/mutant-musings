# Truthy or not Truthy is never the question!

You may have been taking advantage of falsiness of nil in Ruby. Don't recommend you do that with your specs.

## Takeaway

- Be explicit about whether you expect `nil` or `false`. Avoid `be_falsey`.
- Be explicit about the true values - use `be true` or `be_a(Foo)` - avoid `be_truthy`