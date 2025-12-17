Two Ways to Improve Portrait Generation in InfiniteYou: Base Model Replacement + anti-realism LoRA

\section*{InfiniteYou-schnell}

This work studies how to \textbf{accelerate InfiniteYou} for personalized image generation under low-step diffusion.

We replace the original backbone \textbf{FLUX.1-dev} with \textbf{FLUX.1-schnell} and introduce a lightweight \textbf{Realism LoRA} to reduce quality degradation at low sampling steps.
The identity injection module (\textbf{InfuseNet}) is kept unchanged.

\subsection*{Key Observations}
\begin{itemize}
\item FLUX.1-schnell achieves approximately \textbf{2--3$\times$ faster inference} at 1--4 diffusion steps.
\item Image quality degrades noticeably at very low steps (1--2).
\item Realism LoRA improves visual realism and texture details.
\item \textbf{4 steps with FLUX.1-schnell + Realism LoRA} provides the best speed--quality balance.
\end{itemize}

\subsection*{Experimental Setup}
\begin{itemize}
\item Steps: 1--4 / 32
\item GPU: NVIDIA A100
\item Precision: BF16
\item Timing: averaged over 50 runs
\end{itemize}

\subsection*{Notes}
This work is intended for \textbf{research exploration} of speed--quality trade-offs rather than production use.

\subsection*{References}
InfiniteYou (2025), FLUX.1 (2024), LoRA (ICLR 2022).

