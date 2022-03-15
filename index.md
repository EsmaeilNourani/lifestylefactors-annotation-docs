---
layout: entry
title: Documentation for Lifestyle Relation Annotation
---

## Annotation scope

The scope of this annotation is to detect lifestyle factors which affect the risk of disease onset and development. Below are some general examples of the guidelines that will be used in the annotation.

## General guidelines

* Annotations should be made according to the annotator’s best understanding of the __author’s intended meaning in context__. 
* Annotators should treat named entities as being __masked__, i.e. they shouldn't annotate relationships between entities just based on their names, when they would be unable to make the same annotations for two other entities.

### What to annotate:

1. Causal relationship: _LSF causes disease_ / _disease causes LSF_.
Examples:
    * A __LSF__ causes a __disease__.
    * A __LSF__  contributes to the development of a __disease__.  
    * A __LSF__  developed a __disease__.
    * A __LSF__ is a recognized/reversible/know/common cause of a __disease__
    * __LSF__-induced __DIS__
    * A __LSF__ may induce a __DIS__.
    * A __disease__ is a result/side-effect of a __LSF__.
    * A __disease__ is attributed to / transmitted by / determined by a __LSF__.
    * The consequences of a __LSF__ is a __disease__.
    * (Subject to final IAA results) A __disease__ survivors suffer from a __LSF__.


2. Statistically associated relationship: _LSF is statistically associated with disease_. 
Examples:
    * A __LSF__ is associated with a __disease__.
    * A __LSF__ is associated with the risk of a __disease__.

    2.1 Positive statistical association:
      * A __LSF__ increases the risk of a __disease__.
      * A __LSF__ is the risk factor a __disease__.
      * A __LSF__ carries a risk of a __disease__.
      * A __LSF__ is a predictor of a __disease__.
      * A __disease__ is characterized by a __LSF__.
      * survivors/patients with __disease__ were more likely to be __LSF__.
      * A __LSF__ increases incidence of a __disease__.
      * A __LSF__ increases prevalence of a __disease__. But prevalence without any statistical significance testing should not be annotated.
      * A __LSF__ contributes to the burden of a __disease__.

    2.2 Negative statistical association:
      * A __LSF__ decreases the risk of a __disease__.
      * A __LSF__ decreases incidence of a __disease__.
      * A __LSF__ decreases prevalence of a __disease__.
      * A __LSF__ used as defense for a __disease__. → implied risk reduction.
      * A __LSF__ could be critical in the current fight against __disease__.
      * A __LSF__ is inversely associated with a __disease__.
      
3. Controls: _LSF controls disease_. Examples:
    * A __LSF__ play a regulatory role in __disease__.
    * A __LSF__ has beneficial effect for the control of __disease__. 
    * A __LSF__ is associated with __disease__ treatment and control.

    3.1 Prevents relationship: _LSF prevents disease_ / _disease prevents LSF_. Examples:
     * A __LSF__ is therefore imperative for preventing a __disease__ morbidity and mortality.
     * A __LSF__ is chemopreventive in a __disease__.
     * A __LSF__ is protected against a __disease__.

    3.2 Therapeutic relationship: _LSF treats disease_.
    Examples:
     * The treatment of a __disease__ includes a __LSF__.
     * A __LSF__ is essential for treating a __disease__.
     * A __LSF__ is used for the therapy of a __disease__.
     * The efficacy of a __LSF__  in __disease__.
     * A __LSF__ is the relief of a __disease__.

4. No statistical association: _LSF is not associated with disease_. Examples:
    * A __LSF__ is **not** associated with a __disease__.
    * There is no association between __LSF__ and __disease__.
    * There is a association between __LSF__ and __disease__, but **no significance**.

### What **NOT** to annotate:
1. Hypothetical statements: 

    “Here we study the link between LSF and disease”
    
2. No statistical significance: 

    “We **did not** find the relationship between LSF and disease to be statistically significant”

    _or_

    No statement about a correlation or statistical significance:
    
    “A majority percentage of HIV-positive MSM engage in unprotected sexual behavior”. → other individuals without HIV could have the same behavior.

    _or_

    Observation:

    “Cannabis is the most widely used illicit substance in the United States with especially high prevalence of use among those with psychiatric disorders.”

