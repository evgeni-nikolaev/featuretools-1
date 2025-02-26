.. _release_notes:

Release Notes
-------------
Future Release
==============
    * Enhancements
    * Fixes
    * Changes
        * Add auto assign bot on GitHub (:pr:`1380`)
    * Documentation Changes
        * Improve formatting of release notes (:pr:`1396`)
    * Testing Changes
        * Update Dask/Koalas test fixtures (:pr:`1382`)
        * Update Spark config in test fixtures and docs (:pr:`1387`, :pr:`1389`)
        * Don't cancel other CI jobs if one fails (:pr:`1386`)
        * Update boto3 and urllib3 version requirements (:pr:`1394`)
        * Change from GitHub PAT to auto generated GitHub Token for dependency checker (:pr:`1402`)
        
    Thanks to the following people for contributing to this release:
    :user:`gsheni`, :user:`rwedge`, :user:`thehomebrewnerd`

v0.23.3 Mar 31, 2021
====================
    .. warning::
        The next non-bugfix release of Featuretools will not support Python 3.6

    * Changes
        * Minor updates to work with Koalas version 1.7.0 (:pr:`1351`)
        * Explicitly mention Python 3.8 support in setup.py classifiers (:pr:`1371`)
        * Fix issue with smart-open version 5.0.0 (:pr:`1372`, :pr:`1376`)
    * Testing Changes
        * Make release notes updated check separate from unit tests (:pr:`1347`)
        * Performance tests now specify which commit to check (:pr:`1354`)

    Thanks to the following people for contributing to this release:
    :user:`gsheni`, :user:`rwedge`, :user:`thehomebrewnerd`

v0.23.2 Feb 26, 2021
====================
    .. warning::
        The next non-bugfix release of Featuretools will not support Python 3.6

    * Enhancements
        * The ``list_primitives`` function returns valid input types and the return type (:pr:`1341`)
    * Fixes
        * Restrict numpy version when installing koalas (:pr:`1329`)
    * Changes
        * Warn python 3.6 users support will be dropped in future release (:pr:`1344`)
    * Documentation Changes
        * Update docs for defining custom primitives (:pr:`1332`)
        * Update featuretools release instructions (:pr:`1345`)

    Thanks to the following people for contributing to this release:
    :user:`gsheni`, :user:`jeff-hernandez`, :user:`rwedge`

v0.23.1 Jan 29, 2021
====================
    * Fixes
        * Calculate direct features uses default value if parent missing (:pr:`1312`)
        * Fix bug and improve tests for ``EntitySet.__eq__`` and ``Entity.__eq__`` (:pr:`1323`)
    * Documentation Changes
        * Update Twitter link to documentation toolbar (:pr:`1322`)
    * Testing Changes
        * Unpin python-graphviz package on Windows (:pr:`1296`)
        * Reorganize and clean up tests (:pr:`1294`, :pr:`1303`, :pr:`1306`)
        * Trigger tests on pull request events (:pr:`1304`, :pr:`1315`)
        * Remove unnecessary test skips on Windows (:pr:`1320`)

    Thanks to the following people for contributing to this release:
    :user:`gsheni`, :user:`jeff-hernandez`, :user:`rwedge`, :user:`seriallazer`, :user:`thehomebrewnerd`

v0.23.0 Dec 31, 2020
====================
    * Fixes
        * Fix logic for inferring variable type from unusual dtype (:pr:`1273`)
        * Allow passing entities without relationships to ``calculate_feature_matrix`` (:pr:`1290`)
    * Changes
        * Move ``query_by_values`` method from ``Entity`` to ``EntitySet`` (:pr:`1251`)
        * Move ``_handle_time`` method from ``Entity`` to ``EntitySet`` (:pr:`1276`)
        * Remove usage of ``ravel`` to resolve unexpected warning with pandas 1.2.0 (:pr:`1286`)
    * Documentation Changes
        * Fix installation command for Add-ons (:pr:`1279`)
        * Fix various broken links in documentation (:pr:`1313`)
    * Testing Changes
        * Use repository-scoped token for dependency check (:pr:`1245`:, :pr:`1248`)
        * Fix install error during docs CI test (:pr:`1250`)

    Thanks to the following people for contributing to this release:
    :user:`gsheni`, :user:`jeff-hernandez`, :user:`rwedge`, :user:`thehomebrewnerd`

Breaking Changes
++++++++++++++++

* ``Entity.query_by_values`` has been removed and replaced by ``EntitySet.query_by_values`` with an
  added ``entity_id`` parameter to specify which entity in the entityset should be used for the query.

v0.22.0 Nov 30, 2020
====================
    * Enhancements
        * Allow variable descriptions to be set directly on variable (:pr:`1207`)
        * Add ability to add feature description captions to feature lineage graphs (:pr:`1212`)
        * Add support for local tar file in read_entityset (:pr:`1228`)
    * Fixes
        * Updates to fix unit test errors from koalas 1.4 (:pr:`1230`, :pr:`1232`)
    * Documentation Changes
        * Removed link to unused feedback board (:pr:`1220`)
        * Update footer with Alteryx Innovation Labs (:pr:`1221`)
        * Update links to repo in documentation to use alteryx org url (:pr:`1224`)
    * Testing Changes
        * Update release notes check to use new repo url (:pr:`1222`)
        * Use new version of pull request Github Action (:pr:`1234`)
        * Upgrade pip during featuretools[complete] test (:pr:`1236`)
        * Migrated CI tests to github actions (:pr:`1226`, :pr:`1237`, :pr:`1239`)

    Thanks to the following people for contributing to this release:
    :user:`frances-h`, :user:`gsheni`, :user:`jeff-hernandez`, :user:`kmax12`, :user:`rwedge`, :user:`thehomebrewnerd`

v0.21.0 Oct 30, 2020
====================
    * Enhancements
        * Add ``describe_feature`` to generate an English language feature description for a given feature (:pr:`1201`)
    * Fixes
        * Update ``EntitySet.add_last_time_indexes`` to work with Koalas 1.3.0 (:pr:`1192`, :pr:`1202`)
    * Changes
        * Keep koalas requirements in separate file (:pr:`1195`)
    * Documentation Changes
        * Added footer to the documentation (:pr:`1189`)
        * Add guide for feature selection functions (:pr:`1184`)
        * Fix README.md badge with correct link (:pr:`1200`)
    * Testing Changes
        * Add ``pyspark`` and ``koalas`` to automated dependency checks (:pr:`1191`)
        * Add DockerHub credentials to CI testing environment (:pr:`1204`)
        * Update premium primitives job name on CI (:pr:`1205`)

    Thanks to the following people for contributing to this release:
    :user:`frances-h`, :user:`gsheni`, :user:`jeff-hernandez`, :user:`rwedge`, :user:`tamargrey`, :user:`thehomebrewnerd`

