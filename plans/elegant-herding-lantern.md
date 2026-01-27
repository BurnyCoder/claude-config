# AI Interpretability Wiki - Implementation Plan

## Overview

Create a comprehensive Obsidian vault wiki on AI Interpretability with focus on Mechanistic Interpretability. All content will be fact-checked with sources linked to existing URLs.

**User Preferences:**
- Scope: Full comprehensive (~57 files)
- Structure: Folder-based (13 topic folders)
- Focus: Balanced coverage across all topics

## Vault Structure

```
ai-interpretability-wiki/
├── Home.md                          (Main index/dashboard)
├── Concepts/
│   ├── Core Concepts.md
│   ├── Features.md
│   ├── Circuits.md
│   ├── Superposition.md
│   ├── Polysemanticity and Monosemanticity.md
│   ├── Linear Representation Hypothesis.md
│   └── Universality.md
├── Techniques/
│   ├── Overview of Techniques.md
│   ├── Activation Patching.md
│   ├── Probing Classifiers.md
│   ├── Sparse Autoencoders.md
│   ├── Feature Visualization.md
│   ├── Logit Lens and Tuned Lens.md
│   ├── Circuit Analysis.md
│   ├── Attribution Graphs.md
│   └── Causal Tracing.md
├── Results/
│   ├── Key Discoveries.md
│   ├── Induction Heads.md
│   ├── Grokking.md
│   ├── IOI Circuit.md
│   ├── Scaling Monosemanticity.md
│   └── Vision Model Circuits.md
├── People and Organizations/
│   ├── Overview.md
│   ├── Key Researchers.md           (Chris Olah, Neel Nanda, David Bau, Max Tegmark, etc.)
│   ├── Anthropic.md
│   ├── Google DeepMind.md
│   ├── OpenAI.md
│   ├── Redwood Research.md
│   ├── Apollo Research.md
│   ├── UK AI Safety Institute.md
│   └── Academic Labs.md             (MIT, Northeastern, etc.)
├── Papers/
│   ├── Foundational Papers.md
│   ├── Circuits Thread.md           (Anthropic's transformer-circuits.pub)
│   ├── SAE Papers.md
│   ├── Survey Papers.md
│   └── Recent Papers 2024-2025.md
├── Tools and Libraries/
│   ├── Overview.md
│   ├── TransformerLens.md
│   ├── SAELens.md
│   ├── NNsight.md
│   ├── Pyvene.md
│   ├── Neuronpedia.md
│   ├── Gemma Scope.md
│   └── Other Tools.md               (BertViz, SAE-Vis, etc.)
├── Learning Resources/
│   ├── Getting Started.md
│   ├── ARENA.md
│   ├── MATS.md
│   ├── Online Courses.md
│   ├── Books.md                     (Christoph Molnar's book, etc.)
│   ├── Tutorials.md
│   └── Video Resources.md           (3Blue1Brown, AXRP, etc.)
├── Communities/
│   ├── Overview.md
│   ├── Alignment Forum.md
│   ├── LessWrong.md
│   ├── EleutherAI.md
│   ├── Discord Servers.md
│   ├── Slack Communities.md
│   └── Local Groups.md
├── Events/
│   ├── Conferences.md               (NeurIPS, ICML workshops)
│   ├── Hackathons.md                (Apart Research)
│   └── Past Events.md
├── Theory/
│   ├── Theoretical Foundations.md
│   ├── Superposition Theory.md
│   ├── Computational Mechanics.md
│   └── Open Problems.md
├── Architectures/
│   ├── Transformers.md
│   ├── Vision Models.md
│   └── Other Architectures.md
├── XAI Context/
│   ├── Explainable AI Overview.md
│   ├── LIME and SHAP.md
│   └── Mechanistic vs Post-hoc.md
└── Resources/
    ├── Wikipedia Links.md
    ├── Glossary.md
    ├── Reading Lists.md
    ├── Taxonomies and Maps.md
    └── External Links.md
```

## Files to Create (Priority Order)

### Phase 1: Core Structure (12 files)
1. **Home.md** - Main dashboard with navigation
2. **Concepts/Core Concepts.md** - Overview linking to all concept pages
3. **Techniques/Overview of Techniques.md** - Techniques summary
4. **People and Organizations/Overview.md** - Key players summary
5. **Tools and Libraries/Overview.md** - Tools ecosystem
6. **Learning Resources/Getting Started.md** - Entry point for learners
7. **Resources/Glossary.md** - Key terms with definitions
8. **Papers/Foundational Papers.md** - Essential reading list
9. **Communities/Overview.md** - Where to engage
10. **Events/Conferences.md** - Key events
11. **Theory/Open Problems.md** - Research frontiers
12. **Resources/Wikipedia Links.md** - External references

