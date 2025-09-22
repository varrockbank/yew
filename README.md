# Yew

This project addresses the ~~problem~~ problems of personal knowledge management (PKM). Yew avoids the complexity of PKM systems by not attempting to solve
the worlds' problems. 

Yew is not even a system; it's a 
method. Yew involves a set of guidelines/conventions on structuring directories and plaintext files. 
Most functionality will come free from the Unix bin. Spoiler: Yew lends itself naturally to people who have a Git repo for
each project in their life. 

### Problem 

PKM systems attempt to assimilate and monopolize one's entire digital footprint.

The first dimension of complexification is that these systems treat PKM as a monolith that can be tamed,
cross-cutting across disparate projects.

The second dimension of complexification is attempting to accommodate every client and their use case.
By making everyone happy, PKMs make no one happy. Even adherents find themselves 
bikeshedding and chasing the long-tail of productivity.

Fortunately with Yew I just need to make myself happy. 

### Solution
Yew federates knowledge management to individual projects and their 
respective file directories. In doing so projects are self-contained.

This is not exotic to coders who automatically instantiate a Git repo for each
"project" in their life. 

This project-oriented paradigm is exceedingly powerful. 

A strict boundary is enforced 
between private, professional and academic projects. Why on earth would you want to
hyperlink between your vacation and a college course anyway? Monoliths  
punishes heterogeny, while federation promote internal consistency (projects are smaller). 
Yew is minimally prescriptive leaving more discretion to individual projects. After all,
a video game project and an English writing course involve different workflows and should be 
accommodated differently. 

Yew couples KPM to the project. PKM files are co-located within a project directory,
rather than being standalone entities. i.e. Wiki or an exclusive set of PKM
files for use with some proprietary note-taking app. In a way, Yew can be thought
of a generalization of `README.md`. 

Yew embraces Unix ethos. Meaning delegating implementation to 
readily available toolchains and interop. The Yew Project is a specification 
first-and-foremost and any "extracurricular" implementations follow thereafter.

see `journal/manifesto.md` for background context and in-depth commentary
on underlying philosophy. 

###  Survey 

The Yew Project identified various modalities which involve
different flow states which should be partioned into different spaces.  

1. space: diary

   - workflow: log

     - flow state: stream of thought of day-to-day
     - data structure: append-only list of logs, one log file per day.
           This list is chronological. 

   - workflow: recap
   
     - flow state: reflecting on diary entries over some time period  
     - data structure: a summary document 

2. workflow: scratchpads

   - flow state: need to dump ephemeral down before forgetting
   - data structure: a cache

4. space: journal

    - workflow: R&D  
      - flow state: information gathering and organizing
      - data structure: a folder of documents and resources 
    - workflow: learning 
      - flow state: distilling and explaining of a topic. The audience
        can be for the future version of yourself.

5. space: lists
   - flow state: shopping lists, TODO lists
   - data structure: mutable lists 

6. space: blog
   - flow state: publishing finalized documents from journal 
   - data structure: editable set of documents

## Legal

No support is provided. The author bears no responsibility for this system's usage. 
Don't plagiarize without citation.

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
Versions should not "re-index", reusing old label indexes when removing obsolete indexes.
This should be finalized between alpha and production versions.

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

### § alpha.1 Diary Space

Directory `diary` is reserved for the Diary space. 
This space is for chronological entry with the granularity is on a 
day-to-day basis. An entry file should correspond to a specific day.

Users can modify an entry file as much as they want on a given day but 
should avoid modifying an entry file once the day is over. 

### § alpha.1.1 format

`md` extension and markdown is used for log files.  Files without `md` extensions are ignored.

#### § alpha.1.2 entry file validation 

Files with `md` extension are assumed to be valid Markdown, without validation.

#### § alpha.1.3 directory structure and file pattern

Every file should be named `YYYY_MM_DD.md` where `YYYY`is the year, `MM` is the month, `DD` is the day.

This file should be placed in the following directory: `diary/YYYY/MM`. i.e. `diary/2025/09/2025_09_21.md`

```
diary/
   2025/
      09/
        2025_09_21.md
```

### § alpha.1.4

Files that do not match the pattern `diary/YYYY/MM/DD/YYYY_MM_DD.md` are to be ignored by Yew implementations. 
i.e. `diary/2025/1/31` and `diary/2025/12/1`.

### § alpha.1.5 Dates 

YYYY/MM/DD are not checked the be valid days. For example: 02/29 would be a valid date on a leap year but
invalid on a regular year. Yew does not validate 2025/02/29 to be a valid date.

In the future, Yew will validate the date.

### § alpha.1.8 monthly `recap.md`

Each `YYYY/MM` directory should have`recap.md` file. 
Around the near the end of the month, the user should populate
such a file if one does not exist already.

Yew implementations should remind and encourage users to populate this file.

Users can update the recap file throughout the month, but 
make sure that it is finalized around the end of the month. 

### § alpha.1.9 Weekly recaps 

If user wants to have recaps weekly or other time periods, they can 
create "indexed" recap files: `recap_1.md`, `recap_2.md` and so on and so forth.

It is up to the user to decide when these time periods start and end.
It is up to the user's discretion when to create additional periodic 
recaps. For me, I intend on creating a recap file at the end of the weekend. 

The indexing does not need to start from 1. Suppose this is the 3rd week of the 
month. Then the user can specify `recap_3.md`.

The indexing also does not need to be `1`, `2`, `3`. The goal is that these 
index values are "lexicographically ordered". `week1`, `week2`, `week3` would also work.


### § alpha.2 Media, pictures and non .MD files 

Currently unsupported and ignored. Perhaps when we want to have a collection of files on a given
day, we will reintroduce the `YYYY/MM/DD/` archive path.

### § alpha.3 Yew Project

A directory which follows the specification is a valid Yew Project.

It is generally recommended that the Yew Project be at the root level 
of a project, co-existing with any code in that directory. 

In instances where reserved Yew directories conflict, such as coding project that 
has the directory `journal`, one can push the Yew directory down into a directory named
`yew` to avoid this conflict. Obviously, this directory name can be anything and if `yew` also
conflicts then the user can specify any other available directory name.

Other techniques such as a metadata file, i.e. `remapping.json`, could be fed to the Yew toolchain 
to deal with conflicts and allow arbitrary naming of the various spaces. However, we avoid 
this overengineed solution.

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

#### § alpha.6 `fridgenote.md`

In a multi-user setting, `fridgenote.md` can be used to leave notes 
behind for other developers like a sticky note on the refrigerator.

#### § alpha.7 Journal Space

A `journal` directory is a space for distilled and collected thoughts. 
This does not preclude drafts. In fact, the `journal` space is 
where `drafts` and `finalized` documents are authored being published.

Users can use arbitrary directories and documents.

#### alpha.7.1 `scratchpad.md`, `clipboard.md`

It is recommended that `journal/scratchpad.md` be reserved to jot down 
ideas. As such, it is recommended that this file is `gitignore`d.

`journal/clipboard.md` is the same idea but for copy and pastes.

#### § alpha.7.2 journal versioning

Drafts should be suffixed `.draft.md`
Finalized versions should be suffixed `.final.md`

#### § alpha.7.3 Authoring Date

This should be in the file as a header or metadata (TBD)



