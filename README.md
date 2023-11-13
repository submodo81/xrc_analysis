# xrcAnalysis
Created a Python script to automate processing of x-ray rocking curve files. The parsing that is performed in this file was specifically developed for .csv files generated from Panalytical x-ray diffraction tools.

I developed this jointly with Tia Gray as part of our collaborative work on the development of etching processes for bulk single crystal diamond.

There are some issues with the code.
1. It cannot parse the converted Panalytical file in .csv format as-received. You first need to delete the row starting with the word "Divergence". This row will cause error in parse the file.
2. The prompts are not 100% clear, please carefully read the prompt for information to give the correct input. Incorrect input will not cause the code to stop working, but will be confusing for you to read later. I hope to fix this later.
3. The Chi-square value is quite low for my test datasets, although the fitting it visually quite good and for single diffraction peaks R-squared values are >0.999 for the datasets that I've tested on single crystal diamond peaks. I am not sure what the issue is the chi-squared yet, but I suspect it's related to the large number of data points that don't contain the diffraction peak. I hope to address this in future versions.

Some additional notes related to using the code and its output:
1. Testing: I have only tested this script on Windows systems using Spyder v5.4.3 in Anaconda.
2. Inputting data: Right after you run the script it will prompt you to enter the file path of the file you want to process. For Windows users locate the directory where your file is stored, right-click or shift + right-click and scroll down to 'Copy as path'. Then paste this path into the script.
3. Output: The files will save to your working directory. In testing, I pointed Spyder to my chosen directory and copied the generated files over to another. You can chose whatever works best for you.
4. Figures: The figures save as scalable vector graphics (.svg) files. I like these as they perserve resolution well and aren't too memory intensive. I have not had any issues dropping these into powerpoint presentations but they may not work well in all situations.
5. Data files: The script adds extra columns and retains all the original columns. Consequently the file size increases by roughly double. Please keep this in mind when running this script.
