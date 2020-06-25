# ground-water-index-using-gisimport xlrd 
import pandas as pd  
import numpy as np  
import seaborn as sns
import matplotlib.pyplot as plt


# Give the location of the file 
loc = ("G:\\semister-8(winter sem)\\geographic information system\\gis project\\apwaterxl.xlsx") 
ano = pd.read_excel(loc)
#anomalies.head()


ano.shape


ano.columns




ano["Quality Parameter"].value_counts()



 
wb = xlrd.open_workbook(loc) 
sheet = wb.sheet_by_index(0) 
sheet.cell_value(0, 0) 
  
# Extracting number of rows 
length = sheet.nrows
#print(length)
vil = input ("1. Enter your village name and \n2. put your area number in bracket \n3. dont missspell your village name\n4. enter in caps \n")
#vil=DAMMANNAPET(04)
#RAJA PURAM(13)
#GODALWAHI
#BAVALI

ele = sheet.cell_value(220, 3)
val=''
#print(ele)




for x in range(length):
    if sheet.cell_value(x, 3) == vil:
        val=sheet.cell_value(x, 6)
        #bolded_string = "\0100[1m" + a_string + "\0100[0m"
        print("You have entered village named",vil,"and it contains",val,"\n")
        break




if val == 'Fluoride':
    print("Hazards of flouride\n")
    print('Too much fluoride can lead to dental fluorosis or skeletal fluorosis, which can damage bones and joints')
    print("To know anythin additional information about this contenet plase visit this site thankyou www.google.co.in")

if val=='Salinity':
    print("The excess of salts content is one of the major concerns with water used for irrigation. A high salt concentration present in the water and soil will negatively affect the crop yields, degrade the land and pollute groundwater.")
    print("To know anythin additional information about this contenet plase visit this site thankyou www.google.co.in")
    print("Drinking water salinity has been found to be associated with cardiovascular diseases (CVD), diarrhea, and abdominal pain.")
if val=='Iron':
          print("Aeration of iron-containing layers in the soil can affect the quality of both groundwater and surface water\n \nif the groundwater table is lowered or nitrate leaching takes place. \n\nDissolutionof iron can occur as a result of oxidation and decrease in pH")
          print("For more information of effects of having iron refer https://www.who.int/water_sanitation_health/dwq/chemicals/iron.pdf")
          print("To know anythin additional information about this contenet plase visit this site thankyou www.google.co.in")
