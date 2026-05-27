# Prototype Claim Graph Schema

This document defines a minimal but extensible schema for a claim extraction and querying prototype.

The design goal is:

- keep the core object model stable
- keep ontology enhancement consistent everywhere
- support simple extraction today
- support richer domain-specific profiles later
- keep the graph shape queryable without forcing everything into flat triples

## 1. Design Principles

### 1.1 Stable base objects

The prototype should keep a small fixed set of objects:

- `Paper`
- `Span`
- `Claim`
- `EvidenceItem`
- `ClaimEvidenceLink`

Optional supporting objects:

- `Entity`
- `OntologyAnnotation`

### 1.2 Stable ontology enhancement rule

Any field that may be ontology-enhanced should use the same pattern:

```json
{
  "value": "human",
  "entity_type": "species",
  "ontology": {
    "annotation_type": "mapping",
    "raw_text": "human",
    "normalized_text": "human",
    "mapping_status": "mapped",
    "candidate_mappings": [
      {
        "ontology_source": "NCBITaxon",
        "ontology_id": "NCBITaxon:9606",
        "ontology_label": "Homo sapiens",
        "match_type": "exact",
        "confidence": 0.98
      }
    ],
    "selected_mapping": {
      "ontology_source": "NCBITaxon",
      "ontology_id": "NCBITaxon:9606",
      "ontology_label": "Homo sapiens"
    },
    "mapping_method": "dictionary_plus_context"
  }
}
```

This reusable pattern is called a `SemanticField` in this document.

### 1.3 Stable extension rule

Extensibility should happen in exactly two places:

- `context`
- `details`

`context` holds qualifiers and applicability conditions.

`details` holds type-specific structured payloads.

This prevents schema sprawl while still allowing richer domain coverage later.

## 2. Object Model

### 2.1 `Paper`

The source document or source artifact.

Example schema:

```json
{
  "paper_id": "paper_123",
  "doi": "10.1234/example",
  "pmid": "12345678",
  "title": "Example Paper",
  "authors": ["A. Smith", "B. Jones"],
  "journal": "Journal Name",
  "year": 2026,
  "source_type": "journal_article",
  "open_access": true
}
```

Brief explanation:

- identifies the source
- stores high-level bibliographic metadata
- is the parent object for claims and spans

### 2.2 `Span`

A precise source anchor from the paper.

Example schema:

```json
{
  "span_id": "span_45",
  "paper_id": "paper_123",
  "section_type": "RESULTS",
  "section_name": "Primary outcome",
  "page": 7,
  "char_start": 18452,
  "char_end": 18527,
  "text": "Mean anxiety score decreased by 3.1 points (95% CI -5.4 to -0.8, p=0.01, n=184).",
  "table_id": null,
  "figure_id": null,
  "caption_id": null
}
```

Brief explanation:

- anchors a claim or evidence item to exact source text
- can also represent table, figure, or caption anchors
- carries provenance needed for later export or verification

### 2.3 `OntologyAnnotation`

The uniform structure used inside any `.ontology` subfield.

Example schema:

```json
{
  "annotation_type": "mapping",
  "raw_text": "5-HT1A",
  "normalized_text": "5-HT1A receptor",
  "mapping_status": "mapped",
  "candidate_mappings": [
    {
      "ontology_source": "CustomReceptorOntology",
      "ontology_id": "REC:5HT1A",
      "ontology_label": "5-hydroxytryptamine receptor 1A",
      "match_type": "exact",
      "confidence": 0.94
    }
  ],
  "selected_mapping": {
    "ontology_source": "CustomReceptorOntology",
    "ontology_id": "REC:5HT1A",
    "ontology_label": "5-hydroxytryptamine receptor 1A"
  },
  "mapping_method": "dictionary_plus_context"
}
```

Brief explanation:

- stores ontology enhancement in one consistent shape
- supports both successful mappings and unresolved cases
- can be used for concepts, qualifiers, and evidence-level classification

Recommended field meanings:

- `annotation_type`: `mapping` or `classification`
- `mapping_status`: `mapped`, `ambiguous`, `unresolved`, `rejected`
- `candidate_mappings`: ranked ontology candidates
- `selected_mapping`: chosen ontology concept if available

### 2.4 `SemanticField`

A reusable wrapper for any concept-like field.

Example schema:

```json
{
  "value": "Psilocybin",
  "entity_type": "chemical",
  "ontology": {
    "annotation_type": "mapping",
    "raw_text": "Psilocybin",
    "normalized_text": "psilocybin",
    "mapping_status": "mapped",
    "candidate_mappings": [
      {
        "ontology_source": "ChEBI",
        "ontology_id": "CHEBI:0000",
        "ontology_label": "Psilocybin",
        "match_type": "exact",
        "confidence": 0.99
      }
    ],
    "selected_mapping": {
      "ontology_source": "ChEBI",
      "ontology_id": "CHEBI:0000",
      "ontology_label": "Psilocybin"
    },
    "mapping_method": "dictionary_plus_context"
  }
}
```

Brief explanation:

- keeps raw value and ontology enhancement separate
- should be used wherever a field may need semantic normalization
- avoids inventing different field shapes for subject, object, species, assay type, and so on

Recommended usage:

- `Claim.subject`
- `Claim.object`
- `Claim.context.*`
- `EvidenceItem.context.*`
- concept-like fields inside `details`

### 2.5 `Claim`

A paper-specific assertion with a queryable subject-predicate-object core plus epistemic metadata.

Example schema:

```json
{
  "claim_id": "claim_1",
  "paper_id": "paper_123",
  "claim_text": "Psilocybin reduced anxiety symptoms in treatment-resistant adults.",
  "subject": {
    "value": "Psilocybin",
    "entity_type": "chemical",
    "ontology": {
      "annotation_type": "mapping",
      "raw_text": "Psilocybin",
      "normalized_text": "psilocybin",
      "mapping_status": "mapped",
      "candidate_mappings": [
        {
          "ontology_source": "ChEBI",
          "ontology_id": "CHEBI:0000",
          "ontology_label": "Psilocybin",
          "match_type": "exact",
          "confidence": 0.99
        }
      ],
      "selected_mapping": {
        "ontology_source": "ChEBI",
        "ontology_id": "CHEBI:0000",
        "ontology_label": "Psilocybin"
      },
      "mapping_method": "dictionary_plus_context"
    }
  },
  "predicate": {
    "value": "reduced",
    "entity_type": "predicate",
    "ontology": {
      "annotation_type": "mapping",
      "raw_text": "reduced",
      "normalized_text": "decreases",
      "mapping_status": "mapped",
      "candidate_mappings": [
        {
          "ontology_source": "CustomPredicateVocabulary",
          "ontology_id": "PRED:decreases",
          "ontology_label": "decreases",
          "match_type": "exact",
          "confidence": 0.93
        }
      ],
      "selected_mapping": {
        "ontology_source": "CustomPredicateVocabulary",
        "ontology_id": "PRED:decreases",
        "ontology_label": "decreases"
      },
      "mapping_method": "normalization_rule"
    }
  },
  "object": {
    "value": "anxiety symptoms",
    "entity_type": "phenotype",
    "ontology": {
      "annotation_type": "mapping",
      "raw_text": "anxiety symptoms",
      "normalized_text": "anxiety symptoms",
      "mapping_status": "mapped",
      "candidate_mappings": [
        {
          "ontology_source": "MeSH",
          "ontology_id": "MESH:0000",
          "ontology_label": "Anxiety",
          "match_type": "broad",
          "confidence": 0.82
        }
      ],
      "selected_mapping": {
        "ontology_source": "MeSH",
        "ontology_id": "MESH:0000",
        "ontology_label": "Anxiety"
      },
      "mapping_method": "dictionary_plus_context"
    }
  },
  "claim_kind": "result",
  "epistemic_status": "empirical",
  "support_origin": "own_results",
  "source_span_ids": ["span_44"],
  "context": {
    "population": {
      "value": "treatment-resistant adults",
      "entity_type": "population",
      "ontology": {
        "annotation_type": "mapping",
        "raw_text": "treatment-resistant adults",
        "normalized_text": "treatment-resistant adults",
        "mapping_status": "unresolved",
        "candidate_mappings": [],
        "selected_mapping": null,
        "mapping_method": "none"
      }
    }
  },
  "details": {},
  "extractor_confidence": 0.81
}
```

Brief explanation:

- contains the main proposition the system should reason over
- keeps SPO explicit but not as the entire data model
- uses `context` for applicability qualifiers
- leaves `details` available for future claim-specific structured extensions

Recommended field meanings:

- `claim_kind`: `result`, `background`, `hypothesis`, `method`, `interpretation`, `causal`, `correlational`, `descriptive`
- `epistemic_status`: `empirical`, `conjectural`, `theoretical`, `cited`, `inferred`, `mixed`
- `support_origin`: `own_results`, `cited_results`, `background`, `methodological`, `speculative`

### 2.6 `EvidenceItem`

A first-class evidence object that supports, qualifies, or contradicts a claim.

Example schema:

```json
{
  "evidence_id": "ev_1",
  "paper_id": "paper_123",
  "role": "supports",
  "summary_text": "Mean anxiety score decreased by 3.1 points (95% CI -5.4 to -0.8, p=0.01, n=184).",
  "evidence_method": {
    "value": "randomized_controlled_trial",
    "entity_type": "evidence_method",
    "ontology": null
  },
  "outcome_type": {
    "value": "clinical_outcome",
    "entity_type": "outcome_type",
    "ontology": null
  },
  "presentation_type": {
    "value": "table",
    "entity_type": "presentation_type",
    "ontology": null
  },
  "source_span_ids": ["span_45"],
  "context": {
    "population": {
      "value": "treatment-resistant adults",
      "entity_type": "population",
      "ontology": {
        "annotation_type": "mapping",
        "raw_text": "treatment-resistant adults",
        "normalized_text": "treatment-resistant adults",
        "mapping_status": "unresolved",
        "candidate_mappings": [],
        "selected_mapping": null,
        "mapping_method": "none"
      }
    },
    "species": {
      "value": "human",
      "entity_type": "species",
      "ontology": {
        "annotation_type": "mapping",
        "raw_text": "human",
        "normalized_text": "human",
        "mapping_status": "mapped",
        "candidate_mappings": [
          {
            "ontology_source": "NCBITaxon",
            "ontology_id": "NCBITaxon:9606",
            "ontology_label": "Homo sapiens",
            "match_type": "exact",
            "confidence": 0.98
          }
        ],
        "selected_mapping": {
          "ontology_source": "NCBITaxon",
          "ontology_id": "NCBITaxon:9606",
          "ontology_label": "Homo sapiens"
        },
        "mapping_method": "dictionary_plus_context"
      }
    }
  },
  "details": {
    "outcome_name": "anxiety score",
    "effect_size": -3.1,
    "unit": "scale points",
    "ci_low": -5.4,
    "ci_high": -0.8,
    "p_value": 0.01,
    "sample_size": 184
  },
  "ontology": {
    "annotation_type": "classification",
    "raw_text": "clinical evidence",
    "normalized_text": "clinical evidence",
    "mapping_status": "mapped",
    "candidate_mappings": [
      {
        "ontology_source": "ECO",
        "ontology_id": "ECO:0000",
        "ontology_label": "clinical evidence",
        "match_type": "exact",
        "confidence": 0.91
      }
    ],
    "selected_mapping": {
      "ontology_source": "ECO",
      "ontology_id": "ECO:0000",
      "ontology_label": "clinical evidence"
    },
    "mapping_method": "rule_plus_llm"
  }
}
```

Brief explanation:

- stores queryable support, not just loose evidence sentences
- separates the HOW, WHAT, and presentation format into different fields
- uses `context` for evidence qualifiers such as species, population, assay type, dose, comparator
- uses `details` for type-specific structure
- uses top-level `ontology` for ontology classification of the evidence item as a whole

Recommended field meanings:

- `evidence_method`: how the evidence was produced, such as `randomized_controlled_trial`, `laboratory_experiment`, `regression_estimate`, `observation`, `simulation`, `meta_analysis`, `theoretical_argument`, `mathematical_derivation`
- `outcome_type`: what kind of thing was measured, such as `clinical_outcome`, `molecular_binding`, `gene_expression`, `physiological_measure`, `adverse_event`
- `presentation_type`: how the result appears in the paper, such as `text`, `table`, `figure`, `caption`, `supplement`
- `role`: `supports`, `contradicts`, `qualifies`, `backgrounds`

### 2.7 `ClaimEvidenceLink`

The explicit relation between a claim and an evidence item.

Example schema:

```json
{
  "link_id": "link_1",
  "claim_id": "claim_1",
  "evidence_id": "ev_1",
  "relation": "supports",
  "confidence": 0.92
}
```

Brief explanation:

- keeps claim/evidence linkage explicit
- allows one evidence item to relate to many claims
- allows one claim to be backed by many evidence items

## 3. Profiles

Profiles define the expected shape of `context` and `details` without changing the core schema.

The base object model stays fixed. Profiles only say which keys are relevant for a given use case.

### 3.1 Claim profile

Purpose:

- specializes `Claim.context`
- optionally specializes `Claim.details`

Recommended default claim profile:

```json
{
  "allowed_context_keys": [
    "population",
    "species",
    "setting",
    "timepoint",
    "comparator"
  ],
  "allowed_details_keys": []
}
```

Brief explanation:

- claims usually need only lightweight qualifiers at first
- most heavy structured data should live in evidence, not in claims

### 3.2 Evidence method profiles

Purpose:

- specializes `EvidenceItem.context`
- specializes `EvidenceItem.details` according to `evidence_method`

#### Randomized controlled trial profile

```json
{
  "evidence_method": "randomized_controlled_trial",
  "allowed_context_keys": [
    "population",
    "species",
    "setting",
    "dose",
    "timepoint",
    "comparator"
  ],
  "allowed_details_keys": [
    "outcome_name",
    "effect_size",
    "unit",
    "ci_low",
    "ci_high",
    "p_value",
    "sample_size"
  ]
}
```

#### Laboratory experiment profile

```json
{
  "evidence_method": "laboratory_experiment",
  "allowed_context_keys": [
    "species",
    "assay_type",
    "dose",
    "timepoint",
    "temperature",
    "ph"
  ],
  "allowed_details_keys": [
    "measurement_type",
    "outcome_name",
    "value",
    "unit",
    "ci_low",
    "ci_high",
    "sample_size",
    "target"
  ]
}
```

#### Meta-analysis profile

```json
{
  "evidence_method": "meta_analysis",
  "allowed_context_keys": [
    "population",
    "species",
    "setting"
  ],
  "allowed_details_keys": [
    "outcome_name",
    "effect_size",
    "unit",
    "ci_low",
    "ci_high",
    "p_value",
    "study_count",
    "sample_size"
  ]
}
```

### 3.3 Outcome type profiles

```json
{
  "outcome_type": "clinical_outcome",
  "description": "Observed clinical endpoint, symptom score, or patient outcome."
}
```

```json
{
  "outcome_type": "molecular_binding",
  "description": "Binding affinity, receptor activation, or related molecular readout."
}
```

### 3.4 Presentation type profiles

```json
{
  "presentation_type": "table",
  "description": "Evidence primarily presented in a table."
}
```

```json
{
  "presentation_type": "text",
  "description": "Evidence primarily described in narrative prose."
}
```

Brief explanation:

- profiles constrain shape without requiring new top-level objects
- evidence method carries the epistemic ontology focus on the HOW
- outcome type captures the WHAT
- presentation type captures where the result appears in the paper
- they give miners a clearer contract for what to populate
- they keep future domain growth manageable

## 4. Graph Translation

The object model maps naturally to a graph.

Recommended graph shape:

```text
(Paper)-[:HAS_SPAN]->(Span)
(Paper)-[:HAS_CLAIM]->(Claim)
(Claim)-[:HAS_SUBJECT]->(Entity)
(Claim)-[:HAS_OBJECT]->(Entity)
(Claim)-[:SUPPORTED_BY]->(EvidenceItem)
(EvidenceItem)-[:ANCHORED_IN]->(Span)
```

Notes:

- `Claim` should be a node, not only an edge, because claims need metadata, provenance, and many evidence links
- `subject` and `object` can be stored as `Entity` nodes or flattened into claim fields in a simpler prototype
- most structured metadata can remain node properties rather than exploding into many tiny graph nodes

## 5. Worked Example

This example shows all major objects together.

### `Paper`

```json
{
  "paper_id": "paper_123",
  "doi": "10.1234/example",
  "title": "Psilocybin in treatment-resistant anxiety",
  "year": 2026
}
```

### `Span`

```json
{
  "span_id": "span_45",
  "paper_id": "paper_123",
  "section_type": "RESULTS",
  "text": "Mean anxiety score decreased by 3.1 points (95% CI -5.4 to -0.8, p=0.01, n=184)."
}
```

### `Claim`

