# Facial Recognition Evasive Attacks

## Setup
### You need to have the requiremtns setup as well as python3
within ./AIV directory

```
pip3 install -r counterfit/requirements.txt
```

or

```
pip install -r counterfit/requirements.txt
```

## Purpose: Usage of AI Vulnerability finder tool [Coutnerfit] in locating vulnerabilities of facial recognition machine learning models

## Data Source

### Source: 
This data is nibuilt and gotten from a python module source
It is provided externally under sklearn public datasets and can be accessed using

```
from sklearn.datasets import fetch_lfw_people
n_samples, h, w = lfw_people.images.shape
```
Refer to https://github.com/popoolasubomi/AIV/blob/main/counterfit/counterfit/targets/Faces/Trial.ipynb regarding more info on the data usage and training of the ML model

### Data Description
- Construct of multiple facial images of the following targets: 'Ariel Sharon', 'Colin Powell', 'Donald Rumsfeld', 'George W Bush', 'Gerhard Schroeder', 'Hugo Chavez', 'Tony Blair'
- Data is collected from the python module and transforomed in to .npx format for compression and easier usage / manipulation.
- Machine learning model was built & trained based on the context of the data provided and the model created was used as the main test of vulnerabiility within the Faces target

## Instruction On Usage
You would need to run counterfit.py
within ./AIV directory
```
cd counterfit
python3 counterfit.py
```

1. We need to view the targets accessible with this command:
```
list targets
```

2. We are interacting with the target we constructed {Faces}
```
interact Faces
```

3. Now we are going to list the possible frameworks we could use to attack the models with command
```
list frameworks
```

4. The framework we are going to require with this particular attack is the *art* framework so we load that using:
```
load art
```

5. Now we can list the attacks loaded using
```
list attacks
```

6. we are going to use the HopSkipJump attack becuase it supports imagery data and is under the evasive atack category needed for our project. To do this:
```
use HopSkipJump
```

7. to view information about this attack you can:

```
show info
``` 

8. We need to predict a variety of sample data within our Faces target to utilize this attack and to do this, we simply:
```
predict -i range(50)
```

9. After this, we want to set the parameters for the attack, we are going to test the attack on the 990th sample using this command
```
set --sample_index 990 --norm 2 --max_iter 10 --max_eval 5000 --verbose true
```

to set a sample of another index 5 we simply:
```
set --sample_index 5 --norm 2 --max_iter 10 --max_eval 5000 --verbose true
```

10. to run this attack, we use the 'run' command
```
run
```

note: The 'run' operation could take some time

If the final results has a success value of true, we owuld be informed of the input label confidence levels as well as the confidence level of the adversial label informaing us how likely the adversial labels are to succeed


# MIT License

Copyright (c) 2022 subomi

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
