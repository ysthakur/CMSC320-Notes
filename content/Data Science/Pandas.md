
## Useful Pandas functions

- `pd.read_csv('file.csv')` for loading a `DataFrame` from a CSV
- `apply`
    - `df.apply(f)` applies `f` to every row (a `Series` object) of `df`
    - `df["col"].apply(f)` applies `f` to every individual value inside `df["col"]`
- `groupby`: `df.groupby("col")` or `df.groupby(fn)`
- Filtering: Pandas allows filtering with masks, like APL
    - `df[<some boolean Series>]` will select only rows of `df` where the corresponding item in `<some boolean Series>` is true
    - e.g. `df[df["Age"] > 30]` to only select rows where people’s ages are greater than 30
    - Use `&` and `|` for multiple conditions
- `value_counts`: Both `DataFrame` and `Series` have `value_counts()` methods
    - With a `Series`, it returns another `Series` containing counts of unique values (with the index being the original values)
    - With a `DataFrame`, it returns a `Series` containing the count of each unique row
- `astype` (can be applied to both `DataFrame` and `Series`)
    - The data type given has to be a Numpy or Python type
    - e.g. `df.astype('int32')` to turn all columns into `int32`
    - e.g. `df.astype({'col1': 'int32'})` to turn only `col1` into `int32`
    - e.g. `ser.astype('category')` to turn into categorical type
- `unique()`/`drop_duplicates()` to drop duplicate rows
- `dropna()` to drop any rows with any `NaN` values
- `fillna('foo')` to replace `NaN` values with `'foo'`
- `len(df)` to get the number of rows

- `hist()` can generate a histogram of a `Series`