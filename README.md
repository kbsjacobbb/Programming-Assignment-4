# ECE 2112 - Experiment 4: Data Wrangling and Data Visualization

Balagtas, Jacob T.

2ECE-B

9/17/2026

## Objective of the Experiment

The objective of this experiment is to hone and develop Python skills. In these activities, the programmer tackles **Data Wrangling and Data Visualization**. These will help in gaining knowledge and developing skills in concepts such as filtering data using conditions, constructing focused DataFrames, and summarizing relationships between categorical features and numerical variables. 

### General Codes:

    import pandas as pd

The code above is a Python command that imports the **pandas** library and uses the alias "pd" to shorten it.

    import matplotlib.pyplot as plt

Just like the first code, it is a Python command that imports the **pyplot** module from the **matplotlib** library and uses the alias **plt** to shorten it.

## A. VISAYAS COMMUNICATION DATAFRAME

### Code: 

    df = pd.read_excel("board2.xlsx")
    df

The code above reads the imported file and displays its contents.

    score_columns = ["Math", "Electronics", "GEAS", "Communication"]
    score_columns

The code above identifies the score for each test that each individual took in Math, Electronics, GEAS, and Communication.

    df["Average"] = df[score_columns].mean(axis=1)
    df

This code then computes the average of the scores they received in those categories. 

    VisComm = df[(df["Hometown"] == "Visayas") & (df["Track"] == "Communication")]
    VisComm

The code above filters the list to identify only people who live in Visayas and have a Communication track.

    Vis_Comm = VisComm[["Name", "Gender", "Math", "Electronics", "Average"]]
    Vis_Comm

The code above then identifies the name, gender, Math and Electronics scores, and the average of the filtered list.

## B. VISAYAS FEMALE DATAFRAME

### Code:

    Vis_Fem = df[(df["Hometown"] == "Visayas") & (df["Gender"] == "Female")]
    Vis_Fem

Just like one of the codes from the first activity, this code filters the list to identify only people who live in Visayas and are Female.

    VisFemale = Vis_Fem[["Name", "Track", "GEAS", "Electronics", "Average"]]
    VisFemale

Also, like a code from earlier, it identifies the name, track, GEAS and Electronics scores, and the average of the filtered list.

    VisFemale[VisFemale["Average"] >= 60]

This code then further filters the list by identifying only people who achieved an average of 60 or higher.

## C. CATEGORY-AVERAGE VISUALIZATION

### Code:

    average_track = df.groupby("Track")["Average"].mean()
    average_track

    average_gender = df.groupby("Gender")["Average"].mean()
    average_gender

    average_hometown = df.groupby("Hometown")["Average"].mean()
    average_hometown

These lines of code display the average scores of each of the three categories: Track, Gender, and Hometown.

    average_track.plot(kind="bar", figsize=[10, 6])

    plt.title("Mean Average by Track")
    plt.xlabel("Track")
    plt.ylabel("Mean Average")
    plt.xticks(rotation=0)
    plt.tight_layout()
    plt.show()
--------------------------------------------------------------
    average_gender.plot(kind="bar", figsize=[10, 6])

    plt.title("Mean Average by Gender")
    plt.xlabel("Gender")
    plt.ylabel("Mean Average")
    plt.xticks(rotation=0)
    plt.tight_layout()
    plt.show()
--------------------------------------------------------------
    average_hometown.plot(kind="bar", figsize=[10, 6])

    plt.title("Mean Average by Hometown")
    plt.xlabel("Hometown")
    plt.ylabel("Mean Average")
    plt.xticks(rotation=0)
    plt.tight_layout()
    plt.show()

These lines of code display the bar graphs of the results from the first set of lines of code.