v0.20.0 Sep 30, 2020
====================
    .. warning::
        The Text variable type has been deprecated and been replaced with the NaturalLanguage variable type. The Text variable type will be removed in a future release.

    * Fixes
        * Allow FeatureOutputSlice features to be serialized (:pr:`1150`)
        * Fix duplicate label column generation when labels are passed in cutoff times and approximate is being used (:pr:`1160`)
        * Determine calculate_feature_matrix behavior with approximate and a cutoff df that is a subclass of a pandas DataFrame (:pr:`1166`)
    * Changes
        * Text variable type has been replaced with NaturalLanguage (:pr:`1159`)
    * Documentation Changes
        * Update release doc for clarity and to add Future Release template (:pr:`1151`)
        * Use the PyData Sphinx theme (:pr:`1169`)
    * Testing Changes
        * Stop requiring single-threaded dask scheduler in tests (:pr:`1163`, :pr:`1170`)

    Thanks to the following people for contributing to this release:
    :user:`gsheni`, :user:`rwedge`, :user:`tamargrey`, :user:`tuethan1999`

v0.19.0 Sep 8, 2020
===================
    * Enhancements
        * Support use of Koalas DataFrames in entitysets (:pr:`1031`)
        * Add feature selection functions for null, correlated, and single value features (:pr:`1126`)
    * Fixes
        * Fix ``encode_features`` converting excluded feature columns to a numeric dtype (:pr:`1123`)
        * Improve performance of unused primitive check in dfs (:pr:`1140`)
    * Changes
        * Remove the ability to stack transform primitives (:pr:`1119`, :pr:`1145`)
        * Sort primitives passed to ``dfs`` to get consistent ordering of features\* (:pr:`1119`)
    * Documentation Changes
        * Added return values to dfs and calculate_feature_matrix (:pr:`1125`)
    * Testing Changes
        * Better test case for normalizing from no time index to time index (:pr:`1113`)

    \* When passing multiple instances of a primitive built with ``make_trans_primitive``
    or ``maxe_agg_primitive``, those instances must have the same relative order when passed
    to ``dfs`` to ensure a consistent ordering of features.

    Thanks to the following people for contributing to this release:
    :user:`frances-h`, :user:`gsheni`, :user:`rwedge`, :user:`tamargrey`, :user:`thehomebrewnerd`, :user:`tuethan1999`


Breaking Changes
++++++++++++++++

* ``ft.dfs`` will no longer build features from Transform primitives where one
  of the inputs is a Transform feature, a GroupByTransform feature,
  or a Direct Feature of a Transform / GroupByTransform feature. This will make some
  features that would previously be generated by ``ft.dfs`` only possible if
  explicitly specified in ``seed_features``.

v0.18.1 Aug 12, 2020
====================
    * Fixes
        * Fix ``EntitySet.plot()`` when given a dask entityset (:pr:`1086`)
    * Changes
        * Use ``nlp-primitives[complete]`` install for ``nlp_primitives`` extra in ``setup.py`` (:pr:`1103`)
    * Documentation Changes
        * Fix broken downloads badge in README.md (:pr:`1107`)
    * Testing Changes
        * Use CircleCI matrix jobs in config to trigger multiple runs of same job with different parameters (:pr:`1105`)

    Thanks to the following people for contributing to this release:
    :user:`gsheni`, :user:`systemshift`, :user:`thehomebrewnerd`

v0.18.0 Jul 31, 2020
====================
    * Enhancements
        * Warn user if supplied primitives are not used during dfs (:pr:`1073`)
    * Fixes
        * Use more consistent and uniform warnings (:pr:`1040`)
        * Fix issue with missing instance ids and categorical entity index (:pr:`1050`)
        * Remove warnings.simplefilter in feature_set_calculator to un-silence warnings (:pr:`1053`)
        * Fix feature visualization for features with '>' or '<' in name (:pr:`1055`)
        * Fix boolean dtype mismatch between encode_features and dfs and calculate_feature_matrix (:pr:`1082`)
        * Update primitive options to check reversed inputs if primitive is commutative (:pr:`1085`)
        * Fix inconsistent ordering of features between kernel restarts (:pr:`1088`)
    * Changes
        * Make DFS match ``TimeSince`` primitive with all ``Datetime`` types (:pr:`1048`)
        * Change default branch to ``main`` (:pr:`1038`)
        * Raise TypeError if improper input is supplied to ``Entity.delete_variables()`` (:pr:`1064`)
        * Updates for compatibility with pandas 1.1.0 (:pr:`1079`, :pr:`1089`)
        * Set pandas version to pandas>=0.24.1,<2.0.0. Filter pandas deprecation warning in Week primitive. (:pr:`1094`)
    * Documentation Changes
        * Remove benchmarks folder (:pr:`1049`)
        * Add custom variables types section to variables page (:pr:`1066`)
    * Testing Changes
        * Add fixture for ``ft.demo.load_mock_customer`` (:pr:`1036`)
        * Refactor Dask test units (:pr:`1052`)
        * Implement automated process for checking critical dependencies (:pr:`1045`, :pr:`1054`, :pr:`1081`)
        * Don't run changelog check for release PRs or automated dependency PRs (:pr:`1057`)
        * Fix non-deterministic behavior in Dask test causing codecov issues (:pr:`1070`)

    Thanks to the following people for contributing to this release:
    :user:`frances-h`, :user:`gsheni`, :user:`monti-python`, :user:`rwedge`,
    :user:`systemshift`,  :user:`tamargrey`, :user:`thehomebrewnerd`, :user:`wsankey`

v0.17.0 Jun 30, 2020
====================
    * Enhancements
        * Add ``list_variable_types`` and ``graph_variable_types`` for Variable Types (:pr:`1013`)
        * Add ``graph_feature`` to generate a feature lineage graph for a given feature (:pr:`1032`)
    * Fixes
        * Improve warnings when using a Dask dataframe for cutoff times (:pr:`1026`)
        * Error if attempting to add entityset relationship where child variable is also child index (:pr:`1034`)
    * Changes
        * Remove ``Feature.get_names`` (:pr:`1021`)
        * Remove unnecessary ``pd.Series`` and ``pd.DatetimeIndex`` calls from primitives (:pr:`1020`, :pr:`1024`)
        * Improve cutoff time handling when a single value or no value is passed (:pr:`1028`)
        * Moved ``find_variable_types`` to Variable utils (:pr:`1013`)
    * Documentation Changes
        * Add page on Variable Types to describe some Variable Types, and util functions (:pr:`1013`)
        * Remove featuretools enterprise from documentation (:pr:`1022`)
        * Add development install instructions to contributing.md (:pr:`1030`)
    * Testing Changes
        * Add ``required`` flag to CircleCI codecov upload command (:pr:`1035`)

    Thanks to the following people for contributing to this release:
    :user:`frances-h`, :user:`gsheni`, :user:`kmax12`, :user:`rwedge`,
    :user:`thehomebrewnerd`, :user:`tuethan1999`

