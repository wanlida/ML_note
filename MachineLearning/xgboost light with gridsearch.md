```
## XGBClassifier with GridSearchCV


param_set = {
 'n_estimators':[50, 100, 500, 1000]
}
gsearch = GridSearchCV(estimator = XGBClassifier( learning_rate =0.1, 
n_estimators=100, max_depth=5,
min_child_weight=1, gamma=0, subsample=0.8, colsample_bytree=0.8, 
nthread=7,
objective= 'binary:logistic', scale_pos_weight=1, seed=410), 
param_grid = param_set, scoring='roc_auc',n_jobs=7,iid=False, cv=10)

xgb_model2 = gsearch.fit(features_train, label_train)
xgb_model2.grid_scores_, xgb_model2.best_params_, xgb_model2.best_score_


## LightGBM with GridSearchCV	

param_set = {
 'n_estimators':[20, 50]
}

gsearch = GridSearchCV(estimator = LGBMClassifier( boosting_type='gbdt', num_leaves=30, max_depth=5, learning_rate=0.1, n_estimators=50, max_bin=225, 
 subsample_for_bin=0.8, objective=None, min_split_gain=0, 
 min_child_weight=5, 
 min_child_samples=10, subsample=1, subsample_freq=1, 
colsample_bytree=1, 
reg_alpha=1, reg_lambda=0, seed=410, nthread=7, silent=True), 
param_grid = param_set, scoring='roc_auc',n_jobs=7,iid=False, cv=10)

lgb_model2 = gsearch.fit(features_train, label_train)
lgb_model2.grid_scores_, lgb_model2.best_params_, lgb_model2.best_score_
```
