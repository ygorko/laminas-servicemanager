# Changelog

All notable changes to this project will be documented in this file, in reverse chronological order by release.

## 2.7.2 - 2016-01-11

### Added

- [#63](https://github.com/zendframework/zend-servicemanager/pull/63) adds a
  constructor to `InvokableFactory`. In v2, this allows plugin managers to pass
  construction options to the factory to use during instantiation of the
  requested service class, emulating the behavior of `build()` in v3.

### Deprecated

- Nothing.

### Removed

- Nothing.

### Fixed

- Nothing.

## 2.7.1 - 2016-01-11

### Added

- [#61](https://github.com/zendframework/zend-servicemanager/pull/61) adds
  `Zend\ServiceManager\Exception\InvalidServiceException` for forwards
  compatibility with v3.

### Deprecated

- Nothing.

### Removed

- Nothing.

### Fixed

- [#61](https://github.com/zendframework/zend-servicemanager/pull/61) updates
  the `InvokableFactory` to throw `InvalidServiceException` instead of
  `InvalidServiceNameException`, for forwards compatibility with v3.
- [#61](https://github.com/zendframework/zend-servicemanager/pull/61) fixes
  the behavior of `InvokableFactory` when invoked after resolving an alias.

## 2.7.0 - 2016-01-11

### Added

- [#60](https://github.com/zendframework/zend-servicemanager/pull/60) adds
  forward compatibility features for `AbstractPluingManager` and introduces
  `InvokableFactory` to help forward migration to version 3.

### Deprecated

- Nothing.

### Removed

- Nothing.

### Fixed

- [#46](https://github.com/zendframework/zend-servicemanager/pull/46) updates
  the exception hierarchy to inherit from the container-interop exceptions.
  This ensures that all exceptions thrown by the component follow the
  recommendations of that project.
- [#52](https://github.com/zendframework/zend-servicemanager/pull/52) fixes
  the exception message thrown by `ServiceManager::setFactory()` to remove
  references to abstract factories.

## 2.6.0 - 2015-07-23

### Added

- [#4](https://github.com/zendframework/zend-servicemanager/pull/4) updates the
    `ServiceManager` to [implement the container-interop interface](https://github.com/container-interop/container-interop),
    allowing interoperability with applications that consume that interface.

### Deprecated

- Nothing.

### Removed

- Nothing.

### Fixed

- [#3](https://github.com/zendframework/zend-servicemanager/pull/3) properly updates the
  codebase to PHP 5.5, by taking advantage of the default closure binding
  (`$this` in a closure is the invoking object when created within a method). It
  also removes several `@requires PHP 5.4.0` annotations.