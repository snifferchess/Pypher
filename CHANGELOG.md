# Pypher Changelog


## 0.10.0 -- 5/12/2018

### Added

* `Relationship` now accept `min_hops` and `max_hops` arguments that will resolve to a pattern.


## 0.9.2 -- 5/9/2018

### Bugfix

* Ensured that `MapProjection` could have a `name` kwarg
* Modified `List` to use a comma as the concatenator instead of a blank space


## 0.9.0.1 -- 5/5/2018

### Hotfix

* Ensured ordering of params for dict assignments


## 0.9.0 -- 5/5/2018

### Added

* `ctrl-c` shortcut to clear the Pypher pane in the tester.py console
* `func_raw=False` argument to the `Pypher.builder.crete_function` method that will create a `FuncRaw` class instead of a `Func` when set to true.

## 0.8.0 -- 4/28/2018

### Added

* Added a few missing statements; `XOR`, `NULL`, `IS_NULL`, `IS_NOT_NULL`, `NOT`, and `OR`

### Fixed

* A bug where dynamic statements were printing out `STATEMENT`. Now `p.some_statemnt(1, 2, 3)` will return `some_statement 1, 2, 3`
* Ensured ordering of `kwargs` in `Map` and `MapProjection` objects


## 0.7.0 -- 4/26/2018

### Added

* Map and map projection support via `Map` and `MapProjection` respectively.
* Dict support for assignments
* Very alpha CLI app used to test Pypher scripts. Simply run `python tester.py` after installing this package.


## 0.6.0 -- 4/13/2018

### Added

* `Entity` objects now accept a `Label` instance for the `labels` or `types` argument.
* `Relationship` objects now accept a `types` kwarg that will supercede the `labels` definition.

### Fixed

* `Property` objects' alias `prop` now work as expected.
* Fixed a few bugs regarding `Param.name` and `Pypher.bound_params` keys.

## 0.5.0 -- 4/1/2018

### Added

* Added optional params argument to the `Pypher` class that will allow self-defined `Params` objects to be used instead of being created when a `Pypher` instance is created.


## 0.4.2 -- 3/15/2018

### Fixed

* Ensured that params that share the same value with previously bound params return the same reference.
* Ensured that params passed as a value only, but is the name of an existing key tha thas be bound, returns the same reference.


## 0.4.1 -- 3/14/2018

### Fixed

* Changed the `ID` class to subclass `FuncRaw` so that its arguments are not automatically bound.
* Fixed the name of the param staring with a `$`

## 0.4.0 -- 3/3/2018

### Added

* `Pypher.OperatorRaw` a class where the operator's argument is not automatically bound in the resulting Cypher.

### Bugfix

* Fixed an issue where `Pypher.reset()` was not clearing out the old bound params
* Made `Pypher.Alias` and `Pypher.Rexp` sub-class `Pypher.OperatorRaw`
* Fixed a bug where `Pypher.Link` class `_ALIAS` list were not being stored and referenced by the system properly

## 0.3.3 -- 2/25/2018

### Bugfix

* Fixed division of Pypher objects for Python 3+

### Changed

* The default param name now starts with a dollar sign. And if the manually named param does not start with one, it will be prepended to the name

## 0.3.2 -- 2/23/2018

### Bugfix

* `pypher.builder.Raw` and `pypher.builder.FuncRaw` objects will now adopt bound_params from Pypher and Partial objects

## 0.3.1 -- 2/22/2018

### Hotfix

* The `pypher.builder.Label` class did not add back ticks to the labels.

## 0.3.0 -- 2/22/2018

### Changed

* All labels and properties are now wrapped in back ticks to support labels or properties with spaces and other weird characters. From: "n.name" to "n.`name`"

## 0.2.1 -- 2/21/2018

### Fixed

* A bug where the referenced/right-side operators were not behaving correctly if the right side was not a Pypher object. `99 - p.__field__` would output `p.field - 99` it now outputs `99 - p.field`

## 0.2.0 -- 2/20/2018

### Added

* Support for Partial objects.

## 0.1.1 -- 2/17/2018

### Removed

* `pypher.builder.RElATIONSHIPS['both']` -- this relationship doesn't exist as it was defined.
