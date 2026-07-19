# Skill: Organizing GitHub Organization Repositories with Custom Properties

## Goal

Use GitHub Custom Properties to classify repositories into logical
categories and make them easier to search and manage.

------------------------------------------------------------------------

## Key Concepts

### Repository list limitations

GitHub organizations do **not** currently support:

-   Folder hierarchies
-   Repository collections
-   Sorting by custom property
-   Grouping repositories by custom property on the Repositories page

Custom properties are intended primarily for **metadata** and
**filtering**.

------------------------------------------------------------------------

## Recommended Design

Instead of creating multiple properties such as:

-   Computational-methods
-   Data-sharing
-   Lab-resources

Create a single property:

**Property name**

`Category`

**Type**

`Single select`

**Allowed values**

-   Computational methods
-   Data sharing
-   Lab resources

Each repository receives exactly one category.

Example:

  Repository                         Category
  ---------------------------------- -----------------------
  ScapyPlus                          Computational methods
  Cellsage                           Computational methods
  Human_fetal_lung_cell_atlas_2022   Data sharing
  Peng-He-Lab.github.io              Lab resources

------------------------------------------------------------------------

## Creating Custom Properties

Organization

→ Settings

→ Custom properties

→ New property

Recommended settings:

Name:

`Category`

Type:

`Single select`

Allowed values:

-   Computational methods
-   Data sharing
-   Lab resources

------------------------------------------------------------------------

## Assigning Values

After creating the property:

Organization

→ Settings

→ Custom properties

→ Set values

Select one or more repositories and assign a Category value.

------------------------------------------------------------------------

## Searching Repositories

GitHub does **not** use:

`category:Computational methods`

Instead use:

`props.Category:"Computational methods"`

A convenient workflow is:

1.  Click the repository search box.
2.  Type:

`prop`

3.  Select the property from autocomplete.
4.  Choose the desired value.

------------------------------------------------------------------------

## Important Limitation

Repositories cannot currently be:

-   Sorted by Category
-   Displayed in grouped sections
-   Browsed as folders

Only filtering is supported.

------------------------------------------------------------------------

## Possible Future Enhancement

If a richer browsing experience is desired:

-   Use GitHub Actions.
-   Read repository metadata and Category values through the GitHub API.
-   Generate a repository browser for the lab website.

Recommended implementation:

Keep the existing homepage unchanged and generate a separate page such
as:

`repositories.html`

rather than replacing `index.html`.

------------------------------------------------------------------------

## Recommendations for the Peng He Lab

Recommended taxonomy:

Property:

`Category`

Values:

-   Computational methods
-   Data sharing
-   Lab resources

This keeps the repository metadata simple while remaining scalable.

Additional properties can be added later if needed, for example:

-   Status
-   Funding
-   Language

Avoid adding unnecessary complexity until it becomes useful.

------------------------------------------------------------------------

## Lessons Learned

-   Think of **properties** as fields (columns).
-   Think of **values** as the allowed entries for those fields.
-   Prefer a single categorical property over multiple Boolean/text
    properties when every repository belongs to one logical group.
-   GitHub Custom Properties improve searching and filtering, but they
    do not replace folders or collections.