Breaking Changes
++++++++++++++++

* Removed ``Feature.get_names``, ``Feature.get_feature_names`` should be used instead

v0.16.0 Jun 5, 2020
===================
    * Enhancements
        * Support use of Dask DataFrames in entitysets (:pr:`783`)
        * Add ``make_index`` when initializing an EntitySet by passing in an ``entities`` dictionary (:pr:`1010`)
        * Add ability to use primitive classes and instances as keys in primitive_options dictionary (:pr:`993`)
    * Fixes
        * Cleanly close tqdm instance (:pr:`1018`)
        * Resolve issue with ``NaN`` values in ``LatLong`` columns (:pr:`1007`)
    * Testing Changes
        * Update tests for numpy v1.19.0 compatability (:pr:`1016`)

    Thanks to the following people for contributing to this release:
    :user:`Alex-Monahan`, :user:`frances-h`, :user:`gsheni`, :user:`rwedge`, :user:`thehomebrewnerd`

v0.15.0 May 29, 2020
====================
    * Enhancements
        * Add ``get_default_aggregation_primitives`` and ``get_default_transform_primitives`` (:pr:`945`)
        * Allow cutoff time dataframe columns to be in any order (:pr:`969`, :pr:`995`)
        * Add Age primitive, and make it a default transform primitive for DFS (:pr:`987`)
        * Add ``include_cutoff_time`` arg - control whether data at cutoff times are included in feature calculations (:pr:`959`)
        * Allow ``variables_types`` to be referenced by their ``type_string``
          for the ``entity_from_dataframe`` function (:pr:`988`)
    * Fixes
        * Fix errors with Equals and NotEquals primitives when comparing categoricals or different dtypes (:pr:`968`)
        * Normalized type_strings of ``Variable`` classes so that the ``find_variable_types`` function produces a
          dictionary with a clear key to name transition (:pr:`982`, :pr:`996`)
        * Remove pandas.datetime in test_calculate_feature_matrix due to deprecation (:pr:`998`)
    * Documentation Changes
        * Add python 3.8 support for docs (:pr:`983`)
        * Adds consistent Entityset Docstrings (:pr:`986`)
    * Testing Changes
        * Add automated tests for python 3.8 environment (:pr:`847`)
        * Update testing dependencies (:pr:`976`)

    Thanks to the following people for contributing to this release:
    :user:`ctduffy`, :user:`frances-h`, :user:`gsheni`, :user:`jeff-hernandez`, :user:`rightx2`, :user:`rwedge`, :user:`sebrahimi1988`, :user:`thehomebrewnerd`,  :user:`tuethan1999`

Breaking Changes
++++++++++++++++

* Calls to ``featuretools.dfs`` or ``featuretools.calculate_feature_matrix`` that use a cutoff time
  dataframe, but do not label the time column with either the target entity time index variable name or
  as ``time``, will now result in an ``AttributeError``. Previously, the time column was selected to be the first
  column that was not the instance id column. With this update, the position of the column in the dataframe is
  no longer used to determine the time column. Now, both instance id columns and time columns in a cutoff time
  dataframe can be in any order as long as they are named properly.

* The ``type_string`` attributes of all ``Variable`` subclasses are now a snake case conversion of their class names. This
  changes the ``type_string`` of the ``Unknown``, ``IPAddress``, ``EmailAddress``, ``SubRegionCode``, ``FilePath``, ``LatLong``, and ``ZIPcode`` classes.
  Old saved entitysets that used these variables may load incorrectly.

v0.14.0 Apr 30, 2020
====================
    * Enhancements
        * ft.encode_features - use less memory for one-hot encoded columns (:pr:`876`)
    * Fixes
        * Use logger.warning to fix deprecated logger.warn (:pr:`871`)
        * Add dtype to interesting_values to fix deprecated empty Series with no dtype (:pr:`933`)
        * Remove overlap in training windows (:pr:`930`)
        * Fix progress bar in notebook (:pr:`932`)
    * Changes
        * Change premium primitives CI test to Python 3.6 (:pr:`916`)
        * Remove Python 3.5 support (:pr:`917`)
    * Documentation Changes
        * Fix README links to docs (:pr:`872`)
        * Fix Github links with correct organizations (:pr:`908`)
        * Fix hyperlinks in docs and docstrings with updated address (:pr:`910`)
        * Remove unused script for uploading docs to AWS (:pr:`911`)

    Thanks to the following people for contributing to this release:
    :user:`frances-h`, :user:`gsheni`, :user:`jeff-hernandez`, :user:`rwedge`

Breaking Changes
++++++++++++++++

* Using training windows in feature calculations can result in different values than previous versions.
  This was done to prevent consecutive training windows from overlapping by excluding data at the oldest point in time.
  For example, if we use a cutoff time at the first minute of the hour with a one hour training window,
  the first minute of the previous hour will no longer be included in the feature calculation.

v0.13.4 Mar 27, 2020
====================
    .. warning::
        The next non-bugfix release of Featuretools will not support Python 3.5

    * Fixes
        * Fix ft.show_info() not displaying in Jupyter notebooks (:pr:`863`)
    * Changes
        * Added Plugin Warnings at Entry Point (:pr:`850`, :pr:`869`)
    * Documentation Changes
        * Add links to primitives.featurelabs.com (:pr:`860`)
        * Add source code links to API reference (:pr:`862`)
        * Update links for testing Dask/Spark integrations (:pr:`867`)
        * Update release documentation for featuretools (:pr:`868`)
    * Testing Changes
        * Miscellaneous changes (:pr:`861`)

    Thanks to the following people for contributing to this release:
    :user:`frances-h`, :user:`FreshLeaf8865`, :user:`jeff-hernandez`, :user:`rwedge`, :user:`thehomebrewnerd`

v0.13.3 Feb 28, 2020
====================
    * Fixes
        * Fix a connection closed error when using n_jobs (:pr:`853`)
    * Changes
        * Pin msgpack dependency for Python 3.5; remove dataframe from Dask dependency (:pr:`851`)
    * Documentation Changes
        * Update link to help documentation page in Github issue template (:pr:`855`)

    Thanks to the following people for contributing to this release:
    :user:`frances-h`, :user:`rwedge`