```json
{
  "claim_id": "claim_1",
  "paper_id": "paper_123",
  "claim_text": "Psilocybin reduced anxiety symptoms in treatment-resistant adults.",
  "subject": {
    "value": "Psilocybin",
    "entity_type": "chemical",
    "ontology": {
      "annotation_type": "mapping",
      "raw_text": "Psilocybin",
      "normalized_text": "psilocybin",
      "mapping_status": "mapped",
      "candidate_mappings": [],
      "selected_mapping": {
        "ontology_source": "ChEBI",
        "ontology_id": "CHEBI:0000",
        "ontology_label": "Psilocybin"
      },
      "mapping_method": "dictionary_plus_context"
    }
  },
  "predicate": {
    "value": "reduced",
    "entity_type": "predicate",
    "ontology": null
  },
  "object": {
    "value": "anxiety symptoms",
    "entity_type": "phenotype",
    "ontology": null
  },
  "claim_kind": "result",
  "epistemic_status": "empirical",
  "support_origin": "own_results",
  "source_span_ids": ["span_45"],
  "context": {
    "population": {
      "value": "treatment-resistant adults",
      "entity_type": "population",
      "ontology": null
    }
  },
  "details": {},
  "extractor_confidence": 0.81
}
```

### `EvidenceItem`

```json
{
  "evidence_id": "ev_1",
  "paper_id": "paper_123",
  "evidence_method": {
    "value": "randomized_controlled_trial",
    "entity_type": "evidence_method",
    "ontology": null
  },
  "outcome_type": {
    "value": "clinical_outcome",
    "entity_type": "outcome_type",
    "ontology": null
  },
  "presentation_type": {
    "value": "table",
    "entity_type": "presentation_type",
    "ontology": null
  },
  "role": "supports",
  "summary_text": "Mean anxiety score decreased by 3.1 points (95% CI -5.4 to -0.8, p=0.01, n=184).",
  "source_span_ids": ["span_45"],
  "context": {
    "population": {
      "value": "treatment-resistant adults",
      "entity_type": "population",
      "ontology": null
    },
    "species": {
      "value": "human",
      "entity_type": "species",
      "ontology": {
        "annotation_type": "mapping",
        "raw_text": "human",
        "normalized_text": "human",
        "mapping_status": "mapped",
        "candidate_mappings": [],
        "selected_mapping": {
          "ontology_source": "NCBITaxon",
          "ontology_id": "NCBITaxon:9606",
          "ontology_label": "Homo sapiens"
        },
        "mapping_method": "dictionary_plus_context"
      }
    }
  },
  "details": {
    "outcome_name": "anxiety score",
    "effect_size": -3.1,
    "unit": "scale points",
    "ci_low": -5.4,
    "ci_high": -0.8,
    "p_value": 0.01,
    "sample_size": 184
  },
  "ontology": {
    "annotation_type": "classification",
    "raw_text": "clinical evidence",
    "normalized_text": "clinical evidence",
    "mapping_status": "mapped",
    "candidate_mappings": [],
    "selected_mapping": {
      "ontology_source": "ECO",
      "ontology_id": "ECO:0000",
      "ontology_label": "clinical evidence"
    },
    "mapping_method": "rule_plus_llm"
  }
}
```

### `ClaimEvidenceLink`

```json
{
  "link_id": "link_1",
  "claim_id": "claim_1",
  "evidence_id": "ev_1",
  "relation": "supports",
  "confidence": 0.92
}
```

## 6. What This Schema Intentionally Does Not Do

- it does not force everything into flat SPO triples
- it does not require perfect ontology resolution before extraction is useful
- it does not force every evidence subtype into a new top-level object
- it does not require every structured field to become its own graph node

## 7. Recommended Implementation Contract for Miners

Miners should be able to populate the schema in layers:

### Minimum useful output

- `Paper`
- `Span`
- `Claim`
- `EvidenceItem`
- `ClaimEvidenceLink`

### Better output

- populate `context`
- populate `details`
- populate `.ontology` where confidence is high

### Best output

- include candidate mappings when ontology is ambiguous
- classify evidence item ontology using ECO or a similar vocabulary
- normalize predicates consistently

## 8. Bottom Line

The core design is:

- stable base objects
- one reusable `SemanticField` pattern
- one reusable `OntologyAnnotation` pattern
- extensibility through `context` and `details`
- graph shape built around `Claim` and `EvidenceItem`, not only raw triples

That gives the prototype a simple present-day structure without boxing it out of future ontology-aware querying.
