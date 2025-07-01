# WithdrarXiv-Check
This repository contains the dataset, model outputs, and experiment code for ["Reviewing Scientific Papers for Critical Problems With Reasoning LLMs: Baseline Approaches and Automatic Evaluation"](https://arxiv.org/abs/2505.23824).

## The WithdrarXiv-Check Dataset
The WithdrarXiv-Check dataset is a filtered subset of [WithdrarXiv](https://github.com/darpa-scify/withdrarxiv). Our data filtering procedure is described in the paper.

You can find 3 CSV files in the "Dataset" folder:
- WithdrarXiv-Check.csv: the full dataset.

  It has 6 columns: retraction_id (arXiv ID of a retraction notice), paper_id (arXiv ID of the retracted paper), subjects (subjects of the paper), title, abstract, and retraction_comment.
- WithdrarXiv-Check_train.csv: the 80% training split.

  It contains 1 additional column for the number of pages of each paper.
- WithdrarXiv-Check_test.csv: the 20% test split we used for our experiments.

  It contains 2 additional columns, one for the number of pages of each paper and the other for whether TeX source scripts are available.

## LLM Outputs
Please see folder "LLM_outputs" which contains 3 subfolders:
- checker_problems/: problems identified by LLM checkers.

  File name: "checker_problems_[CheckerModel]" for the PDF approach and "checker_problems_[CheckerModel]_tex" for the LaTeX approach.
- eval_hit/: hit evaluation outputs by LLM judges.

  File name: "eval_hit_[CheckerModel]\_[JudgeModel]" for the PDF approach and "eval_hit_[CheckerModel]\_tex\_[JudgeModel]" for the LaTeX approach.
- eval_tp/: true positive evaluation outputs by LLM judges.

  File name: "eval_tp_[CheckerModel]\_[JudgeModel]" for the PDF approach and "eval_tp_[CheckerModel]\_tex\_[JudgeModel]" for the LaTeX approach.

## Experiment Code
Please see "experiments.ipynb". We used Python 3.11, but any version above should also work.

## Citation
You can cite our work and the original WithdrarXiv dataset as follows:
```bibtex
@misc{Zhang25LLMCriticalReview,
      title={Reviewing Scientific Papers for Critical Problems With Reasoning {LLMs}: Baseline Approaches and Automatic Evaluation},
      author={Tianmai M. Zhang and Neil F. Abernethy},
      year={2025},
      archivePrefix={arXiv},
      eprint={2505.23824},
      url={https://arxiv.org/abs/2505.23824},
}
@misc{Rao24WithdrarXiv,
      title={{WithdrarXiv}: A Large-Scale Dataset for Retraction Study}, 
      author={Delip Rao and Jonathan Young and Thomas Dietterich and Chris Callison-Burch},
      year={2024},
      eprint={2412.03775},
      archivePrefix={arXiv},
      url={https://arxiv.org/abs/2412.03775}, 
}
```
