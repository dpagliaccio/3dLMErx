# 3dLMErx

Minor edits were made to AFNI's 3dLMEr tool to allow voxel-wise brain activity to be a predictor variable in linear-mixed effects models.
For details on the original 3dLMEr and other functionality, see https://afni.nimh.nih.gov/pub/dist/doc/program_help/3dLMEr.html
The edited code was adapted from that in version: "Precompiled binary macos_10.12_local: Apr  8 2021 (Version AFNI_21.1.01 'Domitian')"

Edits included:
1) adding yy (brain activity) as a valid variable name in varsOK on line 534
2) removing the model formula definition on line 892, instead the model should be specified completely with the -model input

For example, brain activity can be examined as a predictor of a clinical outcome variable that is repeatedly assessed at multiple visits with this formulation:
3dLMErx -model outcome~age+sex+visit*yy+(1|Subj)

To 'install': download the 3dLMErx and 3dLMErx.R files and copy them to your AFNI /abin/ folder