### Phase 2: Core Concepts (7 files)
- Features.md, Circuits.md, Superposition.md, Polysemanticity and Monosemanticity.md, Linear Representation Hypothesis.md, Universality.md

### Phase 3: Techniques Deep Dives (8 files)
- Activation Patching.md, Probing Classifiers.md, Sparse Autoencoders.md, Feature Visualization.md, Logit Lens and Tuned Lens.md, Circuit Analysis.md, Attribution Graphs.md, Causal Tracing.md

### Phase 4: Key Results (6 files)
- Key Discoveries.md, Induction Heads.md, Grokking.md, IOI Circuit.md, Scaling Monosemanticity.md, Vision Model Circuits.md

### Phase 5: Organizations & People (9 files)
- Key Researchers.md, Anthropic.md, Google DeepMind.md, OpenAI.md, Redwood Research.md, Apollo Research.md, UK AI Safety Institute.md, Academic Labs.md

### Phase 6: Tools (7 files)
- TransformerLens.md, SAELens.md, NNsight.md, Pyvene.md, Neuronpedia.md, Gemma Scope.md, Other Tools.md

### Phase 7: Learning & Community (10 files)
- ARENA.md, MATS.md, Books.md, Video Resources.md, Alignment Forum.md, LessWrong.md, EleutherAI.md, Discord Servers.md, Hackathons.md

### Phase 8: Remaining Files (8 files)
- Papers sections, Theory pages, XAI context, Taxonomies

**Total: ~57 files**

## Key Sources to Reference

### Primary Sources (with URLs)
- **Anthropic Circuits Thread**: https://transformer-circuits.pub/
- **Alignment Forum**: https://www.alignmentforum.org/
- **LessWrong**: https://www.lesswrong.com/
- **Distill.pub**: https://distill.pub/
- **ARENA**: https://www.arena.education/
- **MATS**: https://www.matsprogram.org/
- **Neuronpedia**: https://www.neuronpedia.org/
- **EleutherAI**: https://www.eleuther.ai/
- **Apart Research**: https://apartresearch.com/
- **TransformerLens GitHub**: https://github.com/TransformerLensOrg/TransformerLens
- **SAELens GitHub**: https://github.com/jbloomAus/SAELens
- **Christoph Molnar's Book**: https://christophm.github.io/interpretable-ml-book/
- **Wikipedia XAI**: https://en.wikipedia.org/wiki/Explainable_artificial_intelligence

### Key Papers (arXiv/direct links)
- Mechanistic Interpretability Review: https://arxiv.org/abs/2404.14082
- Induction Heads: https://arxiv.org/abs/2209.11895
- Scaling Monosemanticity: https://transformer-circuits.pub/2024/scaling-monosemanticity/
- Towards Monosemanticity: https://transformer-circuits.pub/2023/monosemantic-features
- IOI Circuit: https://arxiv.org/abs/2211.00593
- Grokking: https://arxiv.org/abs/2301.05217
- OpenAI SAEs: https://arxiv.org/abs/2406.04093
- Activation Patching: https://arxiv.org/abs/2404.15255
- Tuned Lens: https://arxiv.org/abs/2303.08112
- Open Problems: https://arxiv.org/abs/2501.16496

### Key Researchers to Profile
- Chris Olah (Anthropic) - https://colah.github.io/
- Neel Nanda (Google DeepMind) - https://www.neelnanda.io/
- David Bau (Northeastern) - https://baulab.info/
- Max Tegmark (MIT) - https://tegmark.org/

## Content Guidelines

### For Each Page
1. **Summary**: 2-3 sentence overview
2. **Key Points**: Bulleted main ideas
3. **Details**: Deeper explanation with examples
4. **Sources**: All claims linked to source URLs
5. **Related Pages**: Obsidian wikilinks `[[Page Name]]`
6. **External Links**: Markdown links `[text](url)`

### Obsidian Features to Use
- Wikilinks for internal navigation: `[[Concept Name]]`
- Tags for categorization: `#concept`, `#technique`, `#paper`, `#tool`
- Callouts for important notes: `> [!info]`
- YAML frontmatter for metadata

