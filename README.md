# A proof review of *The Music of the Primes*

This repository examines the proposed proof of the Riemann hypothesis in Alessandro Maria Masullo’s 940-page manuscript. The reports, and this repository, were prepared with Codex GPT Astra 6.2, using two GPT Pro reviews as starting points. [Manuscript PDF](literature/the-music-of-the-primes.pdf) The prompting was done by Eric Naslund, the repository owner.

**Why the calculation at the prime 2 fails (pp. 495–496).** Choose a smooth weight that equals 1 at norm 2 and vanishes outside the interval $(1.9,2.1)$. Among the powers of 2, only 2 contributes, so Theorem 11.3.2.1 gives $\log 2$. To obtain that value, the proof takes a limit of integrals in equation (11.3.2.3). One factor in the integral selects points where the exponent of 2 is nonzero. Once the cutoff reaches the prime 2, a second factor requires that same exponent to be zero. No point satisfies both conditions. Every subsequent integral is therefore zero, so their limit cannot be $\log 2$.

**What the manuscript needs to prove (p. 520).** For the Riemann zeta function, a classical formula relates a sum over primes to a weighted sum over all its nontrivial zeros. The Riemann hypothesis (RH) says that every one of those zeros has real part exactly $1/2$. The manuscript claims that the same formula holds if it includes only the zeros whose real parts lie in an arbitrarily narrow interval around $1/2$. Its proof never shows why it can omit any zeros outside that interval.

**What our attempted repair proves.** We recover the formula with all the zeros included. When we narrow the interval, our formula has an extra term that accounts for the zeros left out. For example, a hypothetical zero with real part $0.6$ would fall outside the interval $(0.49,0.51)$, and a suitable choice of weight would make the extra term nonzero. To finish the proof, we would have to show that this term vanishes for every allowed weight, however narrow the interval. That would rule out every zero off the line, which is exactly RH. This step remains open.

**Why the attempted repair stopped.** We tried two ways to show that the extra term vanishes.

- **Start with a wide interval and shrink it.** In a model built from the manuscript’s test functions, we deliberately inserted two zeros at $0.4$ and $0.6$, preserving the symmetry about $1/2$. For a fixed positive weight, the pair contributes the same positive amount at every width that includes it, then contributes zero once the interval excludes it. Symmetry and agreement over a whole range of wider intervals therefore cannot guarantee the same answer for narrower ones.
- **Estimate the error using the primes.** After accounting for prime squares and higher powers, we compared a weighted sum of primes in a moving interval with its predicted value. If the absolute error stayed below one fixed number as the interval moved to larger primes, RH would follow. Our estimate shows that the *percentage* error tends to zero. Because the predicted value grows, even a shrinking percentage error can correspond to an unbounded *absolute* error. The estimate therefore still allows the kind of growth an off-line zero would cause. [Repair report, pp. 7 and 11–12](review/trace-formula-repair.pdf)

## Reports

| Report | Contents | Files |
| --- | --- | --- |
| *Where the trace argument in The Music of the Primes fails* | Start here. The 10-page report gives the counterexamples, the manuscript equations they contradict, and the limits of the repairs. | [PDF](review/trace-formula-obstructions.pdf) · [LaTeX](review/trace-formula-obstructions.tex) |
| *An adversarial review of The Music of the Primes* | The 17-page audit follows the proof on p. 520 inference by inference, examines its supporting lemmas, and develops a partial repair of the spectral argument. | [PDF](review/proof-audit.pdf) · [LaTeX](review/proof-audit.tex) |
| *An attempted repair of the prime trace formula* | The 12-page follow-up derives the correction for a narrower strip and gives an explicit smoothed sum over primes whose boundedness is equivalent to RH. | [PDF](review/trace-formula-repair.pdf) · [LaTeX](review/trace-formula-repair.tex) |

The page index covers all 940 manuscript pages. The line-check table locates statements, equations, and cross-references by physical page and line of the text extracted with `pdftotext -layout`. The independent mathematical checks focus on the main proof and selected supporting results. [Page index](review/page-index.tsv) · [Line checks](review/line-checks.tsv)

## GPT Pro conversations

| Review | Shared conversation | Repository transcript |
| --- | --- | --- |
| 1 | [GPT Pro conversation 1](https://chatgpt.com/share/6b009dd5-489c-83eb-89a0-fe1bb9e24af1) | [conversation-1.md](gpt-pro-conversations/conversation-1.md) |
| 2 | [GPT Pro conversation 2](https://chatgpt.com/share/6b009ddf-1e14-83ed-b160-de3046ef4190) | [conversation-2.md](gpt-pro-conversations/conversation-2.md) |
