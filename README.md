# ENGR 102 Lab Topic 5 (team)
There is one deliverable for this team assignment. Please submit the following file to Gradescope. **DO NOT** include the team header at the top of your file. This is a team assignment, but **everyone** must submit the file for credit. You may discuss the problems with other teams, but your submitted work must be unique. Check out the [Frequently Asked Questions](#frequently-asked-questions) below.

## Activities

1. [Ten Year Risk](#ten-year-risk)

## Ten Year Risk
In engineering and science, it is common that we want to calculate the effect of some complex behavior. To make this possible, we create a model of the behavior. A model attempts to describe the behavior in a way that is understandable and computable. Some models are based on physical laws and principles, some are based on replicating observations, and many are a combination of these. Once you have a model, you can use it to analyze and predict the performance or behavior of some system or phenomenon. 
 
In this lab you will be writing test cases for a model that has previously been created that may then be used to write a program to use that model to give a user a prediction. In this case, the model that has been developed is to estimate someone's 10-year risk for likelihood of a heart attack, developed by the NIH. This model was constructed from data analysis of various factors that have been demonstrated to contribute to heart attacks for those ages 20-70.

The process is outlined on the final page of [this document](Lab_Topic_5_team_doc.pdf) (also posted to Canvas). Note that the model works by taking several factors, assigning "point" values to them, and calculating an overall risk based on the sum of those points. Your team will focus on the table on the last page of the document for this activity.

Begin by considering what variables might be used to construct a program to calculate someone’s 10-year risk. Also consider a sequence of steps needed to write such a program. Note that you do **NOT** need to create this program, only discuss with your team *how* one may be written (an algorithm).

Next, determine the test cases needed to fully test the model. That means that you need to create enough test cases to check every range of conditions in the model (check every possible item on the page). You will likely need many test cases; it’s okay for some of your test cases to repeat conditions. For each test case you need to provide the inputs for the case as well as the expected output. Inputs include the factors in the table: sex, age, total cholesterol, smoking status, HDL, systolic BP, and medication status. The output is the 10-year risk %.

Create a file named `tyr_test_cases.txt` that will contain all of your test cases. You will **NOT** need to submit a Python file (~.py). For the purposes of autograding, write one test case per line in your file. Format the information in each test case by using the keys below, followed by a colon, then the associated value. Separate each item with a single space. You may write the information in any order, as long as you have only one test case per line. [A template is provided here](tyr_test_cases.txt).

*For full credit all of your test cases must have valid input with the correct expected output as well as complete code coverage (check each value on the page, including output, independent of other variables).*

Keys and their range of values:
- `sex` with possible inputs `F` and `M`
- `age` with possible inputs positive integers between `20` and `79`, inclusive
- `cho` (total cholesterol) with possible inputs any positive integers
- `smo` (smoking status) with possible inputs `Y` and `N`
- `hdl` with possible inputs any positive integers
- `sbp` (systolic BP) with possible inputs any positive integers
- `med` (medication status) with possible inputs `Y` and `N`
- `out` (output) as your expected 10-year risk % (use `>30` for the last value in the table)

Example `tyr_test_cases.txt` file (with one test case using inputs: female, age 40 years, 105 total cholesterol, non-smoker, HDL 60 mg/dL, systolic BP 100 mmHg, not taking blood pressure medication; expected output: <1%):
```
sex:F age:40 cho:105 smo:N hdl:60 sbp:100 med:N out:<1
```

Note that this test case successfully tests a possible range for age, total cholesterol, smoking status, HDL, systolic BP, medication status, and the output for a female patient. This means that in future tests where sex is `F`, you do not need to test these ranges again as you have provided a value within them. Also note that this means you do **NOT** need every combination of every range. For example, if you need to test values for independent variables `A`, `B`, and `C`, you only need one test case that includes all three, and not the multiple other possibilities.

For example, if your program contained the following code
```python
if num > 0:
    print("Positive")
else:
    print("Not positive")
```
then you only need two test cases: a value for `num` greater than zero and a value that's not. There is no need to have infinite test cases to test every possible value for `num`, just one to check the `if` and one to check the `else`.


## Frequently Asked Questions
1. **Do we really need to write a lot of test cases?** Only if you want full credit. :)

2. **What is the minimum number of test cases needed for full credit?** The theoretical minimum is 50, but that's really difficult to do. If you think carefully, you can easily obtain full credit with fewer than 100 test cases. If you don't yet have enough... just keep writing more test cases!

Have a question you don't see here? Email your instructor!

Based upon Dr. Keyser’s Original<br/>
Revised Summer 2025 SNR
