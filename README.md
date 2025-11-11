https://github.com/zensical/zensical/issues/39

* `uvx zensical serve`
* http://localhost:8000

```toml
nav = [
    {"Symlink to internal dir" = "link-internal-dir/internal.md"}, # works
    {"Symlink to external dir" = "link-external-dir/external.md"}, # broken
    {"Symlink to internal file" = "link-internal-file.md"}, # broken
    {"Symlink to external file" = "link-external-file.md"}, # broken
    {"Directly use external file" = "../external/external.md"}, # broken
    {"Directly use internal file" = "internal/internal.md"}, # works
]
```

```
docs
├── index.md
├── internal
│   └── internal.md
├── link-external-dir -> ../external
├── link-external-file.md -> ../external/external.md
├── link-internal-dir -> ./internal
└── link-internal-file.md -> ./internal/internal.md
external
└── external.md
```