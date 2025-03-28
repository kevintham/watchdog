.. :changelog:

Changelog
---------

0.10.0
~~~~~~

unreleased • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.9.0...master>`__

Breaking Changes
================

- Dropped support for Python 2.6, 3.2 and 3.3
- Emitters that failed to start are now removed
- [watchmedo] The utility is no more installed by default but via the extra
  ``watchdog[watchmedo]``

Other Changes
=============

- Fixed several Python 3 warnings
- Identify synthesized events with ``is_synthetic`` attribute (`#369 <https://github.com/gorakhargosh/watchdog/pull/369>`__)
- Use ``os.scandir()`` to improve memory usage (`#503 <https://github.com/gorakhargosh/watchdog/pull/503>`__)
- [bsd] Fixed flavors of FreeBSD detection (`#529 <https://github.com/gorakhargosh/watchdog/pull/529>`__)
- [bsd] Skip unprocessable socket files (`#509 <https://github.com/gorakhargosh/watchdog/issue/509>`__)
- [inotify] Fixed events containing non-ASCII characters (`#516 <https://github.com/gorakhargosh/watchdog/issues/516>`__)
- [inotify] Fixed the way ``OSError`` are re-raised (`#377 <https://github.com/gorakhargosh/watchdog/issues/377>`__)
- [inotify] Fixed wrong source path after renaming a top level folder (`#515 <https://github.com/gorakhargosh/watchdog/pull/515>`__)
- [inotify] Removed  delay from non-move events (`#477 <https://github.com/gorakhargosh/watchdog/pull/477>`__)
- [mac] Fixed a bug when calling ``FSEventsEmitter.stop()`` twice (`#466 <https://github.com/gorakhargosh/watchdog/pull/466>`__)
- [mac] Support for unscheduling deleted watch (`#541 <https://github.com/gorakhargosh/watchdog/issue/541>`__)
- [mac] Fixed missing field initializers and unused parameters in
  ``watchdog_fsevents.c``
- [snapshot] Don't walk directories without read permissions (`#408 <https://github.com/gorakhargosh/watchdog/pull/408>`__)
- [snapshot] Fixed a race condition crash when a directory is swapped for a file (`#513 <https://github.com/gorakhargosh/watchdog/pull/513>`__)
- [snasphot] Fixed an ``AttributeError`` about forgotten ``path_for_inode`` attr (`#436 <https://github.com/gorakhargosh/watchdog/issues/436>`__)
- [snasphot] Added the ``ignore_device=False`` parameter to the ctor (`597 <https://github.com/gorakhargosh/watchdog/pull/597>`__)
- [watchmedo] Fixed the path separator used (`#478 <https://github.com/gorakhargosh/watchdog/pull/478>`__)
- [watchmedo] Fixed the use of ``yaml.load()`` for ``yaml.safe_load()`` (`#453 <https://github.com/gorakhargosh/watchdog/issues/453>`__)
- [watchmedo] Handle all available signals (`#549 <https://github.com/gorakhargosh/watchdog/issue/549>`__)
- [watchmedo] Added the ``--debug-force-polling`` argument (`#404 <https://github.com/gorakhargosh/watchdog/pull/404>`__)
- [windows] Fixed issues when the observed directory is deleted (`#570 <https://github.com/gorakhargosh/watchdog/issues/570>`__ and `#601 <https://github.com/gorakhargosh/watchdog/pull/601>`__)
- [windows] ``WindowsApiEmitter`` made easier to subclass (`#344 <https://github.com/gorakhargosh/watchdog/pull/344>`__)
- [windows] Use separate ctypes DLL instances
- [windows] Generate sub created events only if ``recursive=True`` (`#454 <https://github.com/gorakhargosh/watchdog/pull/454>`__)
- Thanks to our beloved contributors: @BoboTiG, @LKleinNux, @rrzaripov,
  @wildmichael, @TauPan, @segevfiner, @petrblahos, @QuantumEnergyE,
  @jeffwidman, @kapsh, @nickoala, @petrblahos, @julianolf, @tonybaloney,
  @mbakiev, @pR0Ps, javaguirre, @skurfer, @exarkun, @joshuaskelly,
  @danilobellini, @Ajordat


