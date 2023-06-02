```
pip install xlsxstyler
```

```
from xlsxstyler import ExcelWriter
import pandas as pd

# define paths
path = "/path/to/my/xlsx"
img_url = "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1869px-Python-logo-notext.svg.png"
img = "path/to/image"

df = pd.DataFrame({'A': [1, 2, 3],
                   'B': [4, 5, 6]})

# place a data frame in an excel sheeet giving start_row and start_col (human count - starting with 1)
# if file doesn't exist, it will get created.
ExcelWriter.write_dataframe(path, sheet_name='mysheet', df=df, start_row=1, start_col=1, add_rownames=True)

# place an image in an excel sheet giving start_row and start_col (human count - starting with 1)
ExcelWriter.write_image(path, sheet_name='mysheet', image_path=img_url, start_row=10, start_col=5)

import urllib
import io