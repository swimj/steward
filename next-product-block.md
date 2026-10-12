# Next product block

October 12, 2026. A direction to keep chewing on while finishing the current content-improvement work; the scope and timing are still open.

## Directions in view

1. **A thin software factory for small and medium work.** Dogfooding keeps producing useful fixes alongside deeper product work. Make it easy to send an idea through to a tested, reviewable result, or have it stop and escalate when it needs judgment. Justin keeps the final merge and a focused review surface. Some investment here is useful alongside whichever major block comes next.
2. **Improve teaching and practice content for existing learners.** Poor content currently tends to stick for the people who encounter it. New learners spend especially much of their time here, so this shapes their first impression. Extending the review-content improvement loop needs a holistic look at the different teaching/practice models, including how learners actually receive a repair.
3. **Separate exercise repair from post-session teaching.** Working through proposals is laborious, and manual review is a weak guarantee of quality. The lean is toward useful lessons for the learner and an iterative repair process behind the scenes. More deliberate AI workflow decisions could support this; an in-session second opinion on an unfair cue is a possible later extension.
4. **Admit work to a study budget.** A bounded session could feel more approachable than an entire due payload while still respecting SRS urgency. This is the strongest independent alternative to the content-quality block. More personalized session composition would stay outside its first version.
5. **Let learners influence content without owning the machinery.** People differ in preferred detail, examples, and presentation, and may need room to discover what helps them. Variation above a core workflow could let useful content strategies emerge beyond Justin's prompt tuning. Separating repair from teaching would give those preferences a clearer place to live.
6. **Evolve sharing, pinning, and private variation.** Several directions put pressure on today's simple sharing policies. Prefer letting a concrete product need drive the next step, with attention to where it will generalize, rather than designing the whole sharing model in advance.
7. **Measure whether changes improve learning.** Build toward evidence that a repair helps a learner, and eventually comparisons between content or prompt strategies. This is a supporting capability with a larger future, not a prerequisite to build a full experimentation platform now.
8. **Keep the current exercise repertoire.** Initial beta experience suggests it is adequate for the product's present usefulness. Enrichment has room to grow but is not the current bottleneck.

## Lean: teaching/practice improvement plus reflection separation

Directions 2 and 3 look like one coherent next major block. Improving more content matters only if affected learners get a better experience; moving repair out of the learner's way matters only if the system can carry that responsibility reliably. Together they address a visible quality gap and move closer to the [vision](vision.md): the learner brings their experience, and the app takes responsibility for practice and its adjustment.

The desired behavior is straightforward: a learner encounters poor teaching or practice, expresses confusion or dissatisfaction naturally, and the system can improve what they receive without turning them into an editor. Post-session teaching should remain worthwhile in its own right, even when there is nothing to repair. Trust comes from a repair process that can notice, recover, and improve over time, rather than expecting a person to catch every mistake in a one-shot proposal.

