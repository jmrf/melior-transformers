# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.18.2+melior1.1.6] - 2019-03-10
### Added
- Makefile to upload package to Melior's Pypi server
- Drone config to upload package to Melior's Pypi server automatically.

### Changed
- Setup to include upload, test, dev and extra requires.

## [0.18.2+melior1.1.5] - 2019-02-04
### Added
- Pre-commit hooks added.

### Changed
- Drone config to run just one instance.

## [0.18.2+melior1.1.4] - 2019-01-29
### Fixed
- Even when `save_model_every_epoch` the las model was not saved. 

## [0.18.2+melior1.1.3] - 2019-01-29
### Fixed
- `os.mkdir` replaced to `os.makedirs` to create all the intermediate directories

## [0.18.2+melior1.1.2] - 2019-01-27
### Fixed
- `shutil.rmtree` error not handled
- `delete_worst_models` was somehow deleted during old merge conflict

## [0.18.2+melior1.1.1] - 2019-01-21
### Added 
- `Makefile` added with `formatter`, `linter` and `test` comands.
- `requirements-dev.txt ` and `requirementes.txt` with new dependecies.
- `sentence-transformers` wrapper to easaly extract embeddings.
- Drone corectly configured.
- Some simple tests.

### Changed
- Renamed library to `melior-transformers`
- Almost all files are formatted, linted and the imports are sorted.

## [0.18.2+melior1.1.0] - 2019-01-16
### Added
- `metric_criteria` and `save_n_best_epochs` parameters added. These allow to save the best model.
- Renamed library to `meliorTransformers`
- `README` and versioning file update
- Added `.drone.yml` placeholder

## [0.18.2] - 2020-01-15
### Added
- Added option to turn off model saving at the end of every epoch with `save_model_every_epoch`.

### Fixed
- Fixed bug with missing `tensorboard_folder` key in certain situations.

### Changed
- Moved `args` items common to all classes to one place (`config/global_args.py`) for maintainability.

## [0.18.1] - 2020-01-15
### Fixed
- Fixed bug with missing `regression` key when using MultiLabelClassification.

## [0.18.0] - 2020-01-15
### Added
- Sentence pair tasks are now supported.
- Regression tasks are now supported.
- `use_cached_eval_features` to `args`. Evaluation during training will now use cached features by default. Set to `False` if features should be reprocessed.

