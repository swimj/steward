# Week of October 12–18, 2026

## Make improved teaching and practice content reach the learners who need it

This week's sole focus is the content update and repair model. Improving content must lead to a better experience for learners who already encountered it, including teaching and Practice content.

Settle who receives a correction, when they receive it, what progress carries forward, and how shared corrections differ from personal preferences. Ground the model in real disappointing content and use those cases to bound the adoption, sharing, and recovery support needed.

**Done:** an agreed model and a bounded first delivery slice, grounded in real cases. If implementation fits this week, prove one correction reaching an already-affected learner during ordinary study, with history and progress intact.

### Supporting validation — a thin slice of SWI-77

Include observability and validation in the delivery slice: connect the original problem and exact revision to what the affected learner actually receives, then assess whether the original complaint persists. Significant features should come with a practical way to observe their behavior and validate their intended outcome.

**Done for the model:** the slice specifies the evidence needed to verify adoption and assess the subsequent experience. **Done for a shipped slice:** demonstrate that evidence on a real correction, distinguishing successful delivery, perceived content improvement, and evidence of better learning. Immediate answer accuracy alone does not establish learning effectiveness.

Keep this bounded to the practical assessment in [SWI-77](https://linear.app/swimj/issue/SWI-77); a general experimentation platform is outside this week's scope.

## Keep the focus bounded

- Let one concrete teaching/Practice repair determine the necessary infrastructure.
- Treat separating learner-facing teaching from background repair as a design constraint; completing that transition is not required this week.
- Resume manual content improvements and the separate generation-improvement loop after the update/repair foundation is ready.
- Keep other product initiatives outside this week's focus.

**Reorientation question:** Does this work help an affected learner receive better content, or provide the evidence needed to know that it worked?
