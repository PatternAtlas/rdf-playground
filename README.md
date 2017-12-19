# rdf-playground
This repo holds RDF data in different representations. 

Beispiel einer SPARQL-Endpoint implementation (umgesetzt mit [Apache Jena](https://jena.apache.org/)): http://62.217.127.118:8080/sparql-ld-endpoint/

Hier ist das [Github Projekt](https://github.com/fafalios/sparql-ld) dazu. 

## Query RDFa data
Folgende Beispiel Eingabe gibt die namen aller Techarticles in rdfa.html zurück

```
PREFIX foo: <http://schema.org/>
SELECT ?name
WHERE {
  SERVICE <https://patternpedia.github.io/rdf-playground/rdfa.html> {
    ?TechArticles foo:name ?name  }
}
```
## Query über zwei files
```
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
SELECT ?nameOfFriend
WHERE {
  SERVICE <https://patternpedia.github.io/rdf-playground/foaf-manu.html> {
    ?S foaf:knows ?knowsUri   }
  SERVICE ?knowsUri {
    ?Friend foaf:name ?nameOfFriend
  }
}
```
