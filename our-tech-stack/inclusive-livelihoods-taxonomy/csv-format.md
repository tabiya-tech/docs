---
description: >-
  The tabiya CSV format is used to import and export data from the Tabiya Open
  Taxonomy platform.
---

# Taxonomy CSV Format

Each taxonomy version is made up of nine CSV files Each file contains a different type of data. The files are:

* [Model Info](csv-format.md#model-info)
* [Skill Groups](csv-format.md#skill-groups)
* [Skills](csv-format.md#skills)
* [Skill Hierarchy](csv-format.md#skill-hierarchy)
* [Skill to Skill Relations](csv-format.md#skill-to-skill-relations)
* [Occupation Groups](csv-format.md#occupation-groups)
* [Occupations](csv-format.md#occupations)
* [Occupation Hierarchy](csv-format.md#occupation-hierarchy)
* [Occupation to Skill Relations](csv-format.md#occupation-to-skill-relations)
* [LICENSE](csv-format.md#LICENSE)

## General notes on the fields of the CSV files

### UUID History

A `UUIDHISTORY` field is a [list](csv-format.md#lists) of all the UUIDs that have been assigned to an entity during its lifecycle, e.g. when the entity is created, imported, exported or copied into our platform.

It is an identifier that can be used for tracking objects not only across their lifecycle, but also across systems.

The UUID history is ordered from newest to oldest UUID.

The first entry in the list is the current UUID of the object.\
The last entry in the list is the very first (_initial_) UUID of the object.

The entities in this dataset have been assigned an initial UUID. When an entity is imported into our platform, a new UUID will be issued and added at the top of UUID history.

The UUID used by the platform are based on the [Universally Unique Identifier v4](https://datatracker.ietf.org/doc/html/rfc4122) standard.

> The maximum number of UUIDs in the history for an object is constrained to `10000`.

### Origin Uri

The `ORIGINURI` field is a [URI](https://datatracker.ietf.org/doc/html/rfc3986) that points to the location where an entity was originally defined.

> The maximum length for the Origin Uri is `4096` characters.

### ID

The `ID` field is a unique identifier for each entity in the CSV dataset. It is used for referencing within the CSV dataset, for example, in the relations between entities.

This field is not meant to be used as an identifier outside the scope of the CSV files, for that purpose you should use the first entry in the [UUID History](csv-format.md#uuid-history).

### Object Types

The object types are used to differentiate between different types of entities in the dataset.

For example in relations between entities, the object types are used to specify the type of the parent and child objects and determine in which file these objects can be located.

The object types in the CSV files are:

* `skill`: Represents a [skill](csv-format.md#skills).
* `skillgroup`: Represents a [skill group](csv-format.md#skill-groups).
* `escooccupation`: Represents an [occupation](csv-format.md#occupations) that originates from the ESCO framework.
* `localoccupation`: Represents an [occupation](csv-format.md#occupations) that not originate from the ESCO framework and is defined only this taxonomy.
* `occupationgroup`: Represents an [Occupation group](csv-format.md#occupation-groups).

### Lists

List properties are stored in the CSV files as strings separated by a  character. Currently, we do not support values that contain a new line.

### Dates

The dates in the CSV files are stored in the [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format.

## File descriptions

### Model Info

Contains information about the model. The export filename is `model_info.csv`

#### Columns

* [`UUIDHISTORY`](csv-format.md#uuid-history): A list of [UUIDs](csv-format.md#uuid-history).
* `NAME`: The name of the model.
* `LOCALE`: The short code of the model's locale.
* `DESCRIPTION`: The description of the model.
* `VERSION`: The version of the model.
* `RELEASED`: A boolean value that indicates whether the model is released or not.
* `RELEASENOTES`: The release notes of the model.
* `CREATEDAT`: The [date](csv-format.md#dates) the model was created.
* `UPDATEDAT`: The [date](csv-format.md#dates) the model was last updated.

### Skills

Contains the skills of the taxonomy. The export filename is `skills.csv`

#### Columns

* [`ORIGINURI`](csv-format.md#origin-uri): A [URI](csv-format.md#origin-uri) that points to the location where the skill was originally defined.
* [`ID`](csv-format.md#id): A [unique identifier](csv-format.md#id), used for referencing the skill within the CSV dataset.
* [`UUIDHISTORY`](csv-format.md#uuid-history): A list of [UUIDs](csv-format.md#uuid-history).
* `SKILLTYPE`: The skill type.
  * Possible values: `skill/competence`,`knowledge`,`language`,`attitude` or empty ( ).
* `REUSELEVEL`: The skill reuse level.
  * Possible values: `sector-specific`,`occupation-specific`,`cross-sector`,`transversal` or empty ( ).
* `PREFERREDLABEL`: The preferred label of the skill.
* `ALTLABELS`: A [list](csv-format.md#lists) of alternative labels for the skill.
  * Maximum length per label: `256` characters.
  * Maximum number of labels: `100`.
* `DESCRIPTION`: The skill description.
  * Maximum length:`4000` characters.
* `DEFINITION`: The skill definition.
  * Maximum length:`4000` characters.
* `SCOPENOTE`: The skill scope note.
  * Maximum length:`4000` characters.
* `ISLOCALIZED`: A boolean value that indicates whether the skill is localized or not.
  * Possible values: `true` or `false`.
* `CREATEDAT`: The [date](csv-format.md#dates) the skill was created.
* `UPDATEDAT`: The [date](csv-format.md#dates) the skill was last updated.\\

### Skill Groups

Contains the skill groups of the taxonomy. The export filename is `skill_groups.csv`

#### Columns

* [`ORIGINURI`](csv-format.md#origin-uri): A [URI](csv-format.md#origin-uri) that points to the location where the skill group was originally defined.
* [`ID`](csv-format.md#id): A [unique identifier](csv-format.md#id), used for referencing the skill group within the CSV dataset.
* [`UUIDHISTORY`](csv-format.md#uuid-history): A list of [UUIDs](csv-format.md#uuid-history).
* `CODE`: SkillGroup code as defined in ESCO. It has the general format `SX.X.X`, where `X` is a number.
* `PREFERREDLABEL`: The preferred label of the skill group.
* `ALTLABELS`: A [list](csv-format.md#lists) of alternative labels for the skill group.
  * Maximum length per label: `256` characters.
  * Maximum number of labels: `100`.
* `DESCRIPTION`: The skill group description.
  * Maximum length:`4000` characters.
* `SCOPENOTE`: The skill group scope note.
  * Maximum length:`4000` characters.
* `CREATEDAT`: The [date](csv-format.md#dates) the skill group was created.
* `UPDATEDAT`: The [date](csv-format.md#dates) the skill group was last updated.

### Occupations

Contains the occupations of the taxonomy. The export filename is `occupations.csv`

#### Columns

* [`ORIGINURI`](csv-format.md#origin-uri): A [URI](csv-format.md#origin-uri) that points to the location where the occupation was originally defined.
* [`ID`](csv-format.md#id): A [unique identifier](csv-format.md#id), used for referencing the occupation within the CSV dataset.
* [`UUIDHISTORY`](csv-format.md#uuid-history): A list of [UUIDs](csv-format.md#uuid-history).
* `OCCUPATIONGROUPCODE`:The Occupation group that the occupation belongs to.
* `CODE`: An occupation code assigned to the occupation.
  * For ESCO occupations, the code will be the parent code, followed by a `.` and any number of digits. Eg: `XXXX.1234`
  * For local occupations, the code will be the parent code, followed by an `_` and any number of digits. `XXXX_1234`
* `PREFERREDLABEL`: The preferred label of the occupation.
* `ALTLABELS`: A [list](csv-format.md#lists) of alternative labels for the occupation.
  * Maximum length per label: `256` characters.
  * Maximum number of labels: `100`.
* `DESCRIPTION`: The occupation description.
  * Maximum length:`4000` characters.
* `DEFINITION`: The occupation definition.
  * Maximum length:`4000` characters.
* `SCOPENOTE`: The occupation scope note.
  * Maximum length:`4000` characters.
* `REGULATEDPROFESSIONNOTE`: The regulated profession note.
  * Maximum length:`4000` characters.
* `OCCUPATIONTYPE`: The type of the occupation.
  * Possible values: `escooccupation` or `localoccupation`.
* `ISLOCALIZED`: A boolean value that indicates whether the occupation is localized or not. Only ocuppations of the type `escooccupation` can be localized.
  * Possible values: `true` or `false`.
* `CREATEDAT`: The [date](csv-format.md#dates) the occupation was created.
* `UPDATEDAT`: The [date](csv-format.md#dates) the occupation was last updated.

### Occupation Groups

Contains the Occupation groups of the taxonomy. The export filename is `occupation_groups.csv`

### Columns

* [`ORIGINURI`](csv-format.md#origin-uri): A [URI](csv-format.md#origin-uri) that points to the location where the Occupation group was originally defined.
* [`ID`](csv-format.md#id): A [unique identifier](csv-format.md#id), used for referencing the Occupation group within the CSV dataset.
* [`UUIDHISTORY`](csv-format.md#uuid-history): A list of [UUIDs](csv-format.md#uuid-history).
* `CODE`: A four digit identification code of the Occupation group. Each digit represents a level in the hierarchy.
  * For ISCO groups, the code is a maximum of 4 digits, and each child group should have a code that begins with the parent group code. Eg: `1234`
  * For local groups without a parent group, the code should start with an alphabetical character. Eg: `A1234`
  * For local groups, if the parent occupation group is an isco group, the code should start with the parent group code and then have one alphabetical character. Eg: `1234A`
  * For local groups, if the parent occupation group is also a local group, the code should start with the parent group code and then have either an alphabetical character or a number. Eg: `1234AB` or `1234A1`
* `GROUPTYPE`: The type of the Occupation group.
  * Possible values: `iscogroup` or `localgroup`.
* `PREFERREDLABEL`: The preferred label of the Occupation group.
* `ALTLABELS`: A [list](csv-format.md#lists) of alternative labels for the Occupation group.
  * Maximum length per label: `256` characters.
  * Maximum number of labels: `100`.
* `DESCRIPTION`: The Occupation group description.
  * Maximum length:`4000` characters.
* `CREATEDAT`: The [date](csv-format.md#dates) the Occupation group was created.
* `UPDATEDAT`: The [date](csv-format.md#dates) the Occupation group was last updated.

### Skill-to-Skill Relations

Contains the relations between skills. The export filename is `skill_to_skill_relations.csv`

#### Columns

* `REQUIRINGID`: The [`ID`](csv-format.md#id) of the skill that requires another skill.
* `RELATIONTYPE`: The type of the relation.
  * Possible values: `essential` or `optional`.
* `REQUIREDID`: The [`ID`](csv-format.md#id) of the skill that is required by another skill.
* `CREATEDAT`: The [date](csv-format.md#dates) the relation was created.
* `UPDATEDAT`: The [date](csv-format.md#dates) the relation was last updated.

### Occupation-to-Skill Relations

Contains the relations between occupations and skills. The export filename is `occupation_to_skill_relations.csv`

#### Columns

* `OCCUPATIONTYPE`: The type of the occupation.
  * Possible values: `escooccupation` or `localoccupation`.
* `OCCUPATIONID`: The [`ID`](csv-format.md#id) of the occupation.
* `RELATIONTYPE`: The type of the relation.
  * Possible values: `essential`, `optional`, or it can be left empty.
* `SIGNALLINGVALUELABEL`: The signalling value label of the relation.
  * Possible values: `low`, `medium`, `high`, or it can be left empty.
* `SIGNALLINGVALUE`: The signalling value of the relation.
  * A number between `0` and `1`, or it can be left empty. The only allowed delimiter for decimal numbers is a `.`.
* `SKILLID`: The [`ID`](csv-format.md#id) of the skill.
* `CREATEDAT`: The [date](csv-format.md#dates) the relation was created.
* `UPDATEDAT`: The [date](csv-format.md#dates) the relation was last updated.

> Caveat: An escooccuption cannot have a `signalling value` or `signalling value label`. It **must** have a `relationType`.\
> For localoccupations `signalling value` and `relationType` are mutually exclusive. A `localoccupation` can **either** have a `signalling value` and `signalling value label` **or** it can have a `relationType`, but not both.

### Skill Hierarchy

Contains the hierarchical structure of various skills. The export filename is `skill_hierarchy.csv`

#### Columns

* `PARENTOBJECTTYPE`: The type of the parent object.
  * Possible values: `skill` or `skillgroup`.
* `PARENTID`: The [`ID`](csv-format.md#id) of the parent object.
* `CHILDID`: The [`ID`](csv-format.md#id) of the child object.
* `CHILDOBJECTTYPE`: The type of the child object.
  * Possible values: `skill` or `skillgroup`.
* `CREATEDAT`: The [date](csv-format.md#dates) the relation was created.
* `UPDATEDAT`: The [date](csv-format.md#dates) the relation was last updated.

> Caveat: A skill cannot be the parent of a skill group.

### Occupation Hierarchy

Contains the hierarchical structure of various occupations. The export filename is `occupation_hierarchy.csv`

#### Columns

* `PARENTOBJECTTYPE`: The type of the parent object.
  * Possible values: `occupationgroup`, `escooccupation`, `localoccupation`.
* `PARENTID`: The [`ID`](csv-format.md#id) of the parent object.
* `CHILDID`: The [`ID`](csv-format.md#id) of the child object.
* `CHILDOBJECTTYPE`: The type of the child object.
  * Possible values: `occupationgroup`, `escooccupation`, `localoccupation`.
* `CREATEDAT`: The [date](csv-format.md#dates) the relation was created.
* `UPDATEDAT`: The [date](csv-format.md#dates) the relation was last updated.

> Caveat: An `escooccupation` cannot be the parent of an 'occupationgroup'.\
> Caveat: An `localoccupation` can be a child of an `escooccupation` or another `localoccupation`.

### LICENSE

Contains the license information for the model. If one wants to add a license to the dataset, it can be added to a file named `LICENSE` in the root of the dataset.\
The `LICENSE` file supports plain text and Markdown format. During export the license information of the model will also be exported in the `LICENSE` file.
