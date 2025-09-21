# Motivation

I started grad school and sought to consistently snapshot my thoughts, both 
private and intellectual. I hope to retroactively pinpoint the specific 
time frame I developed certain ideas.

Before this, I had a scattered and unstructured set of ad-hoc notes
that would in all likelihood be lost in the entropy. The only way to search
through the documents is to comprehensively look through them all. This
mess also hindered incrementally building knowledge. It was taxing on my brain's 
CPU and memory. 

Software-as-a-services come and go making the value prop of solving this problem.
The two issues I face with these services is data portability and input lag.

A knowledge management system is more than logging daily stream of thoughts in chronological order.
It should have caches, the most common of which is lists of stuff such as a todo list.

## Overarching Ideas

1. Plaintext files
2. Directory structure as a means of organization
3. Version control 
4. Metadata support for purposes of search / information retrieval 
5. Accessible from small (smartphones) and large devices (laptops) on slow internet connection
6. Yew versions aim for backward compatibility
7. Strive to be a specification rather than implementation 
8. Encourages information retrieval (search) and organization (tags) 
9. Do not chase trends or appeal to compatibility for the sake of compatibility

Yew leans towards specification, rather than implementation, on workflow conventions as to 
that interop with readily available software/toolchains, namely on Unix systems. 

Custom implementation and integration should be a backwards compatible extension.

This repository should be "self-hosting" and serve as a valid Yew Project.  

## Legal

No support is provided. The author bears no responsibility for this system's usage. 
Don't plagiarize without citation. 

## Yew 

The name takes inspiration from the tree popularized by RuneScape. 

Currently, Yew specification is not machine parseable. 
When machine-parseability is a feature, the specification will be moved into a separate file.

## Specification

### § alpha.0

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

### § alpha.1 logs

Logs are chronological. The granularity is on a day-to-day basis.
Each log file should correspond to a specific day.

Users can modify a log file as much as they want on a given day, but 
should avoid modify a log file once the day is over. 

### § alpha.1.1 log format

`md` extension and markdown is used for log files.  Files without `md` extensions are ignored.

#### § alpha.1.2 log file validation 

Files with `md` extension are assumed to be valid Markdown, without validation.

#### § alpha.1.3 directory structure and file pattern

Every file should be named `YYYY_MM_DD.md` where `YYYY`is the year, `MM` is the month, `DD` is the day.

This file should be placed in the following directory: `YYYY/MM`. i.e. `2025/09/2025_09_21.md`

The following files collectively form an instance of Yew `Archive`. 
A optional `README.md` can contain user specified commentary about the Archive

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

### § alpha.1.4

Files that do not match the pattern `YYYY/MM/DD/YYYY_MM_DD.md` are to be ignored by the Yew toolchain. 

This includes the following example: `2025/1/31` and `2025/12/1`.

### § alpha.1.5 Dates 

YYYY/MM/DD are not checked the be valid days. For example: 02/29 would be a valid date on a leap year but
invalid on a regular year. Yew does not validate 2025/02/29 to be a valid date.

In the future, Yew will validate the date. 

### § alpha.1.6 Time 

Yew does not care about time of day. 

### § alpha.1.7 

`YYYY-MM-DD.md` may be supported in the future.

### § alpha.2 Media, pictures and non .MD files 

Currently unsupported and ignored. Perhaps when we want to have a collection of files on a given
day, we will reintroduce the `YYYY/MM/DD/` archive path.

### § alpha.3 A Yew Project 

A Yew `Project` contains 1 or more named log archives and a README.md file.

```
   README.md 
   personal_diary/
      ...
   school/
      ... 
   work/
      ...
```

### § alpha.4 Version Control

Currently, this comes free because of plaintext files. 

A Yew project can contain a `.git` directory and `.gitignore` file at the root. 

### § alpha.5 lists

A special directory at a root named `lists` is reserved for arbitrary lists. 
A list is expected to be modified anachronistically.
Each list is encoded in a list file. 

#### § alpha.5.1 format of list files 

Each file with a `txt` extension form a list.

`md` based list may be supported in the future.

#### § alpha.5.2 elements

Each non-empty line in a `txt` file is an element of the list.

#### § alpha.5.2 directory pattern 

Users can use an arbitrary structure of subdirectories.
Yew recurses through the directory for all valid `list`.

#### § alpha.5.3 implementation limits 

lists
: 1000

folder depth
: 10 

Behavior beyond these limits are at the discretion of implementation.






