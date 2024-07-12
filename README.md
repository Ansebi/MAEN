# MAEN
Mean Absolute Error Normalised<br><br>
Magnitude-invariant universal loss score.<br>
Designed for evaluating the performance of Times Series Forecast models.<br>
Evaluates such problematic cases as Near-Zero and Flat vectors of target values.<br><br>

Requires min and max reference values.<br><br>

```
import urllib
urllib.request.urlretrieve(
    'https://github.com/Ansebi/maen/blob/main/maen_score.py?raw=true',
    'maen_score.py'
)
from maen_score import np, maen_score


'''
y_train = np.random.normal(0, 0.00001, 100)
y_test = np.random.normal(0, 0.00001, 10)
y_pred = np.random.normal(0, 0.00001, 10)
'''
y_train: np.array = ...
y_test: np.array = ...
y_pred: np.array = ...

maen = maen_score(y_test, y_pred, y_train.min(), y_train.max())

[print(i) for i in zip(y_test, y_pred)]
print(f'{maen = :.2f}')
```
