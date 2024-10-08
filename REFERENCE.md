# Reference

<!-- DO NOT EDIT: This document was generated by Puppet Strings -->

## Table of Contents

### Classes

* [`augeas`](#augeas): Class: augeas  Install and configure Augeas  Parameters:   ['lens_dir']     - the lens directory to use   ['purge']        - whether to purge
* [`augeas::files`](#augeas--files): Class: augeas::files  Sets up directories and files for Augeas

### Defined types

* [`augeas::lens`](#augeas--lens): Definition: augeas::lens  Deploy an Augeas lens (and its test file). Check the lens (and run the unit tests) automatically and remove the fil

### Functions

* [`augeas`](#augeas): Modifies a string using Augeas.
* [`augeas::lens_dir`](#augeas--lens_dir): function to return augeas lens directory

## Classes

### <a name="augeas"></a>`augeas`

Class: augeas

Install and configure Augeas

Parameters:
  ['lens_dir']     - the lens directory to use
  ['purge']        - whether to purge lens directories

#### Parameters

The following parameters are available in the `augeas` class:

* [`aio_lens_dir`](#-augeas--aio_lens_dir)
* [`system_lens_dir`](#-augeas--system_lens_dir)
* [`files_owner`](#-augeas--files_owner)
* [`files_group`](#-augeas--files_group)
* [`lens_dir`](#-augeas--lens_dir)
* [`purge`](#-augeas--purge)

##### <a name="-augeas--aio_lens_dir"></a>`aio_lens_dir`

Data type: `Stdlib::Absolutepath`



##### <a name="-augeas--system_lens_dir"></a>`system_lens_dir`

Data type: `Stdlib::Absolutepath`



##### <a name="-augeas--files_owner"></a>`files_owner`

Data type: `String`



Default value: `'root'`

##### <a name="-augeas--files_group"></a>`files_group`

Data type: `String`



Default value: `'root'`

##### <a name="-augeas--lens_dir"></a>`lens_dir`

Data type: `Optional[Stdlib::Absolutepath]`



Default value: `undef`

##### <a name="-augeas--purge"></a>`purge`

Data type: `Boolean`



Default value: `true`

### <a name="augeas--files"></a>`augeas::files`

Class: augeas::files

Sets up directories and files for Augeas

## Defined types

### <a name="augeas--lens"></a>`augeas::lens`

Definition: augeas::lens

Deploy an Augeas lens (and its test file).
Check the lens (and run the unit tests) automatically and remove the files if
the checks fail.

Parameters:
  ['ensure']       - present/absent
  ['lens_content'] - the content of the lens
  ['lens_source']  - the source for the lens
  ['test_content'] - optionally, the content of the test
  ['test_source']  - optionally, the source for the test file.
  ['stock_since']  - optionally, indicate in which version of Augeas
                     the lens became stock, so it will not be deployed
                     above that version.

Example usage:

  augeas::lens { 'networkmanager':
    lens_content => file('networkmanager/lenses/networkmanager.aug'),
    test_content => file('networkmanager/lenses/test_networkmanager.aug'),
    stock_since  => '1.0.0',
  }

#### Parameters

The following parameters are available in the `augeas::lens` defined type:

* [`ensure`](#-augeas--lens--ensure)
* [`lens_content`](#-augeas--lens--lens_content)
* [`lens_source`](#-augeas--lens--lens_source)
* [`test_content`](#-augeas--lens--test_content)
* [`test_source`](#-augeas--lens--test_source)
* [`stock_since`](#-augeas--lens--stock_since)

##### <a name="-augeas--lens--ensure"></a>`ensure`

Data type: `Any`



Default value: `present`

##### <a name="-augeas--lens--lens_content"></a>`lens_content`

Data type: `Any`



Default value: `undef`

##### <a name="-augeas--lens--lens_source"></a>`lens_source`

Data type: `Any`



Default value: `undef`

##### <a name="-augeas--lens--test_content"></a>`test_content`

Data type: `Any`



Default value: `undef`

##### <a name="-augeas--lens--test_source"></a>`test_source`

Data type: `Any`



Default value: `undef`

##### <a name="-augeas--lens--stock_since"></a>`stock_since`

Data type: `Any`



Default value: `false`

## Functions

### <a name="augeas"></a>`augeas`

Type: Ruby 4.x API

*Example:*

   augeas("proc        /proc   proc    nodev,noexec,nosuid     0       0
", 'Fstab.lns', ['rm ./1/opt[3]'])

Would result in:

   "proc        /proc   proc    nodev,noexec     0       0
"

#### `augeas(String $content, String $lens, Array[String] $changes)`

*Example:*

   augeas("proc        /proc   proc    nodev,noexec,nosuid     0       0
", 'Fstab.lns', ['rm ./1/opt[3]'])

Would result in:

   "proc        /proc   proc    nodev,noexec     0       0
"

Returns: `String` The resulting string.

##### `content`

Data type: `String`

The string to modify.

##### `lens`

Data type: `String`

The lens to use for parsing.

##### `changes`

Data type: `Array[String]`

An array of changes to apply to the string.

### <a name="augeas--lens_dir"></a>`augeas::lens_dir`

Type: Puppet Language

function to return augeas lens directory

#### `augeas::lens_dir()`

The augeas::lens_dir function.

Returns: `String`

