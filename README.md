# mini-project-with-pandas
import pandas as pd

df = pd.DataFrame(columns=['Age', 'Height', 'Weight', 'BMI', 'Status'])

for i in range(1, 11):
    age = int(input("Enter age #{}: ".format(i)))
    height = float(input("Enter height (in meters) #{}: ".format(i)))
    weight = float(input("Enter weight (in kgs) #{}: ".format(i)))
    bmi = round(weight / (height**2), 2)
    
    status = lambda x: 'Underweight' if x < 18.5 else ('Normal' if x < 25 else ('Overweight' if x < 30 else 'Obese'))
    bmi_status = status(bmi)
    
    df.loc[len(df)] = [age, height, weight, bmi, bmi_status]

print(df)
#this code getting the age height & weight and calcute the bmi