A thin version of direction 1 can run alongside this to reduce the cost of everyday dogfood fixes. Direction 4 remains a worthwhile alternative, but does not need to become part of this block. The existing [staged reflection workflow](https://github.com/swimj/chinese-study-app/blob/main/SPECS/session-reflection-generation.md#staged-production-cue-cleanup) and [independent debrief](https://github.com/swimj/chinese-study-app/blob/main/SPECS/session-debrief.md) are useful footholds; the direction does not imply a full rewrite.

## What needs to line up

### Repairs have to reach the learner

Content identity, revisions, and adoption need enough clarity that publishing a better version leads to better future study. Under the current [serving model](https://github.com/swimj/chinese-study-app/blob/main/docs/word-content-serving.md), existing eligible teaching pins normally keep serving the old package, and introduction completion belongs to the exact package. A successor can already be opened explicitly through the API; the gap is in the ordinary serving and adoption experience, not an absolute inability to reach new content.

Adoption must also respect what the learner has done. Replacing a package should not casually replay completed work or erase progress. Adopting a revision should respect study progress, with a deliberate policy for carrying introduction completion forward and frozen sessions preserved. These are adoption behaviors to work toward; storage architecture is still open.

### Correction and taste need different treatment

A generally misleading cue or explanation can justify a shared correction. A preference for more detail or a different style may belong to one learner or a private variant. Keeping that distinction clear connects this block to directions 5 and 6 without requiring a complete personalization or sharing platform first.

Learners should be able to say what felt wrong in ordinary language. The system then needs a dependable way to distinguish explanation, content repair, and preference, and to route uncertainty appropriately. Typed decisions, including a Jev-style approach, are candidates for making that workflow clearer; neither a particular framework nor its Chinese-language performance is settled by this direction.

### Autonomy needs recovery and boundaries

Low-risk changes to future teaching content should be distinguishable from changes to answer keys, suppression, grading consequences, or scheduling. The repair process needs enough inspection, history, and recovery to diagnose a bad change and improve it again. This is where a bounded practical slice can clarify which protections matter, rather than requiring every learner to scrutinize every proposal.

### Measure what the learner actually received

A thin evidence trail should connect an improvement to the exact content a learner saw and to subsequent learning. Higher accuracy immediately after a repair might mean an easier cue, not stronger learning. Delayed, reasonably independent checks matter before claiming effectiveness. Start with enough visibility to judge the practical slice; broader prompt comparisons and A/B testing can grow from it.

The useful overlap is therefore fairly contained: a teaching/practice repair that reaches the affected learner can motivate the necessary adoption, sharing, recovery, and evidence work. It does not require solving all of directions 5–7 before the experience can improve.

## Appendix: original note

on the plane back to the US, next few days work budget will be a bit hard to gauge.

the app is fairly stable and while i do need to wrap up the content improvement still, i also want to start thinking about the next major block to start chipping away at. there are a few different things coming into view that could be deserving. let's think through the pros/cons/feasibility/prereqs/doors opened for each, and maybe they overlap 

1) invest in "software factory" setup, at least for small/medium tasks. actually sort of want to do this regardless because i've realized as a result of dogfood, i naturally end up having misc little things i want to improve while also focusing on a more complex subject. would like to decrease friction on this, so i can confidently fire off ideas which can be taken to completion (i still do final merge with potentially a very focused review surface area) or halted and escalated if the idea deserves more attention from me

2) figure out how to do content improvement for teaching/practice. currently users that experience subpar teaching/practice content are more or less locked in. this is particularly bad for new user impression because their time is skewed towards that content. the original choice to keep reflection restricted to review items was somewhat for sake of simplicity but also because there are some essential modeling differences. should take a holistic view of problems and solutions.

3) decouple reflection as exercise improvement and reflection as post-session teaching. this has already been noted in the steward's chewing doc, i myself find working through reflection somewhat laborious but i'm willing to do it for sake of product research / there's no other way to improve my study content experience. originally we had low trust in models but i'm realizing that 1) they are often really good , 2) manual edit and review isn't actually that strong of a guard, 3) content improvement might inherently be an iterative process, so "quality" mistakes shouldn't be fixed via strict scrutiny over one shots but a more robust long term steady improvement process. we also have workflow logic now for agent calls so we can build out a more intentional graph of calls. I also think recent advent of jev decision-style framework could be hugely leveraged for the type of AI workflow reflection is. this also might have implications for the in-session flow, e.g. we might be able to inline judge possibility of unfair cue, rather than waiting til post session, this will be more intuitive for users.

4) moving away from SRS due session payload concept, into something more budget based and personal. have had a few users already note that they could see the due load becoming daunting / noting that time boxing study could be nice for meeting average users. this possibly also opens a door to doing more personalized sessions , but that should be out of scope of the first version. 

5) allow for individualized nudges w.r.t. content generation/serving. it's already becoming apparent that different users have different preferences when it comes to what content they want to see / what level of detail is good / etc. Also people might naturally be unsure and it would be cool if the app gave them a way to experiment with what worked for them. but right now the experience is quite tied to hard coded prompts. so it's basically a reflection of my own taste / amount of attention i can devote to such tuning. it would be nice to switch to a more platform model that allows for some level of user variation on top of a core workflow. perhaps this needs to happen after 3 assuming 3 is needed (i think it is, feel free to push back if you think keeping proposals visible to average users might be essential to long term vision). it would also be a nice way to allow for different content strategies to emerge just from individual users (i.e. i don't have to be driving the experiments by shipping prompt changes and then asking for user feedback). 

6) behind a lot of this is the topic of content sharing, we kind of picked some simple policies to start off but taking a next big product step in any way almost certainly touches on the sharing model, and possibly pulls in different ways. not sure if we should try to define this as its own thing or try to just motivate from a single practical need and then trust that with careful attention we'll be able to converge to a good model.

7) some sort of automated observability on learning effectiveness (i.e. quantitatively measure if a fix helps a learner vs. not, a/b test content generated by different prompts, etc.)

8) what i think is clear from initial beta is that the current exercise set is fine. there is obviously room for enrichment but it is not a limiting factor on anyone's sense of the current usefulness.
