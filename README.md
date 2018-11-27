# Import-csv-into-mangodb-in-pymongo
Easiest way to convert csv into mongodb friendly json file 

    import json
    import pymongo
    import pandas as pd
    myclient = pymongo.MongoClient()

    mydb = myclient['mydatabase']
    mycol = mydb['mydata']

    df = pd.read_csv('yourcsv.csv',encoding = 'ISO-8859-1')          # loading csv file
    data = json.loads(df.reset_index().to_json(orient = 'records'))  # reading json file 
    x = mycol.insert_one(data)
