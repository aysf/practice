# Sample 1

```rb
#!/usr/bin/env ruby
# frozen_string_literal: true

$DEBUG = (ARGV[0] == '-d')
numerator = rand(100)
denominator = rand(10)

def pdebug(str)
  warn "DEBUG: #{str}" if $DEBUG
end


puts numerator / denominator
pdebug "dividing #{numerator} by #{denominator}"
```

save as `devide.rb` and run `./devide.rb` from the terminal