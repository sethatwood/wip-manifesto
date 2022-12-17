[![License: CC0-1.0](https://licensebuttons.net/l/zero/1.0/80x15.png)](http://creativecommons.org/publicdomain/zero/1.0/)

# Work in Progress: A Software Engineering Manifesto

![seeing](https://dojo.electrickettle.fr/files/gimgs/35_Mangouste.gif)

All contents herein are written with the aid of [ChatGPT](https://openai.com/blog/chatgpt/)'s Assistant, starting with this introductory quote:

> In a world where humans and artificial intelligence must work together to navigate the complex world of software engineering, one man embarks on a journey to write the ultimate guide. Alongside ChatGPT, the most advanced AI the world has ever seen, Seth Atwood takes on the daunting task of creating "Work in Progress: A Software Engineering Manifesto." Will they succeed in their quest to demystify the art of code and guide software engineers to greatness? 
>
> Find out in the highly anticipated collaboration between man and machine.
> 
> —Assistant

## Table of Contents
1. [Introduction](Introduction.md)
    - [Overview of software engineering philosophy](Introduction.md#overview-of-software-engineering-philosophy)
    - [The importance of code quality and maintainability](Introduction.md#the-importance-of-code-quality-and-maintainability)
2. [Code is a liability, not an asset](Code-is-a-liability.md)
    - [The cost of maintaining and updating code over time](Code-is-a-liability.md#the-cost-of-maintaining-and-updating-code-over-time)
    - [The importance of minimizing code debt](Code-is-a-liability.md#the-importance-of-minimizing-code-debt)
3. [Own code added, altered, removed, and reviewed](Own-code-added-altered-removed-and-reviewed.md)
    - [The importance of understanding and documenting your own code](Own-code-added-altered-removed-and-reviewed.md#the-importance-of-understanding-and-documenting-your-own-code)
    - [The benefits of peer review](Own-code-added-altered-removed-and-reviewed.md#the-benefits-of-peer-review)
4. [Double-check things. Twice.](Double-check-things.md)
    - [The importance of thorough testing and debugging](Double-check-things.md#the-importance-of-thorough-testing-and-debugging)
    - [The consequences of skipping these steps](Double-check-things.md#the-consequences-of-skipping-these-steps)
5. [Dead code is live code](Dead-code-is-live-code.md)
    - [The cost of maintaining unused or unnecessary code](Dead-code-is-live-code.md#the-cost-of-maintaining-unused-or-unnecessary-code)
    - [The importance of regularly reviewing and removing dead code](Dead-code-is-live-code.md#the-importance-of-regularly-reviewing-and-removing-dead-code)
6. [Never ship new errors](Never-ship-new-errors.md)
    - [The importance of thorough testing and debugging](Never-ship-new-errors.md#the-importance-of-thorough-testing-and-debugging)
    - [The consequences of releasing code with errors](Never-ship-new-errors.md#the-consequences-of-releasing-code-with-errors)
7. [Never code before required](Never-code-before-required.md)
    - [The dangers of over-engineering and over-complicating solutions](Never-code-before-required.md#the-dangers-of-over-engineering-and-over-complicating-solutions)
    - [The benefits of only coding what is strictly necessary](Never-code-before-required.md#the-benefits-of-only-coding-what-is-strictly-necessary)
8. [Never code more than required](Never-code-more-than-required.md)
    - [The dangers of over-engineering and over-complicating solutions](Never-code-more-than-required.md#the-dangers-of-over-engineering-and-over-complicating-solutions)
    - [The benefits of simplicity and minimalism in code](Never-code-more-than-required.md#the-benefits-of-simplicity-and-minimalism-in-code)
9. [Favor subtraction over addition](Favor-subtraction-over-addition.md)
    - [The benefits of removing unnecessary or redundant code](Favor-subtraction-over-addition.md#the-benefits-of-removing-unnecessary-or-redundant-code)
    - [The dangers of feature bloat](Favor-subtraction-over-addition.md#the-dangers-of-feature-bloat)
10. [Favor reduction in scope](Favor-reduction-in-scope.md)
    - [The benefits of focusing on smaller, well-defined problems](Favor-reduction-in-scope.md#the-benefits-of-focusing-on-smaller-well-defined-problems)
    - [The dangers of trying to solve too many problems at once](Favor-reduction-in-scope.md#the-dangers-of-trying-to-solve-too-many-problems-at-once)
11. [Favor explicitness](Favor-explicitness.md)
    - [The benefits of clear, concise, and self-explanatory code](Favor-explicitness.md#the-benefits-of-clear-concise-and-self-explanatory-code)
    - [The dangers of implicit or ambiguous code](Favor-explicitness.md#the-dangers-of-implicit-or-ambiguous-code)
12. [Avoid reinventing wheels](Avoid-reinventing-wheels.md)
    - [The benefits of leveraging existing solutions and libraries](Avoid-reinventing-wheels.md#the-benefits-of-leveraging-existing-solutions-and-libraries)
    - [The dangers of re-creating existing solutions from scratch](Avoid-reinventing-wheels.md#the-dangers-of-re-creating-existing-solutions-from-scratch)
13. [Avoid cleverness](Avoid-cleverness.md)
    - [The benefits of simple, straightforward solutions](Avoid-cleverness.md#the-benefits-of-simple-straightforward-solutions)
    - [The dangers of over-complicating solutions with clever tricks](Avoid-cleverness.md#the-dangers-of-over-complicating-solutions-with-clever-tricks)
14. [YAGNI (You Ain't Gonna Need It)](YAGNI.md)
    - [The benefits of only implementing features that are actually needed](YAGNI.md#the-benefits-of-only-implementing-features-that-are-actually-needed)
    - [The dangers of over-engineering and over-complicating solutions](YAGNI.md#the-dangers-of-over-engineering-and-over-complicating-solutions)
15. [Beware scope creep](Beware-scope-creep.md)
    - [The dangers of continually adding new features or requirements to a project](Beware-scope-creep.md#the-dangers-of-continually-adding-new-features-or-requirements-to-a-project)
    - [The importance of clearly defining and sticking to project scope](Beware-scope-creep.md#the-importance-of-clearly-defining-and-sticking-to-project-scope)
16. [Beware premature optimization](Beware-premature-optimization.md)
    - [The dangers of optimizing code or algorithms before they are actually needed](Beware-premature-optimization.md#the-dangers-of-optimizing-code-or-algorithms-before-they-are-actually-needed)
    - [The importance of measuring performance and optimizing where necessary](Beware-premature-optimization.md#the-importance-of-measuring-performance-and-optimizing-where-necessary)
17. [Beware premature abstraction](Beware-premature-abstraction.md)
    - [The dangers of abstracting code or solutions before they are actually needed](Beware-premature-abstraction.md#the-dangers-of-abstracting-code-or-solutions-before-they-are-actually-needed)
    - [The importance of only abstracting when it provides clear benefits](Beware-premature-abstraction.md#the-importance-of-only-abstracting-when-it-provides-clear-benefits)
18. [Beware the sunk cost fallacy](Beware-the-sunk-cost-fallacy.md)
    - [The dangers of continuing to work on a project or feature due to previous time and effort invested](Beware-the-sunk-cost-fallacy.md#the-dangers-of-continuing-to-work-on-a-project-or-feature-due-to-previous-time-and-effort-invested)
    - [The importance of evaluating the costs and benefits of continuing versus starting fresh](Beware-the-sunk-cost-fallacy.md#the-importance-of-evaluating-the-costs-and-benefits-of-continuing-versus-starting-fresh)
19. [It takes as long as it takes](It-takes-as-long-as-it-takes.md)
    - [The importance of taking the time to do things correctly and thoroughly](It-takes-as-long-as-it-takes.md#the-importance-of-taking-the-time-to-do-things-correctly-and-thoroughly)
    - [The dangers of rushing or cutting corners](It-takes-as-long-as-it-takes.md#the-dangers-of-rushing-or-cutting-corners)
20. [Revisit original premisses](Revisit-original-premisses.md)
    - [The importance of regularly revisiting and reevaluating the assumptions and goals of a project](Revisit-original-premisses.md#the-importance-of-regularly-revisiting-and-reevaluating-the-assumptions-and-goals-of-a-project)
    - [The benefits of adapting to changing circumstances or requirements](Revisit-original-premisses.md#the-benefits-of-adapting-to-changing-circumstances-or-requirements)
21. [First Problem != Real Problem](First-Problem-not-Real-Problem.md)
    - [The importance of accurately identifying and addressing the root cause of a problem](First-Problem-not-Real-Problem.md#the-importance-of-accurately-identifying-and-addressing-the-root-cause-of-a-problem)
    - [The dangers of solving the wrong problem or treating symptoms rather than causes](First-Problem-not-Real-Problem.md#the-dangers-of-solving-the-wrong-problem-or-treating-symptoms-rather-than-causes)
22. [DX+ = UX+](DX-equals-UX.md)
    - [The importance of considering the development experience (DX) and user experience (UX) of code and solutions](DX-equals-UX.md#the-importance-of-considering-the-development-experience-dx-and-user-experience-ux-of-code-and-solutions)
    - [The benefits of optimizing for both DX and UX](DX-equals-UX.md#the-benefits-of-optimizing-for-both-dx-and-ux)
21. [First Problem != Real Problem](First-Problem-not-Real-Problem.md)
    - [The importance of accurately identifying and addressing the root cause of a problem](First-Problem-not-Real-Problem.md#the-importance-of-accurately-identifying-and-addressing-the-root-cause-of-a-problem)
    - [The dangers of solving the wrong problem or treating symptoms rather than causes](First-Problem-not-Real-Problem.md#the-dangers-of-solving-the-wrong-problem-or-treating-symptoms-rather-than-causes)
22. [DX+ = UX+](DX-equals-UX.md)
    - [The importance of considering the development experience (DX) and user experience (UX) of code and solutions](DX-equals-UX.md#the-importance-of-considering-the-development-experience-dx-and-user-experience-ux-of-code-and-solutions)
    - [The benefits of optimizing for both DX and UX](DX-equals-UX.md#the-benefits-of-optimizing-for-both-dx-and-ux)
23. [👁️ (open your eyes)](Open-your-eyes.md)
    - [The importance of staying open-minded and receptive to new ideas and approaches](Open-your-eyes.md#the-importance-of-staying-open-minded-and-receptive-to-new-ideas-and-approaches)
    - [The benefits of actively seeking out new knowledge and perspectives](Open-your-eyes.md#the-benefits-of-actively-seeking-out-new-knowledge-and-perspectives)
24. [You are not your code](You-are-not-your-code.md)
    - [The importance of separating personal identity from code](You-are-not-your-code.md#the-importance-of-separating-personal-identity-from-code)
    - [The dangers of becoming too attached or identified with your code](You-are-not-your-code.md#the-dangers-of-becoming-too-attached-or-identified-with-your-code)
25. [Forget everything](Forget-everything.md)
    - [The importance of regularly learning and adapting to new technologies and approaches](Forget-everything.md#the-importance-of-regularly-learning-and-adapting-to-new-technologies-and-approaches)
    - [The dangers of becoming too attached to old ways of doing things](Forget-everything.md#the-dangers-of-becoming-too-attached-to-old-ways-of-doing-things)
26. [Conclusion](Conclusion.md)
    - [Summary of key points](Conclusion.md#summary-of-key-points)
    - [Final thoughts](Conclusion.md#final-thoughts)
