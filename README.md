# Lab 2 Submission
# Key Recovery using Correlation Power Analysis (CPA)

This folder contains three .py files. <lab2.py>, <lab2 no leakage pt.py>, and <lab2UsingHW_ExtraCredit.py> down I will explain them and necessary info to run them accordingly. 

Bofore that, I introduced necesssary libraries to run my code Python environment for this particular Lab I used the following; 

- **NumPy**: For numerical operations and data handling.
- **SciPy**: For statistical functions, particularly `pearsonr` for calculating Pearson correlation.
- **Matplotlib**: For data visualization.

Now let me explain these 3 .py files one by one. 

1. <lab2.py>
This script implements a key recovery method using Correlation Power Analysis (CPA) on AES-encrypted ciphertexts and corresponding power traces. **For In deth explanation of this task see the writeup pdf.** 
//Key Features: Most parts of my codes contains the comment to specify each part of my code.

How to run: Make sure to load give data traces and ciphertext (which I used in my case), ensuring to specify their directory path.
traces_file = './handout/data/traces.txt'
cipher_file = './handout/data/ciphers.txt'

*This file have these four main parts* 
**ds power trace and ciphertext data from specified text files.
**Plots the power consumption for the first trace.
**Implements the CPA algorithm to recover the AES key.
**Visualizes correlation results for each key byte guess, both plots will appear similitaneously. 


2. <lab2_no_leakage_pt.py>
This script is a variant of the first one, designed to simulate the key recovery process without leakage points in the power traces.  I focused on key 0, and used triple for loop to iterate leakage point 2600 ~ 2700, guess key0 0~255, and traces 0 ~ 7000 to find which leakage point can get max correction.

//Key Features: Most parts of my codes contains the comment to specify each part of my code.

This script is a variant of the first one (lab2.py), designed to simulate the key recovery process without leakage points in the power traces. I focused on key byte 0 and used a triple nested loop to iterate over the leakage points (2600 to 2700), key byte guesses (0 to 255), and power traces (0 to 7000). For each key byte guess, the script calculates the Hamming distance between the output of the inverse S-box and the corresponding ciphertext byte. It then computes the Pearson correlation coefficient between the calculated Hamming distances and the power traces to identify the leakage point that yields the highest correlation. Finally, the script prints the best key byte guess and its corresponding leakage point, along with an optional visualization of the correlation coefficients.


3. <lab2UsingHW_ExtraCredit.py>
This Python script simulates the key recovery process for AES encryption by analyzing power traces and ciphertexts, focusing on the first key byte. It calculates the Hamming Weight of the inverse S-box output based on the ciphertext and a predefined correct key byte, and computes Pearson correlation coefficients between the calculated Hamming Weights and power traces for a specified range of leakage points (2400 to 2500). After identifying the leakage point with the highest correlation, the script outputs the best leakage point and maximum correlation value, and optionally visualizes the results with a plot to illustrate the correlation coefficients, aiding in the analysis of the key recovery process.