v0.13.2 Jan 31, 2020
====================
    * Enhancements
        * Support for Pandas 1.0.0 (:pr:`844`)
    * Changes
        * Remove dependency on s3fs library for anonymous downloads from S3 (:pr:`825`)
    * Testing Changes
        * Added GitHub Action to automatically run performance tests (:pr:`840`)

    Thanks to the following people for contributing to this release:
    :user:`frances-h`, :user:`rwedge`

v0.13.1 Dec 28, 2019
====================
    * Fixes
        * Raise error when given wrong input for ignore_variables (:pr:`826`)
        * Fix multi-output features not created when there is no child data (:pr:`834`)
        * Removing type casting in Equals and NotEquals primitives (:pr:`504`)
    * Changes
        * Replace pd.timedelta time units that were deprecated (:pr:`822`)
        * Move sklearn wrapper to separate library (:pr:`835`, :pr:`837`)
    * Testing Changes
        * Run unit tests in windows environment (:pr:`790`)
        * Update boto3 version requirement for tests (:pr:`838`)

    Thanks to the following people for contributing to this release:
    :user:`jeffzi`, :user:`kmax12`, :user:`rwedge`, :user:`systemshift`

v0.13.0 Nov 30, 2019
====================
    * Enhancements
        * Added GitHub Action to auto upload releases to PyPI (:pr:`816`)
    * Fixes
        * Fix issue where some primitive options would not be applied (:pr:`807`)
        * Fix issue with converting to pickle or parquet after adding interesting features (:pr:`798`, :pr:`823`)
        * Diff primitive now calculates using all available data (:pr:`824`)
        * Prevent DFS from creating Identity Features of globally ignored variables (:pr:`819`)
    * Changes
        * Remove python 2.7 support from serialize.py (:pr:`812`)
        * Make smart_open, boto3, and s3fs optional dependencies (:pr:`827`)
    * Documentation Changes
        * remove python 2.7 support and add 3.7 in install.rst (:pr:`805`)
        * Fix import error in docs (:pr:`803`)
        * Fix release title formatting in changelog (:pr:`806`)
    * Testing Changes
        * Use multiple CPUS to run tests on CI (:pr:`811`)
        * Refactor test entityset creation to avoid saving to disk (:pr:`813`, :pr:`821`)
        * Remove get_values() from test_es.py to remove warnings (:pr:`820`)

    Thanks to the following people for contributing to this release:
    :user:`frances-h`, :user:`jeff-hernandez`, :user:`rwedge`, :user:`systemshift`

Breaking Changes
++++++++++++++++

* The libraries used for downloading or uploading from S3 or URLs are now
  optional and will no longer be installed by default.  To use this
  functionality they will need to be installed separately.
* The fix to how the Diff primitive is calculated may slow down the overall
  calculation time of feature lists that use this primitive.

v0.12.0 Oct 31, 2019
====================
    * Enhancements
        * Added First primitive (:pr:`770`)
        * Added Entropy aggregation primitive (:pr:`779`)
        * Allow custom naming for multi-output primitives (:pr:`780`)
    * Fixes
        * Prevents user from removing base entity time index using additional_variables (:pr:`768`)
        * Fixes error when a multioutput primitive was supplied to dfs as a groupby trans primitive (:pr:`786`)
    * Changes
        * Drop Python 2 support (:pr:`759`)
        * Add unit parameter to AvgTimeBetween (:pr:`771`)
        * Require Pandas 0.24.1 or higher (:pr:`787`)
    * Documentation Changes
        * Update featuretools slack link (:pr:`765`)
        * Set up repo to use Read the Docs (:pr:`776`)
        * Add First primitive to API reference docs (:pr:`782`)
    * Testing Changes
        * CircleCI fixes (:pr:`774`)
        * Disable PIP progress bars (:pr:`775`)

    Thanks to the following people for contributing to this release:
    :user:`ablacke-ayx`, :user:`BoopBoopBeepBoop`, :user:`jeffzi`,
    :user:`kmax12`, :user:`rwedge`, :user:`thehomebrewnerd`, :user:`twdobson`

v0.11.0 Sep 30, 2019
====================
    .. warning::
        The next non-bugfix release of Featuretools will not support Python 2

    * Enhancements
        * Improve how files are copied and written (:pr:`721`)
        * Add number of rows to graph in entityset.plot (:pr:`727`)
        * Added support for pandas DateOffsets in DFS and Timedelta (:pr:`732`)
        * Enable feature-specific top_n value using a dictionary in encode_features (:pr:`735`)
        * Added progress_callback parameter to dfs() and calculate_feature_matrix() (:pr:`739`, :pr:`745`)
        * Enable specifying primitives on a per column or per entity basis (:pr:`748`)
    * Fixes
        * Fixed entity set deserialization (:pr:`720`)
        * Added error message when DateTimeIndex is a variable but not set as the time_index (:pr:`723`)
        * Fixed CumCount and other group-by transform primitives that take ID as input (:pr:`733`, :pr:`754`)
        * Fix progress bar undercounting (:pr:`743`)
        * Updated training_window error assertion to only check against observations (:pr:`728`)
        * Don't delete the whole destination folder while saving entityset (:pr:`717`)
    * Changes
        * Raise warning and not error on schema version mismatch (:pr:`718`)
        * Change feature calculation to return in order of instance ids provided (:pr:`676`)
        * Removed time remaining from displayed progress bar in dfs() and calculate_feature_matrix() (:pr:`739`)
        * Raise warning in normalize_entity() when time_index of base_entity has an invalid type (:pr:`749`)
        * Remove toolz as a direct dependency (:pr:`755`)
        * Allow boolean variable types to be used in the Multiply primitive (:pr:`756`)
    * Documentation Changes
        * Updated URL for Compose (:pr:`716`)
    * Testing Changes
        * Update dependencies (:pr:`738`, :pr:`741`, :pr:`747`)

    Thanks to the following people for contributing to this release:
    :user:`angela97lin`, :user:`chidauri`, :user:`christopherbunn`,
    :user:`frances-h`, :user:`jeff-hernandez`, :user:`kmax12`,
    :user:`MarcoGorelli`, :user:`rwedge`, :user:`thehomebrewnerd`

Breaking Changes
++++++++++++++++

* Feature calculations will return in the order of instance ids provided instead of the order of time points instances are calculated at.

