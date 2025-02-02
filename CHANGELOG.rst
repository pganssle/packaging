Changelog
---------

20.0 - `master`_
~~~~~~~~~~~~~~~~

.. note:: This version is not yet released and is under active development.

* Add the `packaging.tags` module.


19.0 - 2019-01-20
~~~~~~~~~~~~~~~~~

* Fix string representation of PEP 508 direct URL requirements with markers.

* Better handling of file URLs

  This allows for using ``file:///absolute/path``, which was previously
  prevented due to the missing ``netloc``.

  This allows for all file URLs that ``urlunparse`` turns back into the
  original URL to be valid.


18.0 - 2018-09-26
~~~~~~~~~~~~~~~~~

* Improve error messages when invalid requirements are given. (:issue:`129`)


17.1 - 2017-02-28
~~~~~~~~~~~~~~~~~

* Fix ``utils.canonicalize_version`` when supplying non PEP 440 versions.


17.0 - 2017-02-28
~~~~~~~~~~~~~~~~~

* Drop support for python 2.6, 3.2, and 3.3.

* Define minimal pyparsing version to 2.0.2 (:issue:`91`).

* Add ``epoch``, ``release``, ``pre``, ``dev``, and ``post`` attributes to
  ``Version`` and ``LegacyVersion`` (:issue:`34`).

* Add ``Version().is_devrelease`` and ``LegacyVersion().is_devrelease`` to
  make it easy to determine if a release is a development release.

* Add ``utils.canonicalize_version`` to canonicalize version strings or
  ``Version`` instances (:issue:`121`).


16.8 - 2016-10-29
~~~~~~~~~~~~~~~~~

* Fix markers that utilize ``in`` so that they render correctly.

* Fix an erroneous test on Python RC releases.


16.7 - 2016-04-23
~~~~~~~~~~~~~~~~~

* Add support for the deprecated ``python_implementation`` marker which was
  an undocumented setuptools marker in addition to the newer markers.


16.6 - 2016-03-29
~~~~~~~~~~~~~~~~~

* Add support for the deprecated, PEP 345 environment markers in addition to
  the newer markers.


16.5 - 2016-02-26
~~~~~~~~~~~~~~~~~

* Fix a regression in parsing requirements with whitespaces between the comma
  separators.


16.4 - 2016-02-22
~~~~~~~~~~~~~~~~~

* Fix a regression in parsing requirements like ``foo (==4)``.


16.3 - 2016-02-21
~~~~~~~~~~~~~~~~~

* Fix a bug where ``packaging.requirements:Requirement`` was overly strict when
  matching legacy requirements.


16.2 - 2016-02-09
~~~~~~~~~~~~~~~~~

* Add a function that implements the name canonicalization from PEP 503.


16.1 - 2016-02-07
~~~~~~~~~~~~~~~~~

* Implement requirement specifiers from PEP 508.


16.0 - 2016-01-19
~~~~~~~~~~~~~~~~~

* Relicense so that packaging is available under *either* the Apache License,
  Version 2.0 or a 2 Clause BSD license.

* Support installation of packaging when only distutils is available.

* Fix ``==`` comparison when there is a prefix and a local version in play.
  (:issue:`41`).

* Implement environment markers from PEP 508.


15.3 - 2015-08-01
~~~~~~~~~~~~~~~~~

* Normalize post-release spellings for rev/r prefixes. :issue:`35`


15.2 - 2015-05-13
~~~~~~~~~~~~~~~~~

* Fix an error where the arbitary specifier (``===``) was not correctly
  allowing pre-releases when it was being used.

* Expose the specifier and version parts through properties on the
  ``Specifier`` classes.

* Allow iterating over the ``SpecifierSet`` to get access to all of the
  ``Specifier`` instances.

* Allow testing if a version is contained within a specifier via the ``in``
  operator.


15.1 - 2015-04-13
~~~~~~~~~~~~~~~~~

* Fix a logic error that was causing inconsistent answers about whether or not
  a pre-release was contained within a ``SpecifierSet`` or not.


15.0 - 2015-01-02
~~~~~~~~~~~~~~~~~

* Add ``Version().is_postrelease`` and ``LegacyVersion().is_postrelease`` to
  make it easy to determine if a release is a post release.

* Add ``Version().base_version`` and ``LegacyVersion().base_version`` to make
  it easy to get the public version without any pre or post release markers.

* Support the update to PEP 440 which removed the implied ``!=V.*`` when using
  either ``>V`` or ``<V`` and which instead special cased the handling of
  pre-releases, post-releases, and local versions when using ``>V`` or ``<V``.


14.5 - 2014-12-17
~~~~~~~~~~~~~~~~~

* Normalize release candidates as ``rc`` instead of ``c``.

* Expose the ``VERSION_PATTERN`` constant, a regular expression matching
  a valid version.


14.4 - 2014-12-15
~~~~~~~~~~~~~~~~~

* Ensure that versions are normalized before comparison when used in a
  specifier with a less than (``<``) or greater than (``>``) operator.


14.3 - 2014-11-19
~~~~~~~~~~~~~~~~~

* **BACKWARDS INCOMPATIBLE** Refactor specifier support so that it can sanely
  handle legacy specifiers as well as PEP 440 specifiers.

* **BACKWARDS INCOMPATIBLE** Move the specifier support out of
  ``packaging.version`` into ``packaging.specifiers``.


14.2 - 2014-09-10
~~~~~~~~~~~~~~~~~

* Add prerelease support to ``Specifier``.
* Remove the ability to do ``item in Specifier()`` and replace it with
  ``Specifier().contains(item)`` in order to allow flags that signal if a
  prerelease should be accepted or not.
* Add a method ``Specifier().filter()`` which will take an iterable and returns
  an iterable with items that do not match the specifier filtered out.


14.1 - 2014-09-08
~~~~~~~~~~~~~~~~~

* Allow ``LegacyVersion`` and ``Version`` to be sorted together.
* Add ``packaging.version.parse()`` to enable easily parsing a version string
  as either a ``Version`` or a ``LegacyVersion`` depending on it's PEP 440
  validity.


14.0 - 2014-09-05
~~~~~~~~~~~~~~~~~

* Initial release.


.. _`master`: https://github.com/pypa/packaging/
