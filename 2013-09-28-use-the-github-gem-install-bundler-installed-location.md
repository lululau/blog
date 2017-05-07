```sh
echo $(gem environ | sed -n '/GEM PATHS/{n;s#.*- ##;p;}')/bundler/gems
```
