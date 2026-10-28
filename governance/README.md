Corn FAW Detector --- Retrospective AI Risk Assessment & Governance Plan
AI Governance Portfolio Case Study --- Rebecca Ssesanga

Domain: Agricultural AI / Computer Vision
Assessment: Retrospective AI Risk Assessment
Primary framework: NIST AI Risk Management Framework (AI RMF)
Overview
The Corn FAW Detector is a mobile machine-learning application developed
during my MSc research to identify visible Fall Armyworm (FAW) pest
damage in maize-leaf images.

This portfolio case study revisits that technical system from an AI
governance and risk-management perspective. It asks:
What governance controls would be required if the research prototype
were transitioned into sustained real-world deployment?

The assessment deliberately distinguishes between:
- Implemented during MSc research --- documented technical and
  evaluation activities.
- Retrospective governance findings --- risks and conclusions
  identified through this assessment.
- Proposed governance controls --- measures recommended for
  operational deployment.
System snapshot
  Attribute          Description
  AI task            Maize-leaf image classification for visible FAW damage
  Technique          CNN transfer learning
  Candidate models   VGG16, InceptionV3, MobileNetV2
  Selected model     MobileNetV2
  Deployment         TensorFlow Lite / Android
  Dataset            2,868 maize-leaf images
  Classes            1,399 FAW-damaged; 1,469 Healthy
  Data geography     Bugiri and Kasese, Uganda
Why governance matters
MobileNetV2 achieved 99.65% test accuracy and an F1 score of
1.00 in the original evaluation. However, field evaluation showed that
of 200 leaves predicted as Healthy, 20 were actually FAW affected.

That gap illustrates a central lesson of this case study:
Strong model performance does not eliminate operational AI risk.

The governance analysis therefore goes beyond accuracy to examine false
negatives, generalisation, image quality, human reliance, purpose
limitation, lifecycle monitoring, data governance and system integrity.
Risk assessment
A retrospective 5×5 likelihood-impact methodology identified 11 risks.

  ID    Risk                                       Score Rating
  R01   False-negative FAW classification             16 High
  R02   Geographic/data generalisation                12 High
  R03   Image quality/input variation                 12 High
  R04   Human over-reliance / automation bias         12 High
  R05   Out-of-scope use                               9 Moderate
  R06   Operational performance degradation           12 High
  R07   Insufficient user understanding                9 Moderate
  R08   Model overfitting/model selection              6 Moderate
  R09   Inadequate post-deployment governance         12 High
  R10   Data governance/dataset accountability         9 Moderate
  R11   AI model/application integrity                 8 Moderate
Highest-priority risk: false negatives
The highest-rated risk is a FAW-affected leaf being classified as
Healthy.

Proposed controls include:
- additional field validation focused on false negatives;
- error analysis of recurring false-negative characteristics;
- human escalation where visible symptoms remain;
- appropriate-use messaging;
- monitoring of field false-negative rate; and
- incident recording for material confirmed failures.
Primary KRI:

False Negative Rate = FN / (FN + TP)
Human oversight
The proposed operating model treats the application as AI-assisted
decision support, not an autonomous agricultural diagnostic authority.
  Scenario                            Human responsibility
  Normal prediction                   Consider the AI result alongside
                                      field context

  Unknown                             Retake the image or seek assistance

  AI/field disagreement               Do not automatically defer to the
                                  AI; retake and/or escalate
An important design principle is that Unknown does not mean Healthy.
Monitoring and oversight
The proposed monitoring plan covers the AI system rather than model
accuracy alone.

Key indicators include:
- field false-negative rate;
- FAW recall;
- Unknown/rejection rate;
- AI-field disagreement rate;
- performance by location;
- user comprehension failure rate;
- out-of-scope use;
- open AI incidents;
- overdue corrective actions;
- unapproved material changes;
- data-lineage exceptions; and
- integrity-verification failures.
Monitoring uses a proposed Green / Amber / Red escalation model.
Numerical thresholds are intentionally not invented; they should be
established using field validation, agronomic expertise, operational
evidence and consequence severity.
Data and model governance
The assessment proposes a Dataset Register and Model Registry to
support traceability.

A production artifact should be traceable through:

Model version → Dataset version → Validation evidence → Approval →
Deployed application version

Material model, data, preprocessing, geographic-scope or application
changes should pass through:

Change request → Impact assessment → Risk review → Validation →
Governance approval → Deployment → Enhanced monitoring
NIST AI RMF mapping
  Function                            Application
  GOVERN                          Accountability, risk ownership,
                                      incidents, change control,
                                      registers and evidence

  MAP                             Purpose, stakeholders, context,
                                      foreseeable misuse and potential
                                      harms

  MEASURE                         Model/field evaluation, KRIs,
                                      regional performance and
                                      control-effectiveness monitoring

  MANAGE                          Risk prioritisation, treatments,
                                      escalation, residual risk and
                                  deployment decisions
The lifecycle is treated as:

Assess → Decide → Monitor → Learn → Reassess
Key findings
1. High model accuracy does not eliminate operational risk.
2. Failure modes should be prioritized according to consequences, not
   aggregate accuracy alone.
3. AI governance extends beyond the model to users, inputs, data,
   deployment context and organizational accountability.
4. Human oversight must define responsibilities and escalation, not
   simply claim a "human in the loop."
5. Safe uncertainty can be preferable to forced prediction.
6. Monitoring must lead to investigation, escalation and corrective
   action.
7. Governance must continue throughout the AI lifecycle.
Portfolio artifacts
The full case study includes:
- AI system profile and intended-use statement
- stakeholder and harm analysis
- 11-risk AI Risk Register
- priority Risk Treatment Plan
- AI Monitoring & Oversight Plan
- incident-management model
- Dataset Register template
- Model Registry template
- change-control workflow
- governance roles and accountability
- NIST AI RMF crosswalk
- AI Incident Record template
- AI Change Record template
- Periodic AI Governance Report template
Disclaimer
This is a retrospective AI governance assessment of a system
originally developed as academic research. Technical results attributed
to the MSc project reflect the original research evidence. Governance
structures, risk scores, treatment plans, monitoring mechanisms and
control recommendations were developed subsequently for this portfolio
and should not be interpreted as controls necessarily implemented during
the original MSc study.
