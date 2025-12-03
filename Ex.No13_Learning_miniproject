# Ex.No: 13 Machine Learning – MiniProject
### REGISTER NUMBER : 212221040147
### AIM:
To write a program to train the classifier for -----------------.
###  Algorithm:
```
Step:1 Import package
Step:2 Get the data
Step:3 Split the data
Step:4 Scale the data
Step:5 Instantiate model
Step 6: Create Gradio Function
Step 7: Print Result
```

### Program:
```
#import packages
import numpy as np
import pandas as pd

pip install gradio

pip install typing-extensions --upgrade

!python --version

pip install --upgrade typing

import gradio as gr

import pandas as pd

#get the data
data = pd.read_csv('diabetes.csv')
data.head()
```

![image](https://github.com/Vijayalakshmi230/miniproject/assets/127175503/d77700c2-ebfd-43d6-9a00-a2357ed192fe)

```

print(data.columns)

x = data.drop(['Outcome'], axis=1)
y = data['Outcome']
print(x[:5])

```

![image](https://github.com/Vijayalakshmi230/miniproject/assets/127175503/7564d59a-2ee4-4272-a566-f70548e113c1)

```

#split data
from sklearn.model_selection import train_test_split

x_train, x_test, y_train, y_test= train_test_split(x,y)

#scale data
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
x_train_scaled = scaler.fit_transform(x_train)
x_test_scaled = scaler.fit_transform(x_test)

instatiate model
from sklearn.neural_network import MLPClassifier
model = MLPClassifier(max_iter=1000, alpha=1)
model.fit(x_train, y_train)
print("Model Accuracy on training set:", model.score(x_train, y_train))
print("Model Accuracy on Test Set:", model.score(x_test, y_test))

print(data.columns)

#create a function for gradio
def diabetes(Pregnancies, Glucose, Blood_Pressure, SkinThickness, Insulin, BMI,Diabetes_Pedigree, Age):
    x = np.array([Pregnancies,Glucose,Blood_Pressure,SkinThickness,Insulin,BMI,Diabetes_Pedigree,Age])
    prediction = model.predict(x.reshape(1, -1))
    if(prediction==0):
      return "NO"
    else:
      return "YES"

outputs = gr.Textbox()
app = gr.Interface(fn=diabetes, inputs=['number','number','number','number','number','number','number','number'], outputs=outputs,description="Detection of Diabeties")
app.launch(share=True)
```

### Output:

![image](https://github.com/Vijayalakshmi230/miniproject/assets/127175503/d7423277-03d0-4789-9187-bad36e044e25)

![image](https://github.com/Vijayalakshmi230/miniproject/assets/127175503/9f1d10e9-af64-431f-834b-d250d3888170)

![image](https://github.com/Vijayalakshmi230/miniproject/assets/127175503/a0882788-27e3-44c4-9e29-ca759516affa)




### Result:
Thus the system was trained successfully and the prediction was carried out.
