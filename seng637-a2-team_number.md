**SENG 637 - Software Testing, Reliability, and Quality**

**Lab. Report \#2 – Requirements-Based Test Generation**

| Group Number 19      |
| -------------- |
| Sami Abdelhalem |
| Mohammad Hallaq |
| Ogechukwu Kanu |
|  Olayinka Afolabi |
| Emmanuel Alafonye |

**Table of Content**

[1 Introduction](https://github.com/seng637-Winter/seng637-a2-AllisonOge/blob/main/seng637-a2-team_number.md#1-introduction)

[2 Detailed description of unit test strategy](https://github.com/seng637-Winter/seng637-a2-AllisonOge/blob/main/seng637-a2-team_number.md#2-detailed-description-of-unit-test-strategy)

[3 Test cases developed](https://github.com/seng637-Winter/seng637-a2-AllisonOge/blob/main/seng637-a2-team_number.md#3-test-cases-developed)

[4 How the teamwork/effort was divided and managed](https://github.com/seng637-Winter/seng637-a2-AllisonOge/blob/main/seng637-a2-team_number.md#4-how-the-teamworkeffort-was-divided-and-managed)

[5 Difficulties encountered, challenges overcome, and lessons learned](https://github.com/seng637-Winter/seng637-a2-AllisonOge/blob/main/seng637-a2-team_number.md#5-difficulties-encountered-challenges-overcome-and-lessons-learned)

[6 Comments/feedback on the lab itself](https://github.com/seng637-Winter/seng637-a2-AllisonOge/blob/main/seng637-a2-team_number.md#6-commentsfeedback-on-the-lab-itself)

# 1 Introduction

This lab report discusses the strategy applied to perform automated unit testing using the black box techniques. The lab is carried out on a version of JFreeChart, an open-source Java framework for chart calculation, creation and display. The unit testing strategy applied explores the JUnit and Javadoc tools to implement test cases for a total of ten methods from the classes `org.jfree.data.Range` and `org.jfree.data.DataUtilities`. We implement the test cases using the JUnit 4 library for compatibility reasons.

We started the assignment with a phase of familiarization, where we acquainted ourselves with the assignment's objectives and the software at hand. Subsequently, we shift our attention towards the meticulous creation of unit test strategies that apply the black box techniques according to the requirements outlined in Javadocs for the classes in concern. The phase was collaboratively carried out by all members of the team through task assignments and check-in meetings to track progress and collectively bring all members up to speed. The final stage comprised the compilation and revision of all individual works of the team members for a comprehensive test suite for the system under test.

The following sections dive into a detailed description of the strategy applied (black box techniques), the test cases that were developed as seen in the source code while correlating them to the test strategies outlined, the teamwork effort, challenges encountered and lessons learned, and lastly final comments on the completed lab.

# 2 Detailed description of unit test strategy

The unit test strategy employed for this lab was the black box testing technique. The tests cover equivalence partitioning, boundary value analysis, decision table strategies, and error guessing to validate the correctness and robustness of the methods of the classes under test (`org.jfree.data.DataUtilites` and `org.jfree.data.Range`).
## Objectives
- To verify that the methods of the `org.jfree.data.Range` class accurately satisfy the requirements of the documentation.
- To verify that the methods of the `org.jfree.data.DataUtilities` class accurately satisfy the requirements of the documentation.

## Test Strategies
The following test strategies will be employed in this lab.

### Equivalence Partitioning (EP)
This technique will divide the inputs to the methods into groups that are expected to elicit similar responses from the methods. For example, valid data inputs for accomplishing the methods function (computing the sum of 2D data given an index) and invalid inputs (such as null inputs) for triggering exceptions.

### Boundary Value Analysis (BVA)
This technique will pay special attention to testing the boundaries of the data input range, such as empty datasets, and maximum allowable indexes just outside the valid range.

### Decision Table Strategies
This technique will be used to systematically explore combinations of inputs, for example, indexes and data conditions (valid and invalid), to ensure all logical paths are verified.

### Error Guessing (EG)
This technique will be employed to identify potential error conditions not covered by the above methods. Based on testers' experience and knowledge of common pitfalls in data manipulation and calculation function, the test will be designed to target overflow conditions, precision issues, handling special numerical values such as NaN and concurrent modifications of the input data which might lead to inconsistent results.

## Codebase Structure and Test Data
These techniques will be applied to the classes under test using the requirements found in the Javadoc to develop test cases for the individual methods. For ease of teamwork and modularity, we chose to design test cases for each method in a class, for example given the method `Range.getCentralValue`, the test cases developed will be implemented in a class called `GetCentralValueTest` contained in the `GetCentralValueTest.java` file. These files were then organized into the `org.jfree.data.test` package. The test cases developed for each of the ten methods tested are discussed in the next section.

With some of the methods, there will be the need for test data which we will accomplish in one of two ways. Either with mock data using the JMock library or explicitly defining the data.

# 3 Test cases developed

The test cases developed for the methods in the classes `org.jfree.data.DataUtilities` and `org.jfree.data.Range` applied the test strategy described in detail in the previous section to ensure comprehensive testing of the methods’ behaviour across a range of valid and invalid input scenarios. The following text discusses the test cases and methods organized based on the source code to identify which partitions they assert.

The `org.jfree.data.Range` class has fifteen methods and the test class implemented test cases for the following five methods out of the fifteen methods; **`getUpperBound`**, **`getLowerBound`**, **`getLength`**, **`expand`**, and **`shift`**. These methods were tested independently with their respective test classes using the black box techniques which are outlined as follows showing the test classes and test cases, functions and expected outcomes.

## A `org.jfree.data.test.GetUpperBoundTest`
`org.jfree.data.test.GetUpperBoundTest` is the JUnit test class that tests the functionality of the org.jfree.data.Range.getUpperBound method. There are four methods (test cases) which are: `testgetUpperBoundNormalRangePositive`,  `testGetUpperBoundNormalRangeNegative`, `testGetUpperBoundRangeWithZeroLowerBound`, and `testGetUpperBoundRangeWithOneElement`,
 and their respective functions are as follows:

- `testGetUpperBoundNormalRangePositive` - to check for a normal range with a positive upper bound.
- `testGetUpperBoundNormalRangeNegative` – to check for a normal range with a negative upper bound.
- `testGetUpperBoundRangeWithZeroLowerBound` - to check for range with upper bound at zero.
- `testGetUpperBoundRangeWithOneElement` – to check for range with only one element.

Depending on boundary value analysis, potential test boundaries of the input ranges are a positive upper bound, a negative upper bound, zero, and the same value for the upper and the lower bound (a range with one element). The method `testGetUpperBoundNormalRangePositive` tests the positive upper bound, the method `testGetUpperBoundNormalRangeNegative` tests the negative upper bound, the method `testGetUpperBoundRangeWithZeroLowerBound` tests the zero upper boundary, and the method `testGetUpperBoundRangeWithOneElement` tests the upper bound of a one-element range. Finally in terms of decision table strategy to help consider every possible input combination and the expected outcome, the four methods collectively meet that criterion. The decision table is shown in Table 1.

Table 1: Decision table for the `org.jfree.data.Range.getUpperBound`
| Lower Bound | Expected Outcome |
|---| ---|
| Positive | The positive upper bound |
| Negative | The negative upper bound |
| Zero | 0 |
| Same as upper bound | The upper bound (same value for lower bound |

## B `org.jfree.data.test.GetLowerBoundTest`
`org.jfree.data.test.GetLowerBoundTest` is the JUnit test class that tests the functionality of the `org.jfree.data.Range.getLowerBound` method. There are four methods (test cases) which are: `testGetLowerBoundNormalRangePositive`, `testGetLowerBoundNormalRangeNegative`, `testGetLowerBoundRangeWithZeroLowerBound`, and `testGetLowerBoundRangeWithOneElement`,
 and their respective functions are as follows:

- `testGetLowerBoundNormalRangePositive` - to check for a normal range with a positive lower bound.
-  `testGetLowerBoundNormalRangeNegative` – to check for a normal range with a negative lower bound.
-  `testGetLowerBoundRangeWithZeroLowerBound` - to check for range with lower bound at zero.
-  `testGetLowerBoundRangeWithOneElement` – to check for range with only one element.

Depending on boundary value analysis, potential test boundaries of the input ranges are a positive lower bound, a negative lower bound, zero, and the same value for the lower and the upper bound (a range with one element). The method `testGetLowerBoundNormalRangePositive` tests the positive lower bound, the method `testGetLowerBoundNormalRangeNegative` tests the negative lower bound, the method `testGetLowerBoundRangeWithZeroLowerBound` tests the zero lower boundary, and the method `testGetLowerBoundRangeWithOneElement` tests the lower bound of a one-element range. Finally in terms of decision table strategy to help consider every possible input combination and the expected outcome, the four methods collectively meet that criterion. The decision table is shown in Table 2.

Table 2: Decision table for the org.jfree.data.Range.getLowerBound
| Lower Bound | Expected Outcome |
| --- | --- |
| Positive | The positive lower bound |
| Negative | The negative lower bound |
| Zero | 0 |
| Same as upper bound | The lower bound (same value for upper bound) |

## C org.jfree.data.test.GetLengthTest
The GetLengthTest class contains JUnit tests for the getLength method in the `org.jfree.data.Range` class. This method returns the length of the range, which represents the difference between the upper and lower bounds of the range. The tests aim to verify the correctness of the getLength method under different scenarios, including positive ranges, negative ranges, and zero-length ranges.

### Test cases
- `testGetLengthPositiveRange`: This test case verifies that the method correctly calculates the length of a positive range by subtracting the lower bound from the upper bound.
- `testGetLengthNegativeRange`: The purpose of this test is to ensure that the method computes the length of a negative range correctly by subtracting the upper bound from the lower bound.
- `testGetLengthZeroLength`: This test checks whether the method returns a length of 0.0 for a range with both bounds set to zero.

### Equivalence Partitioning
The input space for the getLength method is divided into ranges with positive, negative, and zero lengths. Each test case covers one partition to ensure comprehensive testing.

### Boundary Value Analysis
Test cases consider the boundaries of the input range. For example, `testGetLengthZeroLength` specifically targets the boundary where both lower and upper bounds are zero.

### Decision Table Strategy
Although not explicitly represented in a decision table, each test case targets a specific combination of input values and verifies the expected outcome, aligning with the method's specifications.

Table 3: Summary of test cases for `org.jfree.data.Range.getLength` method
| Test cases | Lower Bound | Upper Bound | Expected Outcome |
| --- | --- | --- | --- |
| `testGetLengthPositiveRange` | Any +ve number | Any -ve number | Upper - Lower |
| `testGetLengthNegativeRange` | Any -ve number | Any -ve number | Lower - Upper |
| `testGetLengthZeroLength` | 0 | 0 | 0.0 |

## D `org.jfree.data.test.ExpandTest`
According to the docs accompanying the `expand` method, there are some important considerations which include the following;
- the lower and upper margins expect values from 0 to 1 where the minimum value is 0 (0%) and the maximum value is 1 (100%)
- Valid input range for the range objects can either be positive ranges, negative ranges, or mixed ranges while valid input margins will be values between 0 and 1.
- Invalid margins can either be negative margins or margins greater than 1.
- The method throws InvalidParameterException for invalid `range` data objects

Applying the boundary value analysis we can consider valid margins with valid ranges (positive, negative or mixed ranges) as well as when there is an empty range (the start and the end index of the range object are the same). Then for equivalence partitioning testing, we test invalid input margins with any range. All of the above cases can essentially be captured as part of the decision table with the addition of the null range input to raise the InvalidParameterException. As such there are four methods (test cases) which are testExpandWithValidInput, `testExpandWithEmptyRange`, `testExpandWithInvalidMargins` and `testExpandWithNullRange` and their respective functions are as follows;
- `testExpandWithValidInput` - to check for the correct expansion with valid inputs.
- `testExpandWithEmptyRange` - to check for the correct expansion with empty range.
- `testExpandWithInvalidMargins` - to check for the output range object with negative margins.
- `testExpandWithNullRange` - to check that the method throws an “InvalidParameterException” for null “range”.

Table 4: Decision table for `org.jfree.data.Range.expand` method
| Valid Range | Lower Margin | Upper Margin | Expected Outcome |
| --- | --- | --- | --- |
| Yes | Within 0 - 1 | Within 0 - 1 | Valid expansion |
| Yes (empty range) | Within 0 - 1 | Within 0 - 1 | Valid expansion |
| Yes | Beyond 0 - 1| Beyond 0 - 1 | InvalidParameterException |
| No | Any | Any | InvalidParameterException |

## E `org.jfree.data.test.ShiftTest`
The `org.jfree.data.test.ShiftTest` class contains the test cases that test the `Range.shift` method. This method's primary function is to return the shifted version (to the right) of a Range object. It applies black box techniques in the following fashion to the test cases. 

### Test Cases
- `testPositiveRangeWithPositiveDelta` (Equivalence Partitioning)
  - Objective: Verify shifting a positive range upwards by a positive delta.
  - Rationale: This test resides within a valid input partition where both the range and delta are positive, affirming the method's basic functionality under standard conditions.
- `testPositiveRangeWithNegativeDelta` (Equivalence Partitioning)
  - Objective: Examine the method's response when a positive range is decreased by a negative delta.
  - Rationale: Targets a different valid input partition, ensuring the method accurately processes a reduction in the range.
- `testShiftWithZeroDelta` (Equivalence Partitioning)
  - Objective: Confirm that a range remains unchanged when shifted by a delta of zero.
  - Rationale: Represents a boundary case within the valid input partitions, testing the non-alteration aspect of the method.
- `testPositiveRangePreventingZeroCrossing` (Boundary Value Analysis)
  - Objective: Assess the prevention of zero crossing when shifting a positive range downwards by a delta that would typically result in crossing zero.
  - Rationale: Evaluate the enforcement of the allowZeroCrossing parameter at a critical boundary, ensuring the lower bound is adjusted to zero as per specifications.
- `testShiftWithNullBaseRange` (Error Guessing)
  - Objective: Validate that the expected exception is thrown for a null base range input.
  - Rationale: Leverages common error anticipation, checking the method's resilience and compliance with its contract by expecting a NullPointerException.

---

Similarly, for the `org.jfree.data.DataUtilities` class, there are five methods which include the following; **`calculateColumnTotal`**, **`calcuateRowTotal`**, **`createNumberArray`**, **`createNumberArray2D`**, and **`getCummulativePrecentages`**. The function of each of the test cases developed for the methods and its correlation with the black box testing techniques are discussed as follows.

## A `org.jfree.data.test.calculateColumnTotalTest`
According to the docs accompanying the `calculateColumnTotal` method, there are some important considerations which include the following;
- The `data` parameter must not be null
- The `column` index is zero-based
- The method throws InvalidParameterException for invalid `data` objects
- If the `column` index is out of bounds, it should return a total of zero

As such there are three methods (test cases) which are `testWithValidInput`, `testWithColumnOutOfBounds`, and `testWithNullData` and their respective functions are as follows;
- `testWithValidInput`- to check for the correct sum with valid inputs
- `testWithColumnOutOfBounds`- to check that an out-of-bounds column returns zero.
- `testWithNullData`- to check that the method throws an “InvalidParameterException” for null “data”.

With regards to equivalence partitioning where the input data can be partitioned into valid and invalid, the `testWithValidInput` method satisfies the valid input partition while the `testWithColumnOutOfBounds` and `testWithNullData` methods satisfy the invalid input partitions. For boundary value analysis, potential test boundaries of the input ranges considering the column parameter would be -1, 0 and the maximum column index n (assuming n is the last valid index). The methods `testWithValidInput` and `testWithColumnOutOfBounds` test the boundaries 0 and -1 alone which neglects the last boundary but such a number is arbitrary so cannot be determined. Finally in terms of decision table strategy to help consider every possible input combination and the expected outcome, the three methods collectively meet that criteria. The decision table is shown in Table 4.

Table 5: Decision table for the `org.jfee.data.DataUtilities.calculateColumnTotal` method
| Data Null | Column index | Expected Outcome |
| --- | --- | --- |
| No | Valid | The sum of the column |
| No | Out-of-bounds | 0 |
| Yes | Any | InvalidParameterException |

## B `org.jfree.data.DataUtilities.calculateRowTotalTest`
According to the docs accompanying the `calculateRowTotal` method, there are some important considerations which include the following;
- The `data` parameter must not be null
- The `row` index is zero-based
- The method throws InvalidParameterException for invalid `data` objects
- If the `row` index is out of bounds, it should return a total of zero

As such there are three methods (test cases) which are `calculateRowTotalWithValidInput`, `calculateRowTotalWithRowOutOfBounds`, and `calculateRowTotalWithNullData` and their respective functions are as follows;
- `calculateRowTotalWithValidInput`- to check for the correct sum with valid inputs
- `calculateRowTotalWithRowOutOfBounds`- to check that an out-of-bounds row returns zero.
- `calculateRowTotalWithNullData`- to check that the method throws an “InvalidParameterException” for null “data”.

With regards to equivalence partitioning where the input data can be partitioned into valid and invalid, the `calculateRowTotalWithValidInput` method satisfies the valid input partition while the `calculateRowTotalWithRowOutOfBounds` and `calculateRowTotalWithNullData` methods satisfy the invalid input partitions. For boundary value analysis, potential test boundaries of the input ranges considering the row parameter would be -1, 0 and the maximum row index n (assuming n is the last valid index). The methods `calculateRowTotalWithValidInput` and `calculateRowTotalWithRowOutOfBounds` test the boundaries 0 and -1 alone which neglects the last boundary but such a number is arbitrary so cannot be determined. Finally in terms of decision table strategy to help consider every possible input combination and the expected outcome, the three methods collectively meet that criteria. The decision table is shown in Table 6.

Table 6: Decision table for the `org.jfee.data.DataUtilities.calculateRowTotal` method
| Data Null | Row index | Expected Outcome |
| --- | --- | --- |
| No | Valid | The sum of the row |
| No | Out-of-bounds | 0 |
| Yes | Any | InvalidParameterException |

## C `org.jfree.data.test.CreateNumberArray2DTest`
The `CreateNumberArray2DTest` class contains a set of JUnit tests for the `createNumberArray2D` method in the `org.jfree.data.DataUtilities` class. This method constructs an array of arrays of Number objects from a corresponding structure containing double primitives. The tests aim to ensure the method behaves correctly under various input conditions, including valid input, null input, empty input, and invalid input.

### Test Methods (Cases)
- `testCreateNumberArray2DValidInput`: This test case verifies that the method returns the expected result when provided with valid input data.
- `testCreateNumberArray2DNullInput`: This test ensures that the method throws an IllegalArgumentException when null data is passed as input, as specified in the method's documentation.
- `testCreateNumberArray2DEmptyInput`: The purpose of this test is to check that the method throws an IllegalArgumentException when an empty array is provided as input.
- `testCreateNumberArray2DInvalidInput`: This test verifies that the method throws an IllegalArgumentException when the input data structure is irregular or invalid.

### Equivalence Partitioning
The input data is partitioned into valid and invalid sets. `testCreateNumberArray2DValidInput` covers the valid input partition, while the other test methods handle various scenarios of invalid inputs.

## Boundary Value Analysis
Test cases consider the boundaries of the input range. For instance, `testCreateNumberArray2DNullInput` ensures proper handling of the null input boundary.

### Decision Table Strategy
The test cases collectively consider every possible input combination and expected outcome, aligning with the method's specifications.

Table 7: Summary of test cases for `org.jfree.data.DataUtilities.createNumberArray2D` method

| Test Case | Data Null | Expected Outcome |
| --- | --- | --- |
| `testCreateNumberArray2DValidInput` | No | An array of Number of objects is returned |
| `testCreateNumberArray2DNullInput` | Yes | IllegalArgumentException is thrown |
| `testCreateNumberArray2DEmptyInput` | No | IllegalArgumentException is thrown |
| `testCreateNumberArray2DInvalidInput` | No | IllegalArgumentException is thrown |

## D `org.jfree.data.test.GetCumulativePercentagesTest`
The `DataUtilitiesGetCumulativePercentagesTest` class is designed to rigorously evaluate the `getCumulativePercentages` method from the DataUtilities class. This method's primary function is to calculate the cumulative percentages of numerical data represented by KeyedValues. Our testing strategy encompasses various scenarios to ensure comprehensive validation of the method's correctness, reliability, and robustness.

### Test cases
- `testCumulativePercentagesEmptyDataset` (Boundary Value Analysis)
  - Objective: To confirm the method's behaviour when provided with an empty dataset, expecting it to correctly return an empty set of results.
  - Rationale: This test targets a boundary condition within the input domain (an empty dataset), verifying that edge cases are handled appropriately and yield expected empty outputs.
- `testCumulativePercentagesSingleValue` (Boundary Value Analysis)
  - Objective: To assess the method's accuracy in calculating cumulative percentages for a dataset containing only a single value, which should logically be 100%.
  - Rationale: Focuses on another boundary condition, this time concerning dataset size, to ensure that minimal valid datasets are processed correctly.
- `testCumulativePercentagesWithNegativeValues` (Error Guessing)
  - Objective: To investigate the method's capability to accurately compute cumulative percentages for datasets that include negative values.
  - Rationale: Utilizes Error Guessing to probe potential computational errors or misinterpretations when the input data contains negative numbers, reflecting on the method's comprehensive handling of diverse numeric conditions.
- `testCumulativePercentagesWithZeroValues` (Equivalence Partitioning)
  - Objective: To evaluate the method's performance when dealing with datasets composed entirely of zero values, examining if cumulative percentages are calculated as expected.
  - Rationale: Applies Equivalence Partitioning to test a specific subset of data (zero values) within the broader input domain, ensuring the method's consistent functionality across various numeric datasets.
- `testCumulativePercentagesWithNullInput` (Error Guessing)
  - Objective: To ensure the method throws an IllegalArgumentException when provided with a null dataset, in line with its specifications.
  - Rationale: Employs Error Guessing to confirm the method's robustness in facing common erroneous inputs, such as null, safeguarding against unexpected failures and enforcing contractual adherence.

### Identified Issues
The failures in tests for normal datasets, datasets with a single value, and datasets with negative values highlight critical issues within the getCumulativePercentages method. These include
- Calculation Inaccuracies: The method appears to miscalculate cumulative percentages, as evidenced by the discrepancies in expected and actual outcomes for normal datasets.
Handling of Single Value Datasets: The method fails to correctly assign a cumulative percentage of 100% to a dataset with a single entry, suggesting a fault in its handling of such cases.
- Negative Value Processing: The incorrect cumulative percentages for datasets containing negative values indicate that the method may not properly account for or normalize negative inputs during its computation.
The DataUtilitiesGetCumulativePercentagesTest class, through its comprehensive testing approach, has uncovered significant issues within the getCumulativePercentages method that necessitate attention. These findings serve not only to highlight specific areas for improvement within the method's implementation but also underscore the importance of thorough testing in identifying and rectifying potential faults in software components. 

## E `org.jfree.data.test.CreateNumberArrayTest`
`org.jfree.data.test.CreateNumberArrayTest` is the JUnit test class that tests the functionality of the `org.jfree.data.DataUtilities.createNumberArray` method. According to the docs accompanying the `createNumberArray` method, there are some important considerations which include the following:
- The data parameter must not be null.
- The data parameter must not be empty.
- The method throws InvalidParameterException for invalid data objects.

As such there are three methods (test cases) which are `testCreateNumberArray`, `testCreateNumberArrayNullData`, and `testCreateNumberArrayEmptyData` their respective functions are as follows:
- `testCreateNumberArray` - to check for correct conversion from double data to number data.
- `testCreateNumberArrayNullData` - to check that the method throws an “InvalidParameterException” for null data.
- `testCreateNumberArrayEmptyData` - to check that the method throws an “InvalidParameterException” for empty data.
With regards to equivalence partitioning where the input data can be partitioned into valid and invalid, the `testCreateNumberArray` method satisfies the valid input partition while the `testCreateNumberArrayNullData` and `testCreateNumberArrayEmptyData` methods satisfy the invalid input partitions. Finally in terms of decision table strategy to help consider every possible input combination and the expected outcome, the three methods collectively meet that criterion. The decision table is shown in Table 8.

Table 8: Decision table for the org.jfree.data.test.CreateNumberArrayTest
| Null Data | Empty Data | Expected Outcome |
| --- | --- | --- |
| No | No | A converted array |
| No | Yes | InvalidParameterException |
| Yes | No | InvalidParameterException |


# 4 How the teamwork/effort was divided and managed

Teamwork was an important part of the lab and as such it was crucial to how the lab will be completed. Every member of the team contributed to the test suite development and creation of the lab report through the design, code development and documentation of the test cases for the chosen two methods (one from the `org.jfree.data.Range` class and another from the `org.jfree.data.DataUtilities` class). The work was mostly done independently, only collaborating to either debug a member's codebase or check in on the project's progress. The test cases were developed individually and then compiled by one of the members for consistency and correctness for the final version that was submitted. The task assignments for the members of the team are shown in Table 9.

Table 9: task assignments for each of the team members
| Team Member | Methods Under Test | Additional Duties |
| --- | --- | --- |
| Sami Abdelhalem | `org.jfree.data.test.ShiftTest` <br/> `org.jfree.data.test.GetCumulativePercentagesTest` | 
| Mohammad Hallaq | `org.jfree.data.test.GetUpperBoundTest` <br/> `org.jfree.data.test.CreateNumberArrayTest` | |
| Ogechukwu Kanu | `org.jfree.data.test.ExpandTest` <br/> `org.jfree.data.test.calculateColumnTotalTest` | Compilation of final code and finalizing lab report |
| Olayinka Afolabi | `org.jfree.data.test.GetLowerBoundTest` <br/> `org.jfree.data.DataUtilities.calculateRowTotalTest` | Completion of other sections of the lab report |
| Emmanuel Alafonye | `org.jfree.data.test.GetLengthTest` <br/> `org.jfree.data.test.CreateNumberArray2DTest` | |

# 5 Difficulties encountered, challenges overcome, and lessons learned
These tasks focused on automated unit testing, particularly when using tools like JUnit and testing frameworks such as Javadoc, presented various challenges. Some of the difficulties we encountered are as follows.
1. **Understanding Testing Concepts**: Since we are new to automated unit testing, grasping fundamental testing concepts such as test cases, test suites, assertions, and mock objects was very challenging.
2. **Tool Familiarity**: Learning to navigate and utilize testing tools like JUnit and Javadoc effectively requires time and practice. We struggled with understanding the functionalities and features offered by these tools.
3. **Interpreting Requirements**: Crafting unit tests that accurately reflect the requirements outlined in Javadocs demands a clear understanding of the specifications. Misinterpretation or ambiguity in requirements can lead to incorrect or incomplete test cases.
4. **Test Case Design**: Designing comprehensive test cases that cover various scenarios and edge cases can be complex. We found it challenging to identify all possible inputs, states, and behaviours to be tested.

Most of the difficulties were overcome through team collaboration and sharing of ideas and solutions. Particularly, interpreting the requirements of the methods in order to design the test case was mostly challenging and it can be said that such a craft is an art and improves with experience. Through online resources and research, we devised better test case designs given the requirements. 

# 6 Comments/feedback on the lab itself

The lab helped to build teamwork, collaboration and sharing. We understood our individual strengths and weaknesses which enabled us to plan accordingly. We understood the basics of unit testing and black box testing techniques. In conclusion, the lab was a success and we completed it successfully.
