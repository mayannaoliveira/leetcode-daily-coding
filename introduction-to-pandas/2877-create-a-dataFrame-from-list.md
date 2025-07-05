## 2877. Create a DataFrame from List

#### Pandas

```python
import pandas as pd

def createDataframe(student_data):
    df = pd.DataFrame(student_data, columns=['student_id', 'age'])
    return df
```