import mitosheet
mitosheet.sheet()
from mitosheet import *; register_analysis('UUID-2a0382ac-4010-4276-b380-65d892ffb36a')
    
# Imported /home/papo/minibond/DBfuzzy.csv
import pandas as pd
DBfuzzy = pd.read_csv(r'/mnt/d/DIR/csv/Fdg/2022-M03', sep='\t')





import pandas as pd
from sqlalchemy import create_engine

username = ""
password = ""
port = 3306
database = ""

engine = create_engine('mysql+mysqldb://%s:%s@localhost:%i/%s'
                       %(username, password, port, database))

sql = "SELECT * FROM rna_abs;"
df = pd.read_sql_query(sql, engine)
df["delibera"] = pd.to_datetime(df["delibera"])
#df.index.set_names("regione", inplace=True)

import plotly.express as px
# Construct the graph and style it. Further customize your graph by editing this code.
# See Plotly Documentation for help: https://plotly.com/python/plotly-express/
fig = px.bar(df_pivot, x='regione', y='CF nunique')
fig.update_layout(
    title='regione, CF nunique bar chart',
    barmode='group',
    xaxis=dict(
        rangeslider=dict(
            visible=True,
            thickness=.05
        )
    )
)
fig.show(renderer="iframe")
