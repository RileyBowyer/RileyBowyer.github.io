# Live Update Issue with VSCode

Whislt generating results for the second question of the assignment, I found that VSCode failed to generate some of the useful metric data whilst training that fastai is meant to provide. However, this was solved with this patch, found from stack overflow.

```
# Patch for ipython to allow for updating of display (https://stackoverflow.com/questions/75936184/learn-fine-tune-not-showing-progress-bar-for-each-epoch)
from IPython.display import clear_output, DisplayHandle
def update_patch(self, obj):
    clear_output(wait=True)
    self.display(obj)
DisplayHandle.update = update_patch
```