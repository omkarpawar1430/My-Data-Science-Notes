#eda 

---

#### To show relation of each feature with target variable:
```python
fig, axs = plt.subplots(ncols=7, nrows=2, figsize=(20, 10))

index = 0

axs = axs.flatten()

for k,v in data.items():

sns.distplot(v, ax=axs[index])

index += 1

plt.tight_layout(pad=0.4, w_pad=0.5, h_pad=5.0)

```

#### To Plot Heatmap:
```python

plt.figure(figsize=(20, 10))
sns.heatmap(data.corr().abs(),  annot=True)
```

#### To 