v0.10.1 Aug 25, 2019
====================
    * Fixes
        * Fix serialized LatLong data being loaded as strings (:pr:`712`)
    * Documentation Changes
        * Fixed FAQ cell output (:pr:`710`)

    Thanks to the following people for contributing to this release:
    :user:`gsheni`, :user:`rwedge`


v0.10.0 Aug 19, 2019
====================
    .. warning::
        The next non-bugfix release of Featuretools will not support Python 2


    * Enhancements
        * Give more frequent progress bar updates and update chunk size behavior (:pr:`631`, :pr:`696`)
        * Added drop_first as param in encode_features (:pr:`647`)
        * Added support for stacking multi-output primitives (:pr:`679`)
        * Generate transform features of direct features (:pr:`623`)
        * Added serializing and deserializing from S3 and deserializing from URLs (:pr:`685`)
        * Added nlp_primitives as an add-on library (:pr:`704`)
        * Added AutoNormalize to Featuretools plugins (:pr:`699`)
        * Added functionality for relative units (month/year) in Timedelta (:pr:`692`)
        * Added categorical-encoding as an add-on library (:pr:`700`)
    * Fixes
        * Fix performance regression in DFS (:pr:`637`)
        * Fix deserialization of feature relationship path (:pr:`665`)
        * Set index after adding ancestor relationship variables (:pr:`668`)
        * Fix user-supplied variable_types modification in Entity init (:pr:`675`)
        * Don't calculate dependencies of unnecessary features (:pr:`667`)
        * Prevent normalize entity's new entity having same index as base entity (:pr:`681`)
        * Update variable type inference to better check for string values (:pr:`683`)
    * Changes
        * Moved dask, distributed imports (:pr:`634`)
    * Documentation Changes
        * Miscellaneous changes (:pr:`641`, :pr:`658`)
        * Modified doc_string of top_n in encoding (:pr:`648`)
        * Hyperlinked ComposeML (:pr:`653`)
        * Added FAQ (:pr:`620`, :pr:`677`)
        * Fixed FAQ question with multiple question marks (:pr:`673`)
    * Testing Changes
        * Add master, and release tests for premium primitives (:pr:`660`, :pr:`669`)
        * Miscellaneous changes (:pr:`672`, :pr:`674`)

    Thanks to the following people for contributing to this release:
    :user:`alexjwang`, :user:`allisonportis`, :user:`ayushpatidar`,
    :user:`CJStadler`, :user:`ctduffy`, :user:`gsheni`, :user:`jeff-hernandez`,
    :user:`jeremyliweishih`, :user:`kmax12`, :user:`rwedge`, :user:`zhxt95`,

v0.9.1 Jul 3, 2019
====================
    * Enhancements
        * Speedup groupby transform calculations (:pr:`609`)
        * Generate features along all paths when there are multiple paths between entities (:pr:`600`, :pr:`608`)
    * Fixes
        * Select columns of dataframe using a list (:pr:`615`)
        * Change type of features calculated on Index features to Categorical (:pr:`602`)
        * Filter dataframes through forward relationships (:pr:`625`)
        * Specify Dask version in requirements for python 2 (:pr:`627`)
        * Keep dataframe sorted by time during feature calculation (:pr:`626`)
        * Fix bug in encode_features that created duplicate columns of
          features with multiple outputs (:pr:`622`)
    * Changes
        * Remove unused variance_selection.py file (:pr:`613`)
        * Remove Timedelta data param (:pr:`619`)
        * Remove DaysSince primitive (:pr:`628`)
    * Documentation Changes
        * Add installation instructions for add-on libraries (:pr:`617`)
        * Clarification of Multi Output Feature Creation (:pr:`638`)
        * Miscellaneous changes (:pr:`632`, :pr:`639`)
    * Testing Changes
        * Miscellaneous changes (:pr:`595`, :pr:`612`)

    Thanks to the following people for contributing to this release:
    :user:`CJStadler`, :user:`kmax12`, :user:`rwedge`, :user:`gsheni`, :user:`kkleidal`, :user:`ctduffy`

v0.9.0 Jun 19, 2019
===================
    * Enhancements
        * Add unit parameter to timesince primitives (:pr:`558`)
        * Add ability to install optional add on libraries (:pr:`551`)
        * Load and save features from open files and strings (:pr:`566`)
        * Support custom variable types (:pr:`571`)
        * Support entitysets which have multiple paths between two entities (:pr:`572`, :pr:`544`)
        * Added show_info function, more output information added to CLI `featuretools info` (:pr:`525`)
    * Fixes
        * Normalize_entity specifies error when 'make_time_index' is an invalid string (:pr:`550`)
        * Schema version added for entityset serialization (:pr:`586`)
        * Renamed features have names correctly serialized (:pr:`585`)
        * Improved error message for index/time_index being the same column in normalize_entity and entity_from_dataframe (:pr:`583`)
        * Removed all mentions of allow_where (:pr:`587`, :pr:`588`)
        * Removed unused variable in normalize entity (:pr:`589`)
        * Change time since return type to numeric (:pr:`606`)
    * Changes
        * Refactor get_pandas_data_slice to take single entity (:pr:`547`)
        * Updates TimeSincePrevious and Diff Primitives (:pr:`561`)
        * Remove unecessary time_last variable (:pr:`546`)
    * Documentation Changes
        * Add Featuretools Enterprise to documentation (:pr:`563`)
        * Miscellaneous changes (:pr:`552`, :pr:`573`, :pr:`577`, :pr:`599`)
    * Testing Changes
        * Miscellaneous changes (:pr:`559`, :pr:`569`, :pr:`570`, :pr:`574`, :pr:`584`, :pr:`590`)

    Thanks to the following people for contributing to this release:
    :user:`alexjwang`, :user:`allisonportis`, :user:`CJStadler`, :user:`ctduffy`, :user:`gsheni`, :user:`kmax12`, :user:`rwedge`

