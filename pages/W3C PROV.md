---
title: "W3C PROV"
---

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
You only need to hold the following.

main point
- W3C PROV is a family of standards for representing "[[provenance]]" in a common format. It describes **who** the data or artifact is, **what activity** it went through, and **which entity** it became. It is used for reliability assessment, reproducibility, auditing, and traceability of data systems. ([W3C](https://www.w3.org/TR/prov-overview/?utm_source=chatgpt.com))

Core Concepts (3)
- Entity: A "thing/data" at a given point in time.
- Activity: Some kind of process or operation (can have a start/end time).
- Agent: A person, organization, software, etc., involved in an Activity.
Typical relations: `wasGeneratedBy`, `used`, `wasDerivedFrom`, `wasAttributedTo`, `wasAssociatedWith`, `actedOnBehalfOf`. ([W3C](https://www.w3.org/TR/prov-dm/?utm_source=chatgpt.com))

Specification Family (Which one do you read/use?)
- PROV-PRIMER (Getting Started, This First) ([W3C](https://www.w3.org/TR/prov-primer/?utm_source=chatgpt.com))
- PROV-DM (Definition of Conceptual Model) ([W3C](https://www.w3.org/TR/prov-dm/?utm_source=chatgpt.com))
- PROV-N (human-readable notation) ([W3C](https://www.w3.org/TR/prov-n/?utm_source=chatgpt.com))
- PROV-O (OWL2/RDF ontology, for Linked Data and SPARQL) ([W3C](https://www.w3.org/TR/prov-o/?utm_source=chatgpt.com))
- PROV-XML (XML Schema), PROV-AQ (Get History API/Linking Guidelines), PROV-Constraints (Validity Constraints) ([W3C](https://www.w3.org/TR/prov-aq/?utm_source=chatgpt.com))
- PROV-JSON (not a W3C member submission or recommendation, but has examples of use in practice) ([W3C](https://www.w3.org/Submission/prov-json/?utm_source=chatgpt.com))

Mini Example

PROV-N
provn

```
document
  prefix ex <http://example.com/>

  entity(ex:cleaned_csv)
  entity(ex:raw_csv)
  activity(ex:cleaning, 2025-09-01T12:00:00Z, 2025-09-01T12:05:00Z)
  agent(ex:alice)

  used(ex:cleaning, ex:raw_csv)
  wasGeneratedBy(ex:cleaned_csv, ex:cleaning)
  wasAssociatedWith(ex:cleaning, ex:alice)
  wasAttributedTo(ex:cleaned_csv, ex:alice)
endDocument
```

(See PROV-N for syntax details; go to PROV-O below if you want to use it in RDF.) ([W3C](https://www.w3.org/TR/prov-n/?utm_source=chatgpt.com))

PROV-O（Turtle）
turtle

```
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix ex:   <http://example.com/> .

ex:cleaned_csv a prov:Entity ;
  prov:wasGeneratedBy ex:cleaning ;
  prov:wasAttributedTo ex:alice .

ex:raw_csv a prov:Entity .

ex:cleaning a prov:Activity ;
  prov:used ex:raw_csv ;
  prov:startedAtTime "2025-09-01T12:00:00Z"^^xsd:dateTime ;
  prov:endedAtTime   "2025-09-01T12:05:00Z"^^xsd:dateTime ;
  prov:wasAssociatedWith ex:alice .

ex:alice a prov:Agent .
```

(See PROV-O for vocabulary and modeling guidelines.) ([W3C](https://www.w3.org/TR/prov-o/?utm_source=chatgpt.com))

Practical Tips
- If there is an RDF infrastructure, adopt PROV-O (easy to track and visualize with SPARQL). For lightweight client-to-client exchange, consider PROV-JSON/JSON-LD systems (but with different standard status). ([W3C](https://www.w3.org/TR/prov-o/?utm_source=chatgpt.com))
- In the API design, PROV-AQ is used to link from the resource to the coming history and how to get it. ([W3C](https://www.w3.org/TR/prov-aq/?utm_source=chatgpt.com))
- If you are aware of consistency checks and logical reasoning, you satisfy the PROV-Constraints rule. ([W3C](https://www.w3.org/TR/prov-constraints/?utm_source=chatgpt.com))
- Conversion/verification tools and libraries (e.g. PROV Toolbox for Java) are also available. ([openprovenance.org](https://openprovenance.org/service/about.html?utm_source=chatgpt.com))
If necessary, we will also cut together a minimum subset design and **schema (SHACL)** for your data model.


---
This page is auto-translated from [/nishio/W3C PROV](https://scrapbox.io/nishio/W3C PROV) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.