# Import-csv-into-mangodb-in-pymongo
Easiest way to convert csv into mongodb friendly json file 

    import json
    import pymongo
    import pandas as pd
    myclient = pymongo.MongoClient()

    mydb = myclient['mydatabase']
    mycol = mydb['mydata']

    df = pd.read_csv('yourcsv.csv',encoding = 'ISO-8859-1')   # loading csv file
    df.to_json('yourjson.json')                               # saving to json file
    jdf = open('yourjson.json').read()                        # loading the json file 
    data = json.loads(jdf)                                    # reading json file 
    x = mycol.insert_one(data)
