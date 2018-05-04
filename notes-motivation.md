FORWARD Notebooks

Notebooks are extensively used by data scientists to perform analyses and explore hypotheses.


Challenges with Notebooks for data analysts:

* Loading data. Traditionally notebooks do not provide a universal easy-to-use way for connecting with multiple sources out of the box. In order for data analysts to run an analysis in a notebook:
    * They often need to send CSV, JSON or other files to the server that hosts the notebook in order to run their analysis  
        * This often requires the use of command line (ssh,scp etc) to send the data to the server, which shouldn't be a responsibility of the data analyst.
        * Opening such files and loading them in the main memory also is mundane and time consuming and slows down the actual analysis.

    * If they wish to use data that already exist in some database:
       * They either need to create scripts that interacts with databases and generate the (JSON,CSV etc) files locally and then push them to the notebook server.
       * Or they can use the appropriate database driver from the editor of the notebook. In order for this to take place they need to install the appropriate drivers on the notebook server.
        * Installing these drivers also requires the use of the command line to directly access remote sources. Usually, this set up is very technical and system specific, so it shouldn't be a responsibility of a data analyst.
        * Then imperative logic is required to utilize such drivers, connect to the underlying sources and load the appropriate data into the main memory.
        * Connecting with remote sources often requires the use of security credentials. Notebooks expose every part of the code to the person who interacts with it, therefore these credentials are often exposed to the reader of the analysis since they are inlined in the UI of the notebook. This is a major security concern. (FORWARD Notebook allows the importing of a configuration file that is hidden from the user interface).

* Visualizing data. Visualizations are a vital part of any data science project and are heavily used in notebooks. However:
  * Adding a visualization to a notebook is still fairly labor intensive.
    1. Adding a visualization requires the installation of a corresponding visualization library. This installation once again crosses the boundaries of what a data analyst should do, since it requires access to the notebook server and use of the command line to install the appropriate libraries.
    2. Additionally, each such library has a different API, which means that the data analyst would also have to familiarize herself with the API of each library she decides to use. This means that she would have to read long documentation pages that describe how to construct the much needed graphs and then follow these instructions while using imperative code.
    3. Lastly, while some such libraries produce interactive visualizations (for instance the reader of the notebook can zoom in and out of maps, select a particular area of a chart) this interactivity is not an integral part of the data analysis. This means that the notebooks do not inherently utilize the actions of the user as a means to further explore the data.


* Allow some basic data processing (filtering/joins etc) using the template language
* For the rest define functions and delta functions and use them from the template language


What contributions do we have?
1.Fundamentally visualizations require a nested data model. We use JSON because
2.JSON is the go to data model for interactive visualizations, so we created a language that works seemlessly with them.
3.Also the conversion from relational to JSON is trivial


|Visitors|
|-------------|
| vid | name | lastname| username| age |


|Page Views|
|-------------|
| pid | vid | url| time | day |


