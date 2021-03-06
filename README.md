# DIVER

`Diver` is the `D`ataset `I`nspector, `V`isualiser and `E`ncode`r` library, automating and codifying common data science project steps as standardised and reusable methods.

See `example-notebooks/house-price-demo.ipynb` for a full walkthrough or follow this link: https://tinyurl.com/ye9hfbzp.

<p align="center">
  <img width="460" height="300" src="https://github.com/ClearScore/diver/raw/master/pictures/stingray.jpg">
</p>

## `dataset_inspector`

A set of functions which help perform checks for common dataset issues which can impact machine learning model performance.

![`inspector` flow](https://github.com/ClearScore/diver/raw/master/pictures/inspector_flow.png)

## `dataset_conditioner`

A `scikit-learn`-formatted module which can perform various data-type encodings in a single go, and save the associated attributes from a train-set encoding to reuse on a test-set encoding:
- The `.fit_transform` method learns various encodings (feature means and variances; categorical feature elements - yellow in the flow chart below) and then performs the various encodings on the feature train set
- The `.transform` method applies train-set encodings to a test set

![`fit_transform` flow](https://github.com/ClearScore/diver/raw/master/pictures/readme_flow.png)

## `dataset_visualiser`

Functions for visualising aspects of the dataset

### Correlation analysis
- Display the correlation matrix for the top `n` correlating features (`n` specified by the user) against the dependent variable (at the bottom row of the matrix)

![correlation](https://github.com/ClearScore/diver/raw/master/pictures/correlation.png)

## Latest PyPI Version

- **MAJOR: 0.** - 
- **MINOR: 2.** - New Sklearn single feature missing value imputers (mean, median, zero, most frequent) replace previous manual implementations
- **BUGFIX: 0.** - 


## Future Work

#### `categorical_excess_cardinality_flagger_and_reducer`
- Option for instances where there are no categorical features

#### `missing_value_conditioner`
- Choose between either {use means from train set (default), calculate means for test set}

- Implement missing value imputation: https://measuringu.com/handle-missing-data/

- GOOD READING: https://towardsdatascience.com/6-different-ways-to-compensate-for-missing-values-data-imputation-with-examples-6022d9ca0779

#### `ordinal_encoder`
- Create a function to do this

#### `timestamp_encoder`
- is_public_holiday : bool
  https://pypi.org/project/holidays/
- Update above diagram
- Encode year linked to overall numeric encoding

#### `dataset_inspector` as class
- Memorise training set settings (cardinality reductions, cut features) as attributes in order to apply the same settings to test set
- `fit_transform`/`transform` format as with `dataset_conditioner`

#### Unit test all functions

#### Extreme values

#### Check `infer_useful_cols`
- Seems to be missing timestamps

#### `useful_cols` dtype and filltype dataframe within `inspector`

#### PCA option?

#### Verbose progress bars
- Inspector
- Conditioner

#### Label balanced class checker (for classification problems)
- https://machinelearningmastery.com/tactics-to-combat-imbalanced-classes-in-your-machine-learning-dataset/

#### Distribution and correlation analysis
- Display correlation matrix for top `n` correlates alongside target at the bottom
- Display pairplot for top `n` correlates alongside target at the bottom
- Or instead of `top n` correlates, instead threshold of `cumulative variance`
- Option to DROOP lower correlates (lower than threshold) if desired

## Useful reading
- https://machinelearningmastery.com/process-for-working-through-machine-learning-problems/
- https://towardsdatascience.com/smarter-ways-to-encode-categorical-data-for-machine-learning-part-1-of-3-6dca2f71b159
- https://medium.com/apprentice-journal/pca-application-in-machine-learning-4827c07a61db

