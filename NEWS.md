# ecocomDP 1.2.0

## Enhancements
* Release new plotting functions for taxonomic and geographic exploration.
* Allow multiple input types to the new `data` parameter of "use" functions (supercedes `dataset`), thereby simplifying and accelerating exploratory manipulation and plotting.
* Reformat dataset object returned by `read_data()`. Generally, this simplifies dataset indexing and usage within iteration contexts. It removes a layer of nesting and places the dataset id at the same level as metadata, tables, and validation_issues.
* Release new `annotation_dictionary()` function. This feature will allow ecocomDP creators to view the semantic annotations for existing ecocomDP datasets. Annotation dictionary is published as an EDI data package to apply occasional updates.
* Release new `validate_mapped_id()` function. Ensures values listed under /variable_mapping/mapped_id resolve without error
* Release new Model Overview vignette. The model overview vignette consists of the authoritative set of table descriptions, relationships, and requirements for the ecocomDP model and a visualization of table contents and relationships.
* Release new Shared Practices Vignette. This document delineates the practices that all creators of ecocomDP formatted datasets should adopt in order for the community to build a cohesive and interoperable collection. It contains detailed descriptions of practices, definitions of concepts, and solutions to many common issues.

## Fixes
* Prevent L1 EML from inheriting L0 provenance and additional metadata, these should not be inherited by the L1 in `create_eml()`
  
## Deprecation
* Discourage use of the `observation` parameter of plotting functions and replace it with the more flexible `data` parameter (see above). These changes are backwards compatible with previous releases.
* Discourage use of `plot_taxa_sample_time()` in favor of `plot_sample_space_time()`. These changes are backwards compatible with previous releases.
* Discourage use of the previous `dataset` object returned by `read_data()` in favor of a new one. See details above. These changes are backwards compatible with previous releases.

# ecocomDP 1.1.0

## Enhancements
* Link to ecocomDP article.
* Enable full return of L0 location columns in `flatten_data()`.
* Implement a human readable row sorting based on location_id values in `create_location()`.
* Check create_ecocomDP.R for expected function and associated arguments in `create_eml()`.

## Fixes
* Fix alignment of categorical variable names and definitions in `create_eml()`.
* Allow only one basisOfRecord in `create_eml()`.
* Fix numeric type detection in `create_eml()`.
* Fix taxonomic hierarchy expander in `create_eml()`.
* Fix empty annotation defaults in `create_eml()`.
* Remove all L0 data entities from the L1 EML, these should not be inherited by the L1 in `create_eml()`.
* Handle both present/absent L0 taxonomic coverage in `create_eml()`.
* Fix assignment of self referencing ids in `create_location()`.
* Only return unique locations in `create_location()`.
* Fix methods in `calc_number_of_years_sampled()` and `calc_length_of_survey_years()`.
* Fix handling of datetimes with YYYY format in `read_data()`.
* Include ancillary table datetime in join operations of `flatten_data()`.
* Remove XML attributes to prevent id clashing and schema invalidation when constructing provenance nodes in `create_eml()` and `convert_to_dwca()`.
* Fix basisOfRecord reference in `convert_to_dwca()`.
* Incorporate L0 methods markdown blocks in `convert_to_dwca()`.
* Prevent namespace clash with the taxonomyCleanr package.

# ecocomDP 1.0.0

* The ecocomDP package is now available on CRAN