0.9.0
~~~~~

2018-08-28 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.8.3...v0.9.0>`__

- Deleting the observed directory now emits a ``DirDeletedEvent`` event
- [bsd] Improved the platform detection (`#378 <https://github.com/gorakhargosh/watchdog/pull/378>`__)
- [inotify] Fixed a crash when the root directory being watched by was deleted (`#374 <https://github.com/gorakhargosh/watchdog/pull/374>`__)
- [inotify] Handle systems providing uClibc
- [linux] Fixed a possible ``DirDeletedEvent`` duplication when
  deleting a directory
- [mac] Fixed unicode path handling ``fsevents2.py`` (`#298 <https://github.com/gorakhargosh/watchdog/pull/298>`__)
- [watchmedo] Added the ``--debug-force-polling`` argument (`#336 <https://github.com/gorakhargosh/watchdog/pull/336>`__)
- [windows] Fixed the ``FILE_LIST_DIRECTORY`` constant (`#376 <https://github.com/gorakhargosh/watchdog/pull/376>`__)
- Thanks to our beloved contributors: @vulpeszerda, @hpk42, @tamland, @senden9,
  @gorakhargosh, @nolsto, @mafrosis, @DonyorM, @anthrotype, @danilobellini,
  @pierregr, @ShinNoNoir, @adrpar, @gforcada, @pR0Ps, @yegorich, @dhke


0.8.3
~~~~~

2015-02-11 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.8.2...v0.8.3>`__

- Fixed the use of the root logger (`#274 <https://github.com/gorakhargosh/watchdog/issues/274>`__)
- [inotify] Refactored libc loading and improved error handling in
  ``inotify_c.py``
- [inotify] Fixed a possible unbound local error in ``inotify_c.py``
- Thanks to our beloved contributors: @mmorearty, @tamland, @tony,
  @gorakhargosh


0.8.2
~~~~~

2014-10-29 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.8.1...v0.8.2>`__

- Event emitters are no longer started on schedule if ``Observer`` is not
  already running
- [mac] Fixed usued arguments to pass clang compilation (`#265 <https://github.com/gorakhargosh/watchdog/pull/265>`__)
- [snapshot] Fixed a possible race condition crash on directory deletion (`#281 <https://github.com/gorakhargosh/watchdog/pull/281>`__)
- [windows] Fixed an error when watching the same folder again (`#270 <https://github.com/gorakhargosh/watchdog/pull/270>`__)
- Thanks to our beloved contributors: @tamland, @apetrone, @Falldog,
  @theospears


0.8.1
~~~~~

2014-07-28 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.8.0...v0.8.1>`__

- Fixed ``anon_inode`` descriptors leakage  (`#249 <https://github.com/gorakhargosh/watchdog/pull/249>`__)
- [inotify] Fixed thread stop dead lock (`#250 <https://github.com/gorakhargosh/watchdog/issues/250>`__)
- Thanks to our beloved contributors: @Witos, @adiroiban, @tamland


0.8.0
~~~~~

2014-07-02 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.7.1...v0.8.0>`__

- Fixed ``argh`` deprecation warnings (`#242 <https://github.com/gorakhargosh/watchdog/pull/242>`__)
- [snapshot] Methods returning internal stats info were replaced by
  ``mtime()``, ``inode()`` and ``path()`` methods
- [snapshot] Deprecated the ``walker_callback`` argument
- [watchmedo] Fixed ``auto-restart`` to terminate all children processes (`#225 <https://github.com/gorakhargosh/watchdog/pull/225>`__)
- [watchmedo] Added the ``--no-parallel`` argument (`#227 <https://github.com/gorakhargosh/watchdog/issues/227>`__)
- [windows] Fixed the value of ``INVALID_HANDLE_VALUE`` (`#123 <https://github.com/gorakhargosh/watchdog/issues/123>`__)
- [windows] Fixed octal usages to work with Python 3 as well (`#223 <https://github.com/gorakhargosh/watchdog/issues/223>`__)
- Thanks to our beloved contributors: @tamland, @Ormod, @berdario, @cro,
  @BernieSumption, @pypingou, @gotcha, @tommorris, @frewsxcv