v0.8.0 May 17, 2019
===================
    * Rename NUnique to NumUnique (:pr:`510`)
    * Serialize features as JSON (:pr:`532`)
    * Drop all variables at once in normalize_entity (:pr:`533`)
    * Remove unnecessary sorting from normalize_entity (:pr:`535`)
    * Features cache their names (:pr:`536`)
    * Only calculate features for instances before cutoff (:pr:`523`)
    * Remove all relative imports (:pr:`530`)
    * Added FullName Variable Type (:pr:`506`)
    * Add error message when target entity does not exist (:pr:`520`)
    * New demo links (:pr:`542`)
    * Remove duplicate features check in DFS (:pr:`538`)
    * featuretools_primitives entry point expects list of primitive classes (:pr:`529`)
    * Update ALL_VARIABLE_TYPES list (:pr:`526`)
    * More Informative N Jobs Prints and Warnings (:pr:`511`)
    * Update sklearn version requirements (:pr:`541`)
    * Update Makefile (:pr:`519`)
    * Remove unused parameter in Entity._handle_time (:pr:`524`)
    * Remove build_ext code from setup.py (:pr:`513`)
    * Documentation updates (:pr:`512`, :pr:`514`, :pr:`515`, :pr:`521`, :pr:`522`, :pr:`527`, :pr:`545`)
    * Testing updates (:pr:`509`, :pr:`516`, :pr:`517`, :pr:`539`)

    Thanks to the following people for contributing to this release: :user:`bphi`, :user:`CharlesBradshaw`, :user:`CJStadler`, :user:`glentennis`, :user:`gsheni`, :user:`kmax12`, :user:`rwedge`

Breaking Changes
++++++++++++++++

* ``NUnique`` has been renamed to ``NumUnique``.

    Previous behavior

    .. code-block:: python

        from featuretools.primitives import NUnique

    New behavior

    .. code-block:: python

        from featuretools.primitives import NumUnique

v0.7.1 Apr 24, 2019
===================
    * Automatically generate feature name for controllable primitives (:pr:`481`)
    * Primitive docstring updates (:pr:`489`, :pr:`492`, :pr:`494`, :pr:`495`)
    * Change primitive functions that returned strings to return functions (:pr:`499`)
    * CLI customizable via entrypoints (:pr:`493`)
    * Improve calculation of aggregation features on grandchildren (:pr:`479`)
    * Refactor entrypoints to use decorator (:pr:`483`)
    * Include doctests in testing suite (:pr:`491`)
    * Documentation updates (:pr:`490`)
    * Update how standard primitives are imported internally (:pr:`482`)

    Thanks to the following people for contributing to this release: :user:`bukosabino`, :user:`CharlesBradshaw`, :user:`glentennis`, :user:`gsheni`, :user:`jeff-hernandez`, :user:`kmax12`, :user:`minkvsky`, :user:`rwedge`, :user:`thehomebrewnerd`

v0.7.0 Mar 29, 2019
===================
    * Improve Entity Set Serialization (:pr:`361`)
    * Support calling a primitive instance's function directly (:pr:`461`, :pr:`468`)
    * Support other libraries extending featuretools functionality via entrypoints (:pr:`452`)
    * Remove featuretools install command (:pr:`475`)
    * Add GroupByTransformFeature (:pr:`455`, :pr:`472`, :pr:`476`)
    * Update Haversine Primitive (:pr:`435`, :pr:`462`)
    * Add commutative argument to SubtractNumeric and DivideNumeric primitives (:pr:`457`)
    * Add FilePath variable_type (:pr:`470`)
    * Add PhoneNumber, DateOfBirth, URL variable types (:pr:`447`)
    * Generalize infer_variable_type, convert_variable_data and convert_all_variable_data methods (:pr:`423`)
    * Documentation updates (:pr:`438`, :pr:`446`, :pr:`458`, :pr:`469`)
    * Testing updates (:pr:`440`, :pr:`444`, :pr:`445`, :pr:`459`)

    Thanks to the following people for contributing to this release: :user:`bukosabino`, :user:`CharlesBradshaw`, :user:`ColCarroll`, :user:`glentennis`, :user:`grayskripko`, :user:`gsheni`, :user:`jeff-hernandez`, :user:`jrkinley`, :user:`kmax12`, :user:`RogerTangos`, :user:`rwedge`

Breaking Changes
++++++++++++++++

* ``ft.dfs`` now has a ``groupby_trans_primitives`` parameter that DFS uses to automatically construct features that group by an ID column and then apply a transform primitive to search group. This change applies to the following primitives: ``CumSum``, ``CumCount``, ``CumMean``, ``CumMin``, and ``CumMax``.

    Previous behavior

    .. code-block:: python

        ft.dfs(entityset=es,
               target_entity='customers',
               trans_primitives=["cum_mean"])

    New behavior

    .. code-block:: python

        ft.dfs(entityset=es,
               target_entity='customers',
               groupby_trans_primitives=["cum_mean"])

* Related to the above change, cumulative transform features are now defined using a new feature class, ``GroupByTransformFeature``.

    Previous behavior

    .. code-block:: python

        ft.Feature([base_feature, groupby_feature], primitive=CumulativePrimitive)


    New behavior

    .. code-block:: python

        ft.Feature(base_feature, groupby=groupby_feature, primitive=CumulativePrimitive)


v0.6.1 Feb 15, 2019
===================
    * Cumulative primitives (:pr:`410`)
    * Entity.query_by_values now preserves row order of underlying data (:pr:`428`)
    * Implementing Country Code and Sub Region Codes as variable types (:pr:`430`)
    * Added IPAddress and EmailAddress variable types (:pr:`426`)
    * Install data and dependencies (:pr:`403`)
    * Add TimeSinceFirst, fix TimeSinceLast (:pr:`388`)
    * Allow user to pass in desired feature return types (:pr:`372`)
    * Add new configuration object (:pr:`401`)
    * Replace NUnique get_function (:pr:`434`)
    * _calculate_idenity_features now only returns the features asked for, instead of the entire entity (:pr:`429`)
    * Primitive function name uniqueness (:pr:`424`)
    * Update NumCharacters and NumWords primitives (:pr:`419`)
    * Removed Variable.dtype (:pr:`416`, :pr:`433`)
    * Change to zipcode rep, str for pandas (:pr:`418`)
    * Remove pandas version upper bound (:pr:`408`)
    * Make S3 dependencies optional (:pr:`404`)
    * Check that agg_primitives and trans_primitives are right primitive type (:pr:`397`)
    * Mean primitive changes (:pr:`395`)
    * Fix transform stacking on multi-output aggregation (:pr:`394`)
    * Fix list_primitives (:pr:`391`)
    * Handle graphviz dependency (:pr:`389`, :pr:`396`, :pr:`398`)
    * Testing updates (:pr:`402`, :pr:`417`, :pr:`433`)
    * Documentation updates (:pr:`400`, :pr:`409`, :pr:`415`, :pr:`417`, :pr:`420`, :pr:`421`, :pr:`422`, :pr:`431`)


    Thanks to the following people for contributing to this release:  :user:`CharlesBradshaw`, :user:`csala`, :user:`floscha`, :user:`gsheni`, :user:`jxwolstenholme`, :user:`kmax12`, :user:`RogerTangos`, :user:`rwedge`

