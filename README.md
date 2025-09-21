## Motivation

This project stem from a desire to log my personal diary and incremental knowledge development
on a day-by-day basis in a more organized manner than scattered, unstructured and ephemeral ad-hoc notes.

I sought a structured software-backed workflow to facilitate holding the belief that such an investment
will streamline and encourage a more complete set of logs.

## Overarching Ideas

1. Plaintext files
2. Directory structure as a means of organization
3. Version control 
4. Metadata support for purposes of search / information retrieval 
5. Accessible from small (smartphones) and large devices (laptops) on slow internet connection
6. Yew versions aim for backward compatibility
7. Strive to be a specification rather than implementation 

This projects strives to be a specification, rather than implementation, around a set of conventions on which
existing software toolchains can readily operate. Perhaps custom software will be needed but it connected 
as an optional extension that does not break backwards compatibility.

Yew aims to be recursively specified. This project serves as a valid Yew Project.  

## Legal

No support is provided for this system. The author bears 
no responsibility. 

## Yew 

This project is named Yew takes inspiration from the Yew tree from RuneScape. 

Currently, the alpha Yew specification is not machine parseable. When it is meant to be machine parseable,
the specification will be moved into a separate file.

## Specification

### § v1alpha.0

A Yew specification, or Yew Spec for short, defines the conventions and software interop for a given
version of Yew. A Yew Spec consists of a sequence of explanation uniquely identified by `x.*` 
where `x` is the Yew version number. 

- `x.0` is reserved to make meta commentary about Yew Specs up-to and including version `x`
- `x.0.0` is reserved for structured key-value metadata `x` including, most importantly, the version .
- `x.0.1` is reserved for version `x` to elaborate on how its explanations are labeled. 
i.e. a table of content
- In general, labels `x.0.*` are reserved for version `x` to make self-referential specifications

All other labels `x.*` are reserved and indexed at the discretion of spec version `x`.

if "x" contains the substring "alpha", x is an alpha version. Alpha versions are draft proposals 
and subject to being overwritten / mutated at any time and cannot be relied upon. 

Labels should be placed in a markdown header with optional content to the right of it. The header
should start with § for aesthetic reasons. 

### § alpha.0.0

version
: alpha

release_date
: 2025/09/21

### § alpha.0.1

- `alpha.y` labels, where y is a natural number, are for major definitions
- `alpha.y.z` labels, where z is a natural number, are correlaries of y

### § alpha.1 Format

(It is assumed that) All relevant user documents are valid markdown files with the file extension `.md`

#### § alpha.1.1

Files without `md` extensions are ignored.

#### § alpha.1.2

Files with `md` extension are assumed to be valid Markdown without validation.

### § alpha.2 Archives

Every file should be named `YYYY_MM_DD.md` where `YYYY`is the year, `MM` is the month, `DD` is the day.

This file should be placed in the following directory: `YYYY/MM`. i.e. `2025/09/2025_09_21.md`

The following files collectively form an instance of Yew `Archive`. 
`README.md` is user specified commentary about the Archive 

```
   README.md
   2025/
      09/
        2025_09_21.md
```

More precisely, the name of the parent directory is the name of the `Archive`. In the 
following example "my_first_archive"

```
   my_first_archive/
     README.md
     2025/
        09/
          2025_09_21.md
```

### § alpha.2.1

Files that do not match the pattern `YYYY/MM/DD/YYYY_MM_DD.md` are to be ignored by the Yew toolchain. 

This includes the following example: `2025/1/31` and `2025/12/1`.

### § alpha.2.2 Date 

YYYY/MM/DD are not checked the be valid days. For example: 02/29 would be a valid date on a leap year but
invalid on a regular year. Yew does not validate 2025/02/29 to be a valid date.

In the future, Yew will validate the date. 

### § alpha.2.3 Time 

Yew does not care about time of day. 

### § alpha.2.3 

`YYYY-MM-DD.md` may be supported in the future. 

### § alpha.2.4 

Metadata in README.md is ignored

### alpha.3 Media, pictures and non .MD files 

Currently unsupported and ignored. Perhaps when we want to have a collection of files on a given
day, we will reintroduce the `YYYY/MM/DD/` archive path.

### alpha.4 A Yew Project 

A Yew `Project` contains 1 or more named archives and a README.md file.

```
   README.md 
   personal_diary/
      ...
   school/
      ... 
   work/
      ...
```

### alpha.5 Version Control

A Yew project can contain a git directory and .gitignore file at the root. 


