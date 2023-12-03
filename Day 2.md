# Day 2

![Screenshot](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/blob/main/Files/day2.webp)

## Data Science in Cybersecurity

The integration of data science is rapidly gaining prominence in the field of Cybersecurity due to its capacity to provide valuable insights. The analysis of data, including log events, facilitates an intelligent comprehension of ongoing activities within an organization. An illustrative application of data science in Cybersecurity is anomaly detection. Other notable uses include:

    - **SIEM (Security Information and Event Management):** SIEM systems collect and correlate extensive data to offer a comprehensive understanding of the organization's landscape.
    
    - **Threat Trend Analysis:** Tracking and comprehending emerging threats become more effective.
    
    - **Predictive Analysis:** By scrutinizing historical events, it becomes possible to create a potential picture of the future threat landscape. This proactive approach aids in incident prevention.
    

## Jupyter Notebooks Introduction

Jupyter Notebooks represent open-source documents encompassing code, text, and terminal functionality. 
They are widely embraced in the data science and education realms, these notebooks offer seamless sharing and execution across various systems. Their versatility also makes Jupyter Notebooks an excellent tool for illustrating and elucidating proof of concepts within the field of Cybersecurity.


### Task 1: Open the notebook “Workbook” located in the directory “4_Capstone” on the VM. Use what you have learned today to analyse the packet capture.
        
        No answer needed

### Task 2: How many packets were captured (looking at the PacketNumber)?

To determine the count of columns (Packet Number), you can utilize the `dataframe.count()` function. Assuming your data frame is named `df`, the syntax would be:

```python
df.count()
```
        100

### Task 3: What IP address sent the most amount of traffic during the packet capture?

Use the `dataframe.groupby(['ColumnName']).size()` Function

To identify the IP that generated the highest amount of traffic, you can utilize the `groupby` function on the DataFrame. In this example, assuming the DataFrame is named `df` and the column of interest is named 'Source', the operation would be:

```python
df.groupby(['Source']).size()
```

`10.10.1.4`


### Task 4: What was the most frequent protocol?

Using the `value_counts()` Function in a DataFrame

To identify the most frequent protocol in a DataFrame, you can utilize the `value_counts()` function. Assuming your DataFrame is named `df` and you want to find the frequency of values in the 'Protocol' column, use the following code:

```python
df['Protocol'].value_counts()
```

`ICMP'
