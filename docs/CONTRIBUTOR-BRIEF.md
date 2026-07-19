# Digital DNA Research -- Contributor Brief (v1)

**Human Continuity Institute** -- human-continuity.org
*This is a working draft -- meant to be refined together with the first volunteers, not a finished spec.*

---

## The core idea

If we gather a large, longitudinal set of images and artifacts about one person -- photos across many years, in many contexts -- can we extract a measurable "essence" of that person? Not just a face-recognition profile, but a structured, evolving signature: how they've looked, expressed emotion, spent time, and changed, across a life.

We're calling this a person's **Digital DNA**. This brief exists to turn that idea into something a developer can actually pick up and start building against.

## What we're proposing to build together

A pipeline that takes a personal photo archive as input and produces a structured, machine-readable profile as output -- plus the annotation tooling and schema needed to make that profile meaningful rather than just a pile of tags.

## What "Digital DNA" is made of (draft -- needs your input)

A first cut at the categories we think it should capture. This list is intentionally a starting point for debate, not a final spec:

1. **Physical timeline** -- how appearance changes over years (age progression, style, environment)
2. 2. **Emotional/expression patterns** -- what emotions recur, in what contexts
   3. 3. **Life events & situations** -- weddings, travel, work, family -- clustered from context
      4. 4. **Environments & places** -- where photos were taken, how that shifts over time
         5. 5. **Relationships / social graph** -- who recurs alongside the subject
            6. 6. **Metadata layer** -- timestamps, geolocation, camera data -- the "when/where" skeleton everything else hangs on
              
               7. ## What's already extractable *today* with existing tools
              
               8. This is the realistic starting point -- things off-the-shelf models can already do, which we shouldn't reinvent:
              
               9. - Face detection & basic recognition (clustering "this is probably the same/different person")
                  - - Age estimation
                    - - Emotion/expression classification
                      - - Scene and object detection (already familiar territory -- this overlaps with the YOLOv8/YOLOv12 work published in the IEEE drone-detection research)
                        - - EXIF metadata extraction (timestamp, GPS, camera)
                          - - OCR on any text present in images
                           
                            - ## What we actually want to add (this is where the real objectives live)
                           
                            - The gap between "off-the-shelf tagging" and an actual Digital DNA:
                           
                            - - **Longitudinal aggregation** -- not tagging one photo, but building a model of a *person across hundreds of photos over years*
                              - - **Cross-photo identity consistency** -- linking "this person at 8 years old" to "this person at 30"
                                - - **Emotional trend analysis over time** -- not just "happy in this photo" but patterns across a life
                                  - - **Life-event clustering** -- grouping photos into meaningful episodes automatically
                                    - - **Multi-modal fusion** -- combining photos with any text, voice, or written artifacts the person contributes
                                      - - **A consent-respecting storage & access model** -- this has to be designed alongside the technical pipeline, not bolted on after
                                       
                                        - These open questions are exactly what the first round of developer discussion should pressure-test: what's realistic, what's overkill, what's missing.
                                       
                                        - ## Why a volunteer would want to work on this
                                       
                                        - - A genuinely novel applied CV/ML problem -- not another Kaggle tutorial clone
                                          - - Real chance of co-authorship on a research paper (there's already a publishing track record here -- IEEE work on YOLO-based detection -- this isn't a first attempt at academic output)
                                            - - A letter of contribution / reference from a registered NGO
                                              - - Fully remote, flexible, part-time -- build around your own schedule
                                                - - Early-stage enough that a volunteer's design decisions will actually shape the project, not just implement someone else's spec
                                                  - - A clear social-impact narrative for a portfolio
                                                   
                                                    - ## Proposed first two weeks
                                                   
                                                    - **Week 1 -- Align, don't build yet**
                                                    - - Open the kickoff discussion (GitHub Discussions) with this brief as the starting point
                                                      - - Review a small **synthetic/sample** image set together (not real personal photos) to catalog what current tools can already extract
                                                        - - Evaluate tooling options as a group:
                                                          -   - Managed: Google Cloud Vision API, AWS Rekognition
                                                              -   - Open-source: MediaPipe, DeepFace, InsightFace, CLIP, YOLO (existing expertise here), Detectron2, Hugging Face emotion/scene models
                                                                  - - Draft a first annotation schema -- what fields per image: emotion, activity/situation, people present, location type, approximate era
                                                                   
                                                                    - **Week 2 -- Minimal proof of concept**
                                                                    - - Build a small pipeline on the sample set: ingest -> run detection/annotation models -> output a structured JSON profile
                                                                      - - Review results together as a group, refine the schema based on what actually worked vs. what the models got wrong
                                                                       
                                                                        - ## Open questions for the first discussion thread
                                                                       
                                                                        - - Which of the "what we want to add" objectives above should be phase 1 vs. phase 2+?
                                                                          - - Managed cloud APIs (fast, costs money, less control) vs. open-source models (free, more setup, full control) -- or a hybrid?
                                                                            - - What does the annotation schema actually need to capture to be useful later, without over-engineering it now?
                                                                              - - What's the minimum viable consent/data-handling process before anyone touches real personal photos?
                                                                               
                                                                                - ---
                                                                                *Feedback and edits welcome -- this is meant to be argued with, not accepted as-is.*
                                                                                