v0.6.0 Jan 30, 2018
===================
    * Primitive refactor (:pr:`364`)
    * Mean ignore NaNs (:pr:`379`)
    * Plotting entitysets (:pr:`382`)
    * Add seed features later in DFS process (:pr:`357`)
    * Multiple output column features (:pr:`376`)
    * Add ZipCode Variable Type (:pr:`367`)
    * Add `primitive.get_filepath` and example of primitive loading data from external files (:pr:`380`)
    * Transform primitives take series as input (:pr:`385`)
    * Update dependency requirements (:pr:`378`, :pr:`383`, :pr:`386`)
    * Add modulo to override tests (:pr:`384`)
    * Update documentation (:pr:`368`, :pr:`377`)
    * Update README.md (:pr:`366`, :pr:`373`)
    * Update CI tests (:pr:`359`, :pr:`360`, :pr:`375`)

    Thanks to the following people for contributing to this release: :user:`floscha`, :user:`gsheni`, :user:`kmax12`, :user:`RogerTangos`, :user:`rwedge`

v0.5.1 Dec 17, 2018
===================
    * Add missing dependencies (:pr:`353`)
    * Move comment to note in documentation (:pr:`352`)

v0.5.0 Dec 17, 2018
===================
    * Add specific error for duplicate additional/copy_variables in normalize_entity (:pr:`348`)
    * Removed EntitySet._import_from_dataframe (:pr:`346`)
    * Removed time_index_reduce parameter (:pr:`344`)
    * Allow installation of additional primitives (:pr:`326`)
    * Fix DatetimeIndex variable conversion (:pr:`342`)
    * Update Sklearn DFS Transformer (:pr:`343`)
    * Clean up entity creation logic (:pr:`336`)
    * remove casting to list in transform feature calculation (:pr:`330`)
    * Fix sklearn wrapper (:pr:`335`)
    * Add readme to pypi
    * Update conda docs after move to conda-forge (:pr:`334`)
    * Add wrapper for scikit-learn Pipelines (:pr:`323`)
    * Remove parse_date_cols parameter from EntitySet._import_from_dataframe (:pr:`333`)

    Thanks to the following people for contributing to this release: :user:`bukosabino`, :user:`georgewambold`, :user:`gsheni`, :user:`jeff-hernandez`, :user:`kmax12`, and :user:`rwedge`.

v0.4.1 Nov 29, 2018
===================
    * Resolve bug preventing using first column as index by default (:pr:`308`)
    * Handle return type when creating features from Id variables (:pr:`318`)
    * Make id an optional parameter of EntitySet constructor (:pr:`324`)
    * Handle primitives with same function being applied to same column (:pr:`321`)
    * Update requirements (:pr:`328`)
    * Clean up DFS arguments (:pr:`319`)
    * Clean up Pandas Backend (:pr:`302`)
    * Update properties of cumulative transform primitives (:pr:`320`)
    * Feature stability between versions documentation (:pr:`316`)
    * Add download count to GitHub readme (:pr:`310`)
    * Fixed #297 update tests to check error strings (:pr:`303`)
    * Remove usage of fixtures in agg primitive tests (:pr:`325`)

v0.4.0 Oct 31, 2018
===================
    * Remove ft.utils.gen_utils.getsize and make pympler a test requirement (:pr:`299`)
    * Update requirements.txt (:pr:`298`)
    * Refactor EntitySet.find_path(...) (:pr:`295`)
    * Clean up unused methods (:pr:`293`)
    * Remove unused parents property of Entity (:pr:`283`)
    * Removed relationships parameter (:pr:`284`)
    * Improve time index validation (:pr:`285`)
    * Encode features with "unknown" class in categorical (:pr:`287`)
    * Allow where clauses on direct features in Deep Feature Synthesis (:pr:`279`)
    * Change to fullargsspec (:pr:`288`)
    * Parallel verbose fixes (:pr:`282`)
    * Update tests for python 3.7 (:pr:`277`)
    * Check duplicate rows cutoff times (:pr:`276`)
    * Load retail demo data using compressed file (:pr:`271`)

v0.3.1 Sep 28, 2018
===================
    * Handling time rewrite (:pr:`245`)
    * Update deep_feature_synthesis.py (:pr:`249`)
    * Handling return type when creating features from DatetimeTimeIndex (:pr:`266`)
    * Update retail.py (:pr:`259`)
    * Improve Consistency of Transform Primitives (:pr:`236`)
    * Update demo docstrings (:pr:`268`)
    * Handle non-string column names (:pr:`255`)
    * Clean up merging of aggregation primitives (:pr:`250`)
    * Add tests for Entity methods (:pr:`262`)
    * Handle no child data when calculating aggregation features with multiple arguments (:pr:`264`)
    * Add `is_string` utils function (:pr:`260`)
    * Update python versions to match docker container (:pr:`261`)
    * Handle where clause when no child data (:pr:`258`)
    * No longer cache demo csvs, remove config file (:pr:`257`)
    * Avoid stacking "expanding" primitives (:pr:`238`)
    * Use randomly generated names in retail csv (:pr:`233`)
    * Update README.md (:pr:`243`)

v0.3.0 Aug 27, 2018
===================
    * Improve performance of all feature calculations (:pr:`224`)
    * Update agg primitives to use more efficient functions (:pr:`215`)
    * Optimize metadata calculation (:pr:`229`)
    * More robust handling when no data at a cutoff time (:pr:`234`)
    * Workaround categorical merge (:pr:`231`)
    * Switch which CSV is associated with which variable (:pr:`228`)
    * Remove unused kwargs from query_by_values, filter_and_sort (:pr:`225`)
    * Remove convert_links_to_integers (:pr:`219`)
    * Add conda install instructions (:pr:`223`, :pr:`227`)
    * Add example of using Dask to parallelize to docs  (:pr:`221`)

v0.2.2 Aug 20, 2018
===================
    * Remove unnecessary check no related instances call and refactor (:pr:`209`)
    * Improve memory usage through support for pandas categorical types (:pr:`196`)
    * Bump minimum pandas version from 0.20.3 to 0.23.0 (:pr:`216`)
    * Better parallel memory warnings (:pr:`208`, :pr:`214`)
    * Update demo datasets (:pr:`187`, :pr:`201`, :pr:`207`)
    * Make primitive lookup case insensitive  (:pr:`213`)
    * Use capital name (:pr:`211`)
    * Set class name for Min (:pr:`206`)
    * Remove ``variable_types`` from normalize entity (:pr:`205`)
    * Handle parquet serialization with last time index (:pr:`204`)
    * Reset index of cutoff times in calculate feature matrix (:pr:`198`)
    * Check argument types for .normalize_entity (:pr:`195`)
    * Type checking ignore entities.  (:pr:`193`)

