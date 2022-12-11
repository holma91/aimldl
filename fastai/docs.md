## FAST AI DOCUMENTATTION NOTES

The basic flow is

1. create appropriate DataLoaders
2. create a Learner
3. call a fit method
4. make predictions or view results

Example:

```py
# create a path object from the PETS dataset
path = untar_data(URLs.PETS)/'images'

def is_cat(x): return x[0].isupper()

# set up the DataLoader
dls = ImageDataLoaders.from_name_func(
    path,
    get_image_files(path),
    valid_pct=0.2,
    seed=42,
    label_func=is_cat,
    item_tfms=Resize(224)
)

# download a pretraind model and put it in learn
learn = vision_learner(dls, resnet34, metrics=error_rate)

# fine tune the model
learn.fine_tune(1)
```
