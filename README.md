# android_vendor_neko-priv_keys

A cool template for signing Neko builds with `dev-keys`.

## Usage

1. Clone this repo to `vendor/neko-priv/keys` (on your synced ROM rootdir) and `cd` to it.
2. Edit both `subject` vars on `gen_keys` script to reflect your data [[ref]](https://learn.microsoft.com/en-us/previous-versions/windows/desktop/ldap/distinguished-names).
3. Run it:

```bash
$ ./gen_keys
```

It will generate the certificates (defined in the `.data/` folder) in `vendor/neko-priv/keys`, the actual keys used to generate the certificates in `~/.android-certs/`, and regenerate the makefiles as new entries are added.

Backup **AT ALL COSTS** your `~/.android-certs/` and `vendor/neko-priv/keys` folders **AND NEVER LEAK THOSE**. Losing these keys could prevent you from updating your Neko builds with the same keys, so formatting data would be required. Leakage of these keys can compromise the security and authenticity of your builds, requiring a new pair of keys to be generated.