v0.2.1 Jul 2, 2018
==================
    * Cpu count fix (:pr:`176`)
    * Update flight (:pr:`175`)
    * Move feature matrix calculation helper functions to separate file (:pr:`177`)

v0.2.0 Jun 22, 2018
===================
    * Multiprocessing (:pr:`170`)
    * Handle unicode encoding in repr throughout Featuretools (:pr:`161`)
    * Clean up EntitySet class (:pr:`145`)
    * Add support for building and uploading conda package (:pr:`167`)
    * Parquet serialization (:pr:`152`)
    * Remove variable stats (:pr:`171`)
    * Make sure index variable comes first (:pr:`168`)
    * No last time index update on normalize (:pr:`169`)
    * Remove list of times as on option for `cutoff_time` in `calculate_feature_matrix` (:pr:`165`)
    * Config does error checking to see if it can write to disk (:pr:`162`)


v0.1.21 May 30, 2018
====================
    * Support Pandas 0.23.0 (:pr:`153`, :pr:`154`, :pr:`155`, :pr:`159`)
    * No EntitySet required in loading/saving features (:pr:`141`)
    * Use s3 demo csv with better column names (:pr:`139`)
    * more reasonable start parameter (:pr:`149`)
    * add issue template (:pr:`133`)
    * Improve tests (:pr:`136`, :pr:`137`, :pr:`144`, :pr:`147`)
    * Remove unused functions (:pr:`140`, :pr:`143`, :pr:`146`)
    * Update documentation after recent changes / removals (:pr:`157`)
    * Rename demo retail csv file (:pr:`148`)
    * Add names for binary (:pr:`142`)
    * EntitySet repr to use get_name rather than id (:pr:`134`)
    * Ensure config dir is writable (:pr:`135`)

v0.1.20 Apr 13, 2018
====================
    * Primitives as strings in DFS parameters (:pr:`129`)
    * Integer time index bugfixes (:pr:`128`)
    * Add make_temporal_cutoffs utility function (:pr:`126`)
    * Show all entities, switch shape display to row/col (:pr:`124`)
    * Improved chunking when calculating feature matrices  (:pr:`121`)
    * fixed num characters nan fix (:pr:`118`)
    * modify ignore_variables docstring (:pr:`117`)

v0.1.19 Mar 21, 2018
====================
    * More descriptive DFS progress bar (:pr:`69`)
    * Convert text variable to string before NumWords (:pr:`106`)
    * EntitySet.concat() reindexes relationships (:pr:`96`)
    * Keep non-feature columns when encoding feature matrix (:pr:`111`)
    * Uses full entity update for dependencies of uses_full_entity features (:pr:`110`)
    * Update column names in retail demo (:pr:`104`)
    * Handle Transform features that need access to all values of entity (:pr:`91`)

v0.1.18 Feb 27, 2018
====================
    * fixes related instances bug (:pr:`97`)
    * Adding non-feature columns to calculated feature matrix (:pr:`78`)
    * Relax numpy version req (:pr:`82`)
    * Remove `entity_from_csv`, tests, and lint (:pr:`71`)

v0.1.17 Jan 18, 2018
====================
    * LatLong type (:pr:`57`)
    * Last time index fixes (:pr:`70`)
    * Make median agg primitives ignore nans by default (:pr:`61`)
    * Remove Python 3.4 support (:pr:`64`)
    * Change `normalize_entity` to update `secondary_time_index` (:pr:`59`)
    * Unpin requirements (:pr:`53`)
    * associative -> commutative (:pr:`56`)
    * Add Words and Chars primitives (:pr:`51`)

v0.1.16 Dec 19, 2017
====================
    * fix EntitySet.combine_variables and standardize encode_features (:pr:`47`)
    * Python 3 compatibility (:pr:`16`)

v0.1.15 Dec 18, 2017
====================
    * Fix variable type in demo data (:pr:`37`)
    * Custom primitive kwarg fix (:pr:`38`)
    * Changed order and text of arguments in make_trans_primitive docstring (:pr:`42`)

v0.1.14 Nov 20, 2017
====================
    * Last time index (:pr:`33`)
    * Update Scipy version to 1.0.0 (:pr:`31`)


v0.1.13 Nov 1, 2017
===================
    * Add MANIFEST.in (:pr:`26`)

v0.1.11 Oct 31, 2017
====================
    * Package linting (:pr:`7`)
    * Custom primitive creation functions (:pr:`13`)
    * Split requirements to separate files and pin to latest versions (:pr:`15`)
    * Select low information features (:pr:`18`)
    * Fix docs typos (:pr:`19`)
    * Fixed Diff primitive for rare nan case (:pr:`21`)
    * added some mising doc strings (:pr:`23`)
    * Trend fix (:pr:`22`)
    * Remove as_dir=False option from EntitySet.to_pickle() (:pr:`20`)
    * Entity Normalization Preserves Types of Copy & Additional Variables (:pr:`25`)

v0.1.10 Oct 12, 2017
====================
    * NumTrue primitive added and docstring of other primitives updated (:pr:`11`)
    * fixed hash issue with same base features (:pr:`8`)
    * Head fix (:pr:`9`)
    * Fix training window (:pr:`10`)
    * Add associative attribute to primitives (:pr:`3`)
    * Add status badges, fix license in setup.py (:pr:`1`)
    * fixed head printout and flight demo index (:pr:`2`)

v0.1.9 Sep 8, 2017
==================
    * Documentation improvements
    * New ``featuretools.demo.load_mock_customer`` function

v0.1.8 Sep 1, 2017
==================
    * Bug fixes
    * Added ``Percentile`` transform primitive

v0.1.7 Aug 17, 2017
===================
    * Performance improvements for approximate in ``calculate_feature_matrix`` and ``dfs``
    * Added ``Week`` transform primitive

v0.1.6 Jul 26, 2017
===================
    * Added ``load_features`` and ``save_features`` to persist and reload features
    * Added save_progress argument to ``calculate_feature_matrix``
    * Added approximate parameter to ``calculate_feature_matrix`` and ``dfs``
    * Added ``load_flight`` to ft.demo

v0.1.5 Jul 11, 2017
===================
    * Windows support

v0.1.3 Jul 10, 2017
===================
    * Renamed feature submodule to primitives
    * Renamed prediction_entity arguments to target_entity
    * Added training_window parameter to ``calculate_feature_matrix``

v0.1.2 Jul 3rd, 2017
====================
    * Initial release

.. command
.. git log --pretty=oneline --abbrev-commit
