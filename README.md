# APTO

This is the normative document for the Agriculture Product Types Ontology (APTO). APTO is an ontology of types, meaning it does not contain individuals and is intended as a classification system for agricultural commodities price index databases in Brazil.

## Distributions

- This normative document in [HTML](https://github.com/AlmesCore/APTO/blob/main/README.md)

- [apto.owl](https://w3id.org/apto#)

### Services for browsing the ontology:

- [Text search](https://data.pldn.nl/FilipiSoares/APTO/elasticsearch/APTO-Text-search/) (search entities by labels and comments)

- [Virtuoso](https://data.pldn.nl/FilipiSoares/APTO/sparql) (query the ontology using SPARQL)



### Normative Namespaces

| Prefix      | Namespace IRI                                             |
|-------------|-----------------------------------------------------------|
| apto          | [https://w3id.org/apto#](https://w3id.org/apto#) |
| ro          | [http://purl.obolibrary.org/obo/RO_](http://purl.obolibrary.org/obo/RO_) |
| bco         | [http://purl.obolibrary.org/obo/BCO_](http://purl.obolibrary.org/obo/BCO_) |
| owl         | [http://www.w3.org/2002/07/owl#](http://www.w3.org/2002/07/owl#) |
| rdf         | [http://www.w3.org/1999/02/22-rdf-syntax-ns#](http://www.w3.org/1999/02/22-rdf-syntax-ns#) |
| sdo         | [https://schema.org/](https://schema.org/) |
| xml         | [http://www.w3.org/XML/1998/namespace](http://www.w3.org/XML/1998/namespace) |
| xsd         | [http://www.w3.org/2001/XMLSchema#](http://www.w3.org/2001/XMLSchema#) |
| gbif        | [https://www.gbif.org/species/](https://www.gbif.org/species/) |
| rdfs        | [http://www.w3.org/2000/01/rdf-schema#](http://www.w3.org/2000/01/rdf-schema#) |
| skos        | [http://www.w3.org/2004/02/skos/core#](http://www.w3.org/2004/02/skos/core#) |
| agrovoc     | [http://aims.fao.org/aos/agrovoc/](http://aims.fao.org/aos/agrovoc/) |
| agrotermos  | [https://sistemas.sede.embrapa.br/agrotermos/resources/](https://sistemas.sede.embrapa.br/agrotermos/resources/) |

This ontology contains labels and comments in both Portuguese and English. There are two main modules: `:Organism` and `:Product_type`.


### `:Organism` Module
The `:Organism` class contains subclasses that represent the taxonomy of species related to the production of given product types. It imports taxonomic information from the Global Biodiversity Information Facility (GBIF) Backbone Taxonomy via API.

### `:Product_type` Module
The `:Product_type` class has six main subclasses organized into major groups:

- `:Inorganic_compound`
- `:Animal_product`
- `:Plant_product`
- `:Raw_product`
- `:Processed_product`
- `:By-product`

The `:Animal_product` and `:Plant_product` classes include subclasses indicating the type of processing the product has undergone. These subclasses are also children of `:Raw_product`, `:Processed_product`, and `:By-product`.

### Object Properties
APTO defines nine object properties:

- `:has_ingredient` and `:is_ingredient_of` (inverse properties): Indicate that a product type is used in the manufacturing of a processed product type (e.g., `:Cow_cheese :has_ingredient :Cow_milk`).
- `:derives_from` and `:derives_in` (inverse properties, imported from the Relations Ontology (RO)): Indicate that a product type originates from another product type (e.g., `:Cocoa_almond :derives_from :Cocoa`).
- `:member_of_taxon` (imported from the Biological Collections Ontology (BCO)): Indicates that an organismal entity belongs to a taxon (e.g., `:Pacu :member_of_taxon :Piaractus_mesopotamicus`).
- `:produced_by` and `:produces` (inverse properties, imported from RO): Indicate that an organismal entity produces a given type of product. For example, `:Cotton :produced_by :Cotton_plant`, and `:Cotton_plant :member_of_taxon :Gossypium`. If only the final product is listed in commodity databases and the rest of the organism holds no commercial value, the product is linked directly to the taxon (e.g., `:Pineapple :produced_by :Ananas_comosus`).
- `:residue_of`: Indicates that a by-product is the residue of manufacturing another product (e.g., `:Whey :residue_of :Cheese`).
- `:is_a_hybrid_of`: Specific to the `:Organism` subclasses, indicating a hybrid of two species (e.g., `:Citrus_aurantium :is_a_hybrid_of ( :Citrus_reticulata and :Citrus_maxima )`).

### Data and Annotation Properties
APTO does not include any data properties. Default annotation properties from OWL and RDF are used, with SKOS vocabulary imported to indicate alternative labels for the classes.

### Availability and Licensing
APTO is available both in a user-friendly browser and as an OWL file. Reuse is permitted with citation (License CC-BY 4.0). Recommended citation:

### Citation

Miranda Soares, F., Ferreira Pires, L., Olavo Bonino da Silva Santos, L., Corrêa, F. E., de Abreu Moreira, D., Pignatari Drucker, D., Braghetto, K. R., Botazzo Delbem, A. C., & Mauro Saraiva, A. (2024). Agriculture Product Types Ontology (APTO) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.13271285
