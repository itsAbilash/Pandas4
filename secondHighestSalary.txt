import pandas as pd

def second_highest_salary(employee: pd.DataFrame) -> pd.DataFrame:
    df = employee['salary'].drop_duplicates().sort_values(ascending=False).head(2)
    if len(df)<2:
        return pd.DataFrame({'SecondHighestSalary':[None]})
    return pd.DataFrame(df).tail(1).rename(columns={'salary':'SecondHighestSalary'})