### Example Page Template
```markdown
---
tags: [concept, mechanistic-interpretability]
created: 2026-01-26
---

# Page Title

Brief 2-3 sentence summary of the topic.

## Overview

Main explanation with key details.

## Key Points

- Point 1
- Point 2
- Point 3

## Details

Deeper explanations, examples, and context.

## Sources

- [Source Name](https://url.com)

## Related

- [[Related Page 1]]
- [[Related Page 2]]
```

## Verification Plan

1. **Source Verification**: Every claim includes a working URL
2. **Cross-Reference**: Key facts appear in multiple authoritative sources
3. **Recency Check**: Dates on papers and resources verified
4. **Link Testing**: Manually verify URLs are accessible

## Implementation Order

1. Create folder structure
2. Create Home.md with navigation
3. Create Phase 1 overview files (establishing structure)
4. Create Phase 2-8 detailed content files
5. Add cross-links between related pages
6. Final review for broken links and consistency

## Estimated Scope

- **Total Files**: ~57 markdown files
- **Folders**: 13 main folders
- **Sources Referenced**: 50+ unique URLs
- **Cross-links**: 100+ internal wikilinks

---

## Detailed Content Per Section

### Concepts/ (7 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Core Concepts.md | Overview of mech interp paradigm, three abstraction layers (neurons, circuits, algorithms), key hypotheses | Bereska review, transformer-circuits.pub |
| Features.md | Definition, examples (curve detectors, safety features), feature families | Distill.pub, Scaling Monosemanticity |
| Circuits.md | Definition, examples (induction circuit, IOI circuit), circuit motifs | Anthropic circuits thread |
| Superposition.md | Toy models, overcomplete representations, almost-orthogonal directions | "Toy Models of Superposition" paper |
| Polysemanticity and Monosemanticity.md | Why neurons activate for unrelated concepts, SAEs as solution | Towards Monosemanticity |
| Linear Representation Hypothesis.md | Concepts as directions in activation space | Multiple Anthropic papers |
| Universality.md | Same features/circuits across models | Zoom In paper |

### Techniques/ (9 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Overview of Techniques.md | Taxonomy of methods, when to use each | Bereska review |
| Activation Patching.md | Clean/corrupted runs, causal tracing, attribution patching | Heimersheim paper, Neel Nanda blog |
| Probing Classifiers.md | Linear probes, limitations, behavioral vs causal | Multiple papers |
| Sparse Autoencoders.md | Architecture, training, JumpReLU, TopK, evaluation metrics | OpenAI SAE paper, Anthropic papers |
| Feature Visualization.md | Optimization-based viz, DeepDream history, Building Blocks | Distill.pub Feature Visualization |
| Logit Lens and Tuned Lens.md | Residual stream decoding, affine translators | nostalgebraist, Belrose et al. |
| Circuit Analysis.md | Manual tracing, automated discovery, validation | Circuits thread |
| Attribution Graphs.md | 2025 Anthropic method, transcoders, Neuronpedia integration | Anthropic March 2025 papers |
| Causal Tracing.md | Rome/MEMIT context, fact localization | David Bau papers |

### Results/ (6 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Key Discoveries.md | Timeline of major findings 2017-2025 | Multiple |
| Induction Heads.md | [A][B]...[A]→[B], phase change, in-context learning | Olsson et al. 2022 |
| Grokking.md | Modular arithmetic, Fourier features, three training phases | Nanda et al. 2023 |
| IOI Circuit.md | 26-head circuit, name movers, backup heads | Wang et al. 2022 |
| Scaling Monosemanticity.md | Claude 3 Sonnet SAEs, safety-relevant features | Anthropic 2024 |
| Vision Model Circuits.md | InceptionV1, curve detectors, dog head circuits | Zoom In, Building Blocks |

### People and Organizations/ (9 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Overview.md | Landscape of orgs, research groups, funding | Multiple |
| Key Researchers.md | Chris Olah, Neel Nanda, David Bau, Max Tegmark, etc. | Personal sites, papers |
| Anthropic.md | Interpretability team, Circuits thread, Claude interpretability | anthropic.com, transformer-circuits.pub |
| Google DeepMind.md | Neel Nanda's team, Gemma Scope, SAE research | deepmind.google |
| OpenAI.md | Superalignment team, GPT-4 SAEs, feature visualization | openai.com |
| Redwood Research.md | AI control, MLAB, Constellation, history | redwoodresearch.org |
| Apollo Research.md | Deception evals, scheming detection, AISI partnerships | apolloresearch.ai |
| UK AI Safety Institute.md | Pre-deployment evals, research agenda, gov role | aisi.gov.uk |
| Academic Labs.md | MIT (Tegmark), Northeastern (Bau), Stanford, Berkeley | Academic sites |

