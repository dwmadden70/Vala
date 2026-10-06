# Meson.build - How To

## Multiple executable

---

Simply call executable() multiple times. Each call is an independent target:

```
project('MyApp', 'vala', 'c')

gtk4 = dependency('gtk4')

executable('application',
  'source/application.vala',
  dependencies : [gtk4]
)

executable('utility',
  'source/utility.vala',
  dependencies : [gtk4]
)
```

## Common sources

---

If both executables use the same files, extract them into a static library to avoid recompiling:

```cpp
project('MyApp', 'vala', 'c')

gtk4 = dependency('gtk4')

common = static_library('common', 'source/shared.vala',
  dependencies : [gtk4]
)

executable('application', 'source/application.vala',
  dependencies : [gtk4],
  link_with : common
)

executable('utility', 'source/utility.vala',
  dependencies : [gtk4],
  link_with : common
)
```

## Looping

---

Use <code style="color: orange;">foreach</code> when you have many executables that differ only by name/sources:

```cpp
progs = {
  'app1' : 'source/app1.vala',
  'app2' : 'source/app2.vala',
  'app3' : 'source/app3.vala',
}

foreach name, src : progs
  executable(name, src, dependencies : [gtk4])
endforeach
```

> All executables land in the build root (or in a `build_subdir` if you set one) and can be run directly from there.

---

## Further reading

* [Meson for Vala](https://mesonbuild.com/Vala.html)
