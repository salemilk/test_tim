import pandas as pd

#Read file
match = pd.read_excel('match.xlsx', sheet_name='Sheet1')
replace = pd.read_excel('replace.xlsx', sheet_name='Sheet1') #replace value
sample_input = pd.read_excel('sample_input.xlsx', sheet_name='Sheet1') #raw file

#column
match_col_n1 = ['e', 'i', 'j', 'k', 'l', 'n', 'label']
match_col_n2 = ['e', 'i', 'j', 'k', 'l', 'n']
replace_col_n = ['i', 'j', 'k', 'l', 'label'] #replace
sample_input_col_n = ['a', 'b', 'c', 'd', 'e', 'f',
                      'g', 'h', 'i', 'j', 'k', 'l',
                      'm', 'n']

#DataFrame
match_data = pd.DataFrame(match,  columns=match_col_n1)
replace_data = pd.DataFrame(replace, columns=replace_col_n)
sample_input_data = pd.DataFrame(sample_input,  columns=sample_input_col_n)

# tmp
tmp = sample_input_data.merge(match_data, how='left', on=None, 
                 left_on=match_col_n2, right_on=match_col_n2, 
                 left_index=False, right_index=False, sort=False, 
                 suffixes=('_x', '_y'), copy=True, 
                 indicator=False, validate=None)

sample_input_data['label'] = tmp['label']

#for num in match_data.index.values:
#    label = match_data.loc[num, 'label']
#    sample_input_data[sample_input_data['label'] == label][replace_col_n] = replace_data.iloc[num, :].values


sample_input_data = sample_input_data.to_excel('output.xlsx', index=False)