### Papers/ (5 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Foundational Papers.md | Must-read list with summaries | arXiv, OpenReview |
| Circuits Thread.md | All transformer-circuits.pub papers | transformer-circuits.pub |
| SAE Papers.md | Evolution of SAE techniques | Multiple |
| Survey Papers.md | Bereska review, Open Problems paper | arXiv |
| Recent Papers 2024-2025.md | Latest developments | arXiv |

### Tools and Libraries/ (7 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Overview.md | Ecosystem map, choosing tools | Multiple GitHub repos |
| TransformerLens.md | Installation, API, supported models, tutorials | GitHub, docs |
| SAELens.md | Training SAEs, loading pretrained, integration | GitHub, docs |
| NNsight.md | HuggingFace integration, intervention API | GitHub, docs |
| Pyvene.md | Causal interventions, Stanford origin | GitHub |
| Neuronpedia.md | Feature exploration, steering, visualization | neuronpedia.org |
| Gemma Scope.md | Google DeepMind's SAE suite for Gemma | deepmind.google |

### Learning Resources/ (7 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Getting Started.md | Learning paths, prerequisites, recommended order | Multiple |
| ARENA.md | Program structure, mech interp chapter, how to access | arena.education |
| MATS.md | Application process, mentors, research streams | matsprogram.org |
| Online Courses.md | Additional courses, prerequisites | Various |
| Books.md | Christoph Molnar's book, other resources | christophm.github.io |
| Tutorials.md | TransformerLens tutorials, notebooks, guides | GitHub |
| Video Resources.md | 3Blue1Brown, AXRP podcast, 80k Hours | YouTube, podcast sites |

### Communities/ (7 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Overview.md | Where to engage, community norms | Multiple |
| Alignment Forum.md | Focus, key posts, how to contribute | alignmentforum.org |
| LessWrong.md | Broader context, AI safety discussions | lesswrong.com |
| EleutherAI.md | Discord, interpretability channels, community | eleuther.ai |
| Discord Servers.md | Mech Interp Discord, Rob Miles, others | Discord |
| Slack Communities.md | AI Safety Support, AGI Safety Fundamentals | Various |
| Local Groups.md | In-person meetups, university groups | aisafety.com |

### Events/ (3 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Conferences.md | NeurIPS/ICML workshops, submission info | Conference sites |
| Hackathons.md | Apart Research sprints, ARENA hackathons | apartresearch.com |
| Past Events.md | Historical events, MIT MI Conference | Various |

### Theory/ (4 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Theoretical Foundations.md | Mathematical framework, learning theory | Papers |
| Superposition Theory.md | Toy models formalism, geometry | Anthropic |
| Computational Mechanics.md | Alternative framework, epsilon machines | Papers |
| Open Problems.md | Research frontiers, unsolved questions | Open Problems paper, LessWrong |

### Architectures/ (3 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Transformers.md | Attention, MLPs, residual stream | Various |
| Vision Models.md | CNNs, ViTs, differences from LLMs | Distill |
| Other Architectures.md | RNNs, MoEs, emerging architectures | Various |

### XAI Context/ (3 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Explainable AI Overview.md | XAI history, DARPA program, NIST principles | Wikipedia, DARPA |
| LIME and SHAP.md | Post-hoc methods, comparison to mech interp | Molnar book |
| Mechanistic vs Post-hoc.md | Philosophical differences, trade-offs | Papers |

### Resources/ (5 files)
| File | Key Content | Primary Sources |
|------|-------------|-----------------|
| Wikipedia Links.md | External reference links | Wikipedia |
| Glossary.md | A-Z definitions with sources | Multiple |
| Reading Lists.md | Curated paths by topic/level | Neel Nanda's lists |
| Taxonomies and Maps.md | Visual organization of field | Bereska, others |
| External Links.md | Useful external resources | Multiple |

---

## Verification Checklist

Before marking complete:
- [ ] All URLs tested and accessible
- [ ] Each page has at least 2 sources
- [ ] Cross-links work between pages
- [ ] Tags consistent across files
- [ ] No unsourced claims
- [ ] Dates verified on papers/events
- [ ] Names/organizations spelled correctly
