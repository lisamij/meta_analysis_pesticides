# README

**Functions used in the analyses**

- Analyses.R : 
Those functions return a meta-analytical model from a tibble
 - analysis_1_choose: Analysis with variance method 1
    - analysis_2_choose: Analysis with variance method 2
    - analysis_3_choose: Analysis with variance method 3
    - analysis_efsa: Analysis for EFSA dataset 
    - all_analysis_choose: Allows to run one analysis simply by choosing the parameters
Those functions do summary or comparison of different methods
   - all_analysis_comparison: Comparison of the different options for the main analysis 
    - save_table_summary_dataset: Get a summary of the final dataset in the main analysis 
    - analysis_qualitative_efsa: Comparison of the two qualitative methods for the EFSA dataset 
    

- Variances.R : Those functions modify a tibble to add a column containing the sampling variance
    - variance_method_1: Largest arm 
    - variance_method_2: Largest arm and log scale 
    - variance_method_3: Width CI 
    - lrr_and_variance_efsa: Add the log response ratio and the variance corresponding to the variance of the group of species 
    - lrr_efsa: Just compute the LRR (useful for the qualitative methods for EFSA)

- Imputations.R : Those functions runs the different imputation methods. Due to the different methods of computing sampling variance, each imputation method is declined for the variance method. 
    - imputing_full_1: Run the gamma imputation for the variance method 1
    - imputing_full_2: Run the gamma imputation for the variance method 2
    - imputing_full_3: Run the gamma imputation for the variance method 3
    - imputing_se_1: Auxiliary function for the gamma method 1
    - imputing_se_2: Auxiliary function for the gamma method 2
    - imputing_ci: Auxiliary function for the gamma method 3
    - imputing_method_1_n_1: Run the missing case imputation for variance method 1
    - imputing_method_1_n_2: Run the missing case imputation for variance method 2
    - imputing_method_1_n_3: Run the missing case imputation for variance method 3
    - imputing_method_2_n_1: Run the hybrid imputation for variance method 1
    - imputing_method_2_n_2: Run the hybrid imputation for variance method 2
    - imputing_method_2_n_3: Run the hybrid imputation for variance method 3
    - cv_avg: Compute the coefficient of variation (taken from Nakagawa et al 2023)
    - weighted_cv : Compute the weighted coefficient of variation (taken from Nakagawa et al 2023)



- Sensitivity.R: Those functions are used for the different sensitivity analysis 
   - leave_one_out_m: Run a leave one out analysis by excluding each row and looking at the changes in significance
   - publication_bias: Analyses about publication bias
   - sensitivity_regulatory_guidelines: Sensitivity analysis to regulatory guidelines 
   - sensitivity_animals: Sensitivity analysis to animals 
   - glyphosate_sensitivity: Sensitivity analysis to glyphosate 
   - sensitivity_excluded: Sensitivity to excluded effect sizes
   - profile_plots: Save profile plots for identifiability parameters 
   - heterogeneity: Compute the different measures of heterogenity 
   - sensitivity_supp_efsa: Sensitivity to the maximum values in EFSA
   - sensitivity_matrix: Sensitivity to the parameters in the autocorrelation matrix 

- Plots.R : Those functions save or show the plots from the analysis 
   - plot_mod: Show a plot of a model from the main analysis
   - plot_mod_efsa: Show a plot of a model from the EFSA analsyis 
   - plot_factor_two_mortality: Saves a plot of all effect sizes highlighting the ones with a factor two
   - save_plot: Saves a plot from a model
   - save_plot_efsa: Saves a plot from a EFSA model
   - save_plot_other_efsa: Saves plot from qualitative analysi s for EFSA

- Models.R: Those functions fit the models to the datasets
   - fit_model: Fits a rma model to a dataset 
   - fit_mod_one: Fits a rma model to a dataset without fixed effects, but with the same variance matrix
   - estim_mod_wide: Get estimates in a wide format from a model 
   - fit_model_simple: Fit a simple model to a dataset 
   - estim_mod_simple: Get estimates from a simple model 
   - estim_pred: Get the prediction intervals from a model 
   - save_estimates: Save the estimates from a model 
   - fit_model_structure: Fit a model without moderators but with a random effect structure 
   - fit_model_efsa: Fit a model to the EFSA dataset 
   - get_efsa_results: Get results for qualitative methods for EFSA

- Clean.R: Those functions clean the dataset before the analyses
  - clean_general: First cleaning and import of the main analysis 
  - clean_efsa: First cleaning and import of the EFSA dataset 