### Changed
- Checkpoints saved at the end of an epoch now follow the `checkpoint-{global_step}-epoch-{epoch_number} format.

## [0.17.1] - 2020-01-14
### Fixed
- Fixed `wandb_kwargs` key missing in `args` bug.

## [0.17.0] - 2020-01-14
### Added
- Added new model XLM-RoBERTa. Can now be used with `ClassificationModel` and `NERModel`.

## [0.16.6] - 2020-01-13
### Added
- Added evaluation scores from end-of-epoch evaluation to `training_progress_scores.csv`.

### Fixed
- Typos in `README.md`.

## [0.16.5] - 2020-01-09
### Fixed
- Reverted missed logging commands to print statements.

## [0.16.4] - 2020-01-09
### Changed
- Removed logging import.

## [0.16.3] - 2020-01-09
### Fixed
- Reverted to using print instead of logging as logging seems to be causing issues.

## [0.16.2] - 2020-01-08
### Changed
- Changed print statements to logging.

## [0.16.1] - 2020-01-07
### Added
- Added `wandb_kwargs` to `args` which can be used to specify keyword arguments to `wandb.init()` method.

## [0.16.0] - 2020-01-07
### Added
- Added support for training visualization using the W&B framework.
- Added `save_eval_checkpoints` attribute to `args` which controls whether or not a model checkpoint will be saved with every evaluation.

## [0.15.7] - 2020-01-05
### Added
- Added `**kwargs` for different accuracy measures during multilabel training.

## [0.15.6] - 2020-01-05
### Added
- Added `train_loss` to `training_progress_scores.csv` (which contains the evaluation results of all checkpoints) in the output directory.

## [0.15.5] - 2020-01-05
### Added
- Using `evaluate_during_training` now generates `training_progress_scores.csv` (which contains the evaluation results of all checkpoints) in the output directory.
## [0.15.4+melior1.0.0] - 2019-01-13
### Fixed
- `sliding_window` removed in order to have direct compatibility with Transformers models.
- `metric_criteria` and `save_n_best_epochs` parameters added. These allow to save the best model.

## [0.15.4] - 2019-12-31
### Fixed
- Fixed bug in `QuestonAnsweringModel` when using `evaluate_during_training`.

## [0.15.3] - 2019-12-31
### Fixed
- Fixed bug in MultiLabelClassificationModel due to `tensorboard_dir` being missing in parameter dictionary.

### Changed
- Renamed `tensorboard_folder` to `tensorboard_dir` for consistency.

## [0.15.2] - 2019-12-28
### Added
- Added `tensorboard_folder` to parameter dictionary which can be used to specify the directory in which the tensorboard files will be stored.

## [0.15.1] - 2019-12-27
### Added
- Added `**kwargs` to support different accuracy measures at training time.

## [0.15.0] - 2019-12-24
### Added
- Added `evaluate_during_training_steps` parameter that specifies when evaluation should be performed during training.

### Changed
- A model checkpoint will be created for each evaluation during training and the evaluation results will be saved along with the model.

## [0.14.0] - 2019-12-24
### Added
- Added option to specify a GPU to be used when multiple GPUs are available. E.g.: `cuda_device=1`
- Added `do_lower_case` argument for uncased models.

### Fixed
- Fixed possible bug with output directory not being created before evaluation is run when using `evaluate_during_training`.

## [0.13.4] - 2019-12-21
### Fixed
- Fixed bug with when using `eval_during_training` with QuestionAnswering model.

## [0.13.3] - 2019-12-21
### Fixed
- Fixed bug with loading Multilabel classification models.
- Fixed formatting in README.md.

## [0.13.2] - 2019-12-20
### Fixed
- Fixed formatting in README.md.

## [0.13.1] - 2019-12-20
### Fixed
- Bug in Multilabel Classification due to missing entries in default args dict.

## [0.13.0] - 2019-12-19
### Added
- Sliding window feature for Binary and Multiclass Classification tasks.

## [0.12.0] - 2019-12-19
### Added
- Minimal examples have been added to the `examples` directory as Python scripts.

### Changed
- Readme updated to include the addition of examples.

## [0.11.2] - 2019-12-18
### Fixed
- Evaluation during training fixed for multilabel classification.

## [0.11.1] - 2019-12-18
### Fixed
- Broken multiprocessing support for NER tasks fixed.

## [0.11.0] - 2019-12-15
### Added
- CamemBERT can now be used with NERModel.

### Changed
- Readme changed to include CamemBERT for NER.

## [0.10.8] - 2019-12-15
### Added
- DistilBERT can now be used with NERModel.

### Changed
- Readme changed to include DistilBERT for NER.

## [0.10.7] - 2019-12-15
### Added
- This CHANGELOG file to hopefully serve as an evolving example of a
  standardized open source project CHANGELOG.

[0.18.2]: https://github.com/ThilinaRajapakse/simpletransformers/compare/1fb47f1...HEAD

[0.18.1]: https://github.com/ThilinaRajapakse/simpletransformers/compare/9698fd3...1fb47f1

[0.18.0]: https://github.com/ThilinaRajapakse/simpletransformers/compare/9c9345f...9698fd3

[0.17.1]: https://github.com/ThilinaRajapakse/simpletransformers/compare/9a39cab...9c9345f

[0.17.0]: https://github.com/ThilinaRajapakse/simpletransformers/compare/0e5dd18...9a39cab

[0.16.6]: https://github.com/ThilinaRajapakse/simpletransformers/compare/c6c1792...0e5dd18

[0.16.5]: https://github.com/ThilinaRajapakse/simpletransformers/compare/e9504b5...c6c1792

[0.16.4]: https://github.com/ThilinaRajapakse/simpletransformers/compare/5d1eaa9...e9504b5

[0.16.3]: https://github.com/ThilinaRajapakse/simpletransformers/compare/f5a7699...5d1eaa9

[0.16.2]: https://github.com/ThilinaRajapakse/simpletransformers/compare/d589b75...f5a7699

[0.16.1]: https://github.com/ThilinaRajapakse/simpletransformers/compare/d8df83f...d589b75

[0.16.0]: https://github.com/ThilinaRajapakse/simpletransformers/compare/1684fff...d8df83f

[0.15.7]: https://github.com/ThilinaRajapakse/simpletransformers/compare/c2f620a...1684fff

[0.15.6]: https://github.com/ThilinaRajapakse/simpletransformers/compare/cd24331...c2f620a

[0.15.5]: https://github.com/ThilinaRajapakse/simpletransformers/compare/38cbea5...cd24331

[0.15.4]: https://github.com/ThilinaRajapakse/simpletransformers/compare/70e2a19...38cbea5

[0.15.3]: https://github.com/ThilinaRajapakse/simpletransformers/compare/a65dc73...70e2a19

[0.15.2]: https://github.com/ThilinaRajapakse/simpletransformers/compare/268ced8...a65dc73

[0.15.1]: https://github.com/ThilinaRajapakse/simpletransformers/compare/2c1e5e0...268ced8

[0.15.0]: https://github.com/ThilinaRajapakse/simpletransformers/compare/aa06528...2c1e5e0

[0.14.0]: https://github.com/ThilinaRajapakse/simpletransformers/compare/785ee04...aa06528

[0.13.4]: https://github.com/ThilinaRajapakse/simpletransformers/compare/b6e0573...785ee04

[0.13.3]: https://github.com/ThilinaRajapakse/simpletransformers/compare/b3283da...b6e0573

[0.13.2]: https://github.com/ThilinaRajapakse/simpletransformers/compare/897ef9f...b3283da

[0.13.1]: https://github.com/ThilinaRajapakse/simpletransformers/compare/1ee6093...897ef9f

[0.13.0]: https://github.com/ThilinaRajapakse/simpletransformers/compare/04886b5...1ee6093

[0.12.0]: https://github.com/ThilinaRajapakse/simpletransformers/compare/04c1c06...04886b5

[0.11.2]: https://github.com/ThilinaRajapakse/simpletransformers/compare/bbc9d22...04c1c06

[0.11.1]: https://github.com/ThilinaRajapakse/simpletransformers/compare/191e2f0...bbc9d22

[0.11.0]: https://github.com/ThilinaRajapakse/simpletransformers/compare/92d08ae...191e2f0

[0.10.8]: https://github.com/ThilinaRajapakse/simpletransformers/compare/68d359f...92d08ae

[0.10.7]: https://github.com/ThilinaRajapakse/simpletransformers/compare/0.10.6...68d359f