3. LSF that is a part of a bigger Named entity: sleep in multiple sleep latency test (MSLT)
4. Do NOT annotate "... in/among LSF/DIS":

    __Dairy farmers__ is not part of relation: Among __dairy farmers__, moreover, __lung cancer__ SMRs showed a significant downward trend across the quartiles of increasing __length of work__.

5. Statistical associations should not be annotated if p-value is greater than 0.05.


### Special rules for relationships:
1. Across sentence boundaries should be annotated.
2. “Is believed” should be annotated.

    "Air pollutants are believed to induce or exacerbate a range of inflammatory diseases (atopic dermatitis..."
3. Expression like "limited evidence" should be annotated.

    "Results provide limited evidence for an association of early-life mobile source air pollution with childhood asthma incidence ..."
4. Animal experiments should be annotated, as they are supposed to be a model for a human disease.

5. Be careful with an occupation + a clause with LSFs. 

    In the following examples, farmers __should not__ be linked with acute lymphatic or chronic lymphatic leukemia. 

    "Farmers from major corn-producing, hog- and chicken-raising, and pesticide- and fertilizer-using counties tended to be at higher risk of acute lymphatic.

    "Farmers from counties with large cattle inventories and significant dairy activity were at higher risk of chronic lymphatic leukemia."

6. Annotate what the sentence says, even if there are contradictory statement. Example:
    
    Previous study shows A causes B… : annotate A Cause B.

    In contrast to the previous study, A causes C, or C causes B or no relation… : annotate either A causes C, C causes B or nothing

7. Mentions of “the X-Y association” between an LSF X and a disease Y should be annotated as statistically associated relationships.

1. Indirect relations should be annotated.

2. Relationships like the following: 

    __LSF1__ and __LSF2__ when present together cause disease __disease__, but when __LSF1__ is present alone it **does not** cause __disease__.
    
    Annotate as _LSF1 causes disease_, _LSF2 causes disease_  and negative for LSF1.


4. Compared/comparison: annotate the relationships with the reverse SA type and add a Note: “rel=comparison”.

5. Annotate relationships even when they are not independent.

### Special rules for entities:
1. Top-level terms (e.g. nutrition) should be annotated – even if relationships cannot be annotated for these terms.

8. Standalone adjectives that are not part of named entities should be blacklisted (e.g. nutritional, occupational etc).

9. Adjectives that are used to describe a disease, but are not part of the official nomenclature should not be annotated (e.g. for “occupational asthma” only the word “asthma” should be annotated as a disease) – following from rule 2.

10. Chemical terms should be annotated as standalone entities, and “exposure” should not be annotated as part of these named entities.

11. Lifestyle factor or disease names are annotated when they are part of hyphenated compound words (e.g. **asthma**-causing) but **NOT** when they appear as a substring in a word not separated by a boundary such as a hyphen (e.g. **asthma**tic)

12. Abbreviations are marked if the abbreviation stands for a disease or an LSF mention in scope of the annotation, but not if the full form merely includes an entity mention (e.g. in modifier position. For example, the A in OA is not annotated despite it standing for asthma.)

13. Pregnancy, menopause and puberty are not LSF.

14. Chemicals should be annotated as LSF if they are common, or directly available for ingest as food/supplement, or exposure (even indirect). Examples:
    * sugar intake
    * concentrations of Vitamins A
    * Vitamin D supplements
    * serum Vitamin D levels
    * exposure to dioxins
   
15. Chemicals should NOT be annotated as LSF if they are normally metabolized in the body. Examples:
    * HDL-cholesterol concentrations
    * serum Vitamin D 25-OH levels
    * fasting glucose
   
16. Score/index related to diseases can be annotated as disease and score/index related to LSF can be annotated as LSF. Examples:
    * peripheral neuropathy score
    * sleep quality score

17. Do not annotate all treatments. Only keep psychotherapy and entities related to it (e.g., CBT).
   



### Detailed guidelines

For information on Annodoc, see <http://spyysalo.github.io/annodoc/>.
