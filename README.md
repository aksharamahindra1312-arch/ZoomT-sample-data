Step 1: Extract one consignment
For consignment number 6100957242:
python -c "import pandas as pd; d=pd.read_csv('national_trips_test.csv',dtype={'Consignment_Number':str},low_memory=False); d=d[d['Consignment_Number'].str.strip()=='6100957242']; print('Matching rows:',len(d)); d.to_csv('zt_sample_6100957242.csv',index=False) if len(d)>0 else None"


Step 2: Generate predictions for that consignment
python predict.py --input "zt_sample_6100957242.csv" --output "zt_sample_6100957242_predictions.csv"
