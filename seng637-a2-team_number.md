**SENG 637 - Software Testing, Reliability, and Quality**

**Lab. Report \#2 – Requirements-Based Test Generation**

| Group Number 19      |
| -------------- |
| Sami Abdelhalem |
| Mohammad Hallaq |
| Ogechukwu Kanu |
|  Olayinka Afolabi |
| Emmanuel Alafonye |

# 1 Introduction

In software development, a solid grasp of automated unit testing principles is indispensable. This assignment serves as an introductory voyage into the realm of automated unit testing, specifically tailored for students. Our focus lies on crafting tests that align precisely with unit requirements, with JUnit leading the charge as a cornerstone tool in the XUnit framework family, renowned for its prowess in Java-based unit testing.

We started the assignment with a phase of familiarization, where we acquainted ourselves with the assignment's objectives and the software at hand. Subsequently, we shift our attention towards the meticulous creation of unit tests, crafted in strict accordance with the requirements outlined in Javadocs. As we progress, the final phase involves executing these test suites across various iterations of the system under scrutiny, culminating in a comprehensive collection of test results.

At the heart of these tasks lie two indispensable testing tools: JUnit and Javadoc.
The system under scrutiny in this educational endeavour is JFreeChart, a revered open-source Java framework known for its proficiency in chart computation, construction, and visualization. Offering versatility, JFreeChart caters to an extensive array of chart types, making it a staple in Java applications seeking robust charting functionalities.
As we delve into the intricacies of JFreeChart, it becomes apparent that its framework architecture is housed within the `org.jfree.data` package, which beckons exploration. Although mastery of the JFreeChart API isn't mandatory, we navigate through its functionalities, fueled by the assurance of its user-friendly design.
Ultimately, this assignment embarks on a journey of discovery, equipping us with the tools and insights necessary for proficient automated unit testing within the captivating domain of Java development.

# 2 Detailed description of unit test strategy

The unit test strategy employed for this lab was the black box testing technique. The tests cover equivalence partitioning, boundary value analysis, and decision table strategies to validate the correctness and robustness of the methods of the classes under test (`org.jfree.data.DataUtilites` and `org.jfree.data.Range`).

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
The input space for the getLength method can be divided into ranges with positive, negative, and zero lengths. Each test case covers one partition to ensure comprehensive testing.

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
- The `range` parameter must not be null
- 
- The method throws InvalidParameterException for invalid `range` data objects

As such there are four methods (test cases) which are testExpandWithValidInput, `testExpandWithNullRange`, `testExpandWithNegativeMargin` and `testExpandWithZeroMargins` and their respective functions are as follows;
- `testExpandWithValidInput` - to check for the correct output range object with valid inputs
- `testExpandWithNullRange` - to check that the method throws an “InvalidParameterException” for null “range”.
- `testExpandWithNegativeMargin` - to check for the output range object with negative margins.
- `testExpandWithZeroMargins` - to check for the output range object with zero margins.

Table 4: Decision table for `org.jfree.data.Range.expand` method

## E `org.jfree.data.test.ShiftTest`
The `Range.shift` method plays a pivotal role in adjusting data ranges by a specified delta while considering the allowance or prevention of zero crossings. Given the method's functionalities, our testing strategy is meticulously designed to encompass a wide range of scenarios using black-box testing techniques such as Equivalence Partitioning (EP), Boundary Value Analysis (BVA), and Error Guessing (EG). Below, we detail our test cases and the logic behind each, ensuring a robust evaluation of the method's behaviour.

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
The `DataUtilitiesGetCumulativePercentagesTest` class is designed to rigorously evaluate the `getCumulativePercentages` method from the DataUtilities class within the JFreeChart library. This method's primary function is to calculate the cumulative percentages of numerical data represented by KeyedValues. Our testing strategy encompasses various scenarios to ensure comprehensive validation of the method's correctness, reliability, and robustness.

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

Text…

# 5 Difficulties encountered, challenges overcome, and lessons learned
These tasks focused on automated unit testing, particularly when using tools like JUnit and testing frameworks such as Javadoc, presented various challenges. Some of the difficulties we encountered are as follows.
1. **Understanding Testing Concepts**: Since we are new to automated unit testing, grasping fundamental testing concepts such as test cases, test suites, assertions, and mock objects was very challenging.
2. **Tool Familiarity**: Learning to navigate and utilize testing tools like JUnit and Javadoc effectively requires time and practice. We struggled with understanding the functionalities and features offered by these tools.
3. **Interpreting Requirements**: Crafting unit tests that accurately reflect the requirements outlined in Javadocs demands a clear understanding of the specifications. Misinterpretation or ambiguity in requirements can lead to incorrect or incomplete test cases.
4. **Test Case Design**: Designing comprehensive test cases that cover various scenarios and edge cases can be complex. We found it challenging to identify all possible inputs, states, and behaviours to be tested.
5. **Integration Issues**: Integrating unit tests with the system under test (in this case, JFreeChart), we encountered obstacles such as setting up dependencies, configuring environments, or dealing with compatibility issues.
6. **Mock Objects**: Working with mock objects, essential for isolating components during testing, was tricky. Understanding when and how to use mock objects effectively requires careful consideration and practice.
7. **Debugging**: Troubleshooting failing test cases and debugging issues within test code can be time-consuming. We struggled with identifying the root cause of failures and rectifying them.

# 6 Comments/feedback on the lab itself

Text…
