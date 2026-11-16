# Geotechnical Agent Reproducibility

These materials accompany *An AI Agent for Probabilistic Geotechnical Analysis with an Application to Tunnel Support* by Xuanchi Liu.

## Correction to the v6 record

In the original shared-conversation run, X03 and X04 submitted conflicting stage values in their first specification calls. The dispatcher rejected the calls, and the controller then obtained clarification. The records show that sequence and do not establish the controller's intent. The v6 characterization of these two events as deliberate challenges was a retrospective annotation without supporting pre-run documentation. Version 7 withdraws that characterization, preserves the recorded calls and results, and treats the original run and Box 1 as demonstrations conducted with access to the study-building materials.

## Files and replay

The version 7 reproducibility package contains the files described below.

- `agent/` contains the original study instruction, tool contracts, request texts, reference and episode traces, and replay scripts.
- `followup/` contains the new runs, tool-interface transcripts, scoring, and session protocol. Four fresh controller sessions each received four requests. Each saw only the supplied task materials, its current request, and its own tool results through the study interface. The backend source, fault assignments and pre-recorded replies were withheld. Requests within a session shared context.
- `benchmark/` contains the code, synthetic data and vector figures for Experiments 1–3.

With the pinned dependencies in `agent/requirements.txt` installed, run `python agent/evaluate_reference.py`, `python agent/score_episodes.py` and `python followup/score_followup.py` from the extracted archive. These scripts replay the saved calls without invoking a new model. The two historical stage rejections and the three follow-up clarification rejections are reported separately. See `benchmark/README.txt` for numerical benchmark reproduction commands.

## Licenses

Software is distributed under the [MIT License](LICENSE). The synthetic data and experiment records are distributed under [CC BY 4.0](DATA_LICENSE.md).
