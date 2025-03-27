# Large Scale Data Processing: Project 2
## Getting started
Head to [Project 1](https://github.com/CSCI3390Spring2025/project_1) if you're looking for information on Git, template repositories, or setting up your local/remote environments.

## Resilient distributed datasets in Spark
This project will familiarize you with RDD manipulations by implementing some of the sketching algorithms the course has covered thus far.  

You have been provided with the program's skeleton, which consists of 5 functions for computing either F0 or F2: the BJKST, tidemark, tug-of-war, exact F0, and exact F2 algorithms. The tidemark and exact F0 functions are given for your reference.

## Relevant data

You can find the TAR file containing `2014to2017.csv` [here](https://drive.google.com/file/d/1MtCimcVKN6JrK2sLy4GbjeS7E2a-UMA0/view?usp=sharing). Download and expand the TAR file for local processing. For processing in the cloud, refer to the steps for creating a storage bucket in [Project 1](https://github.com/CSCI3390Spring2025/project_1) and upload `2014to2017.csv`.

`2014to2017.csv` contains the records of parking tickets issued in New York City from 2014 to 2017. You'll see that the data has been cleaned so that only the license plate information remains. Keep in mind that a single car can receive multiple tickets within that period and therefore appear in multiple records.  

**Hint**: while implementing the functions, it may be helpful to copy 100 records or so to a new file and use that file for faster testing.  

## Calculating and reporting your findings
You'll be submitting a report along with your code that provides commentary on the tasks below.  

1. **(3 points)** 
On GCP: Exact F2. Time elapsed:76s. Estimate: 8567966130
2. **(3 points)** Once you've implemented the function, set `width` to 10 and `depth` to 3. Run `Tug_of_War` locally **and** on GCP with 1 driver and 4 machines having 2 x N1 cores. Copy the results to your report. Terminate the program if it runs for longer than 30 minutes.
  - On GCP: Tug-of-War F2 Approximation. Width :10. Depth: 3. Time elapsed:579s. Estimate: 10146147119
4. **(3 points)** Implement the `BJKST` function. The function accepts an RDD of strings, a parameter `width`, and a parameter `trials` as inputs. `width` denotes the maximum bucket size of each sketch. The function should run `trials` sketches and return the median of the estimates of the sketches. A template of the `BJKSTSketch` class is also included in the sample code. You are welcome to finish its methods and apply that class or write your own class from scratch. A 2-universal hash function class `hash_function(numBuckets_in: Long)` has also been provided and will hash a string to an integer in the range `[0, numBuckets_in - 1]`. Once you've implemented the function, determine the smallest `width` required in order to achieve an error of +/- 20% on your estimate. Keeping `width` at that value, set `depth` to 5. Run `BJKST` locally **and** on GCP with 1 driver and 4 machines having 2 x N1 cores. Copy the results to your report. Terminate the program if it runs for longer than 30 minutes.
5. **(1 point)** Compare the BJKST algorithm to the exact F0 algorithm and the tug-of-war algorithm to the exact F2 algorithm. Summarize your findings.
  - Exact F0. Time elapsed:66s. Estimate: 7406649

## Submission via GitHub
Delete your project's current **README.md** file (the one you're reading right now) and include your report as a new **README.md** file in the project root directory. Have no fear—the README with the project description is always available for reading in the template repository you created your repository from. For more information on READMEs, feel free to visit [this page](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/about-readmes) in the GitHub Docs. You'll be writing in [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown). Be sure that your repository is up to date and you have pushed all changes you've made to the project's code. When you're ready to submit, simply provide the link to your repository in the Canvas assignment's submission.

## You must do the following to receive full credit:
1. Create your report in the ``README.md`` and push it to your repo.
2. In the report, you must include your (and your group members') full name in addition to any collaborators.
3. Submit a link to your repo in the Canvas assignment.

## Late submission penalties
Please refer to the course policy.
