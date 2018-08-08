A metapackage to enforce a lowest version on installed Symfony components
=========================================================================

This metapackage conflicts with lower versions of standalone Symfony packages.
This effectively means that it prevents Composer from installing lower versions you'd like to exclude.
It is expected to be used only in root packages, and *not* by library authors.
Open-source authors might still find it usefull to test several versions of Symfony components in their C.I.

Usage
-----

Use the Composer command line:

```bash
composer require symfony/force-lowest ~4.1.0
```

Replace the version number by the lowest one you'd like for Symfony packages.
To be effective, you should lock both the major and the minor version numbers
(use `~4.1.0` instead of `^4.1.0` as shown in the example above.)

Versioning Policy
------------------

When version `X.Y.0` of [symfony/symfony](https://github.com/symfony/symfony) is
released, the conflicting components is updated to the list of components of this
new version (new ones are added, old ones removed, branch-alias updated) and
version `X.Y+1.0` of `symfony/force-lowest` is tagged.
