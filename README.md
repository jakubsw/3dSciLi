# 3dSciLi
Scientific Literature Network Visualization in 3d

http://3dscili.scienceontheweb.net/

Welcome to 3dSciLi: a simple web tool for 3d visualization of bibliographic data networks!


1. General information

1.1. The purpose of the tool

3dSciLi can visualize in 3D five types of bibliographic data networks: work citations and co-citations, author citations and co-authorship, as well as keyword co-occurrence.

The tool requires only an input of a set of bibliographic database search results, freeing the researchers from using a pipeline of programs and manual processing of data for the sake of their 3D visualization.

The tool operates purely in your browser (there is no server-side processing), all the data stay on your own machine, so there is no need for you to worry about privacy and third-party data use limitations.

1.2. Technical requirements

The tool should operate properly in all modern browsers. Note that to get real-time animation of complex networks comprising thousands of nodes and edges, you will need a capable video card. An integrated graphics card is sufficient to get smooth visualization of small networks, but when visualizing larger networks you may see stuttering and delays, increasing with the size of the network.

2. Loading data

2.1. Viewing exemplary data

If you have no own data prepared, yet want to see 3dSciLi in action, click on Load Demo. This will load a graph prepared by me for testing purposes. Note that it depicts quite a large network, so its visualization may be slow on computers with integrated graphics (see 1.2).

2.2. Importing bibliographic data

This is the standard way of getting the data into the tool. Click Import CSV file to load a SCOPUS-compliant CSV file from your disk. Note that only .CSV files are visible in the file selector.

The expected CSV file content should comprise, at minimum, the following columns:

Authors, names of the publication authors,
Author(s) ID, identification numbers of the paper authors, allowing to distinguish people having the same name,
Title of the publication,
Year of the publication,
Cited by, number of publications which cited this one,
Link to the full bibliographic record at SCOPUS,
Author Keywords, the keywords defined by the author,
References, the list of publications cited by this one.
If you have access to SCOPUS, you can generate such a file by performing a query and then clicking on the CSV Export button. In the Export document settings form, you need to choose CSV Excel as the format and mark at least the following information to export:

all items in Citation information column (not all of them are used by 3dSciLi at the moment, but it's easier this way),
Author keywords in the Abstract & keywords column,
Include references in the Other information column.
I am working at providing similar import feature for Web of Science.

Note that processing large (several-megabytes-long) bibliographic data files takes a lot of time (depending on your processor and the size of the file, it can get to minutes), so it is recommended to save the data once they are imported as a JSON file (see 3.1).

2.3. Reloading data from your disk

If you have already saved your processed data as a JSON file (see 3.1), you can reload them using the Load from Disk button. Note that only .JSON files are visible in the file selector.

2.4. Reloading data from your browser storage

If you have saved your processed data in your browser's LocalStorage (see 3.2), you can reload them using the Reload from LocalStorage button.

Note that the data are not stored server-side: they are stored in the environment of your browser. So, they won't be accessible from another machine or even from another browser used on the same machine. Note also that LocalStorage has the limit of about 5 megabytes, which means that larger networks could not be saved there.

3. Saving processed data

3.1. Saving data to your disk

You can save the currently viewed data on your disk as a JSON file using the Save to Disk button. This way, they could be later reloaded (see 2.3) without having to waste time on the long CSV import.

3.2. Saving data to your browser storage

If you keep working on a single file and want to avoid having to choose it in the file selector, you can store it in the LocalStorage of your browser using the Save to LocalStorage button (see 2.4 to learn how such file can be reloaded).
Note that the data are not stored server-side: they are stored in the environment of your browser. So, they won't be accessible from another machine or even from another browser used on the same machine. Note also that LocalStorage has the limit of about 5 megabytes, which means that larger networks could not be saved there.

4. Viewing data

4.1. Basic metadata

In the top left corner of the screen (next to Help and Info buttons), basic data set information is provided:
File: the name of the file loaded (if any),
Authors: the number of authors found in the dataset,
Works: the number of works found in the dataset,
Displayed: the number of works actually displayed (remember that disconnected nodes are not displayed).

4.2. Browsing the list of works

Click the Works button to open the pane with a table listing all works (including their title, year of publication and the number of citations), sorted by the number of citations. Note that the number of citations shown there is the total number of citations provided by the bibliographic database, not the number of citations covered in the visualized dataset (which will usually be much smaller, depending on the scope of the visualized query results). Click the Works button again to close this pane.

4.3. Browsing the list of authors

Click the Authors button to open the pane with a table listing all authors (including their name and the number of works covered in the visualized dataset), sorted by the number of citations. Click the Authors button again to close this pane.

4.4. Browsing the list of keywords

Click the Keywords button to open the pane with a table listing all keywords (including the keyword itself, the earliest year it was mentioned in the visualized dataset, and the number of works covered in the visualized dataset that use them), sorted by the number of works using them. Click the Keywords button again to close this pane.

5. Network 3D visualization

5.1. Viewing controls

Regardless of the type of visualized network, the user can freely zoom the view in and out using the mouse wheel and rotate the view by moving the mouse with the left mouse button pushed down. Hovering the mouse cursor over a node displays a short textual information about it, whereas clicking on a publication or author node opens a separate browser tab displaying a web page with its full bibliographic record. Note that in the case of large networks, it will take some time on machines with integrated graphics to get the graph drawn and then redrawn after each view change.

5.2. Shown content restrictions

Regardless of the graph type, the disconnected single nodes are not displayed. In the author graphs, only the authors having unique ID numbers assigned in the bibliographic database are included.

5.3. Publication citation graph

Click the Citations button in the Works section to draw the publication citation graph. In this graph, the publications are shown as nodes and citations are edges. The nodes are drawn as circles whose size is proportional to the number of citations received by a given publication, whereas color denotes its relative age: from blue (the oldest) to red (the latest).

5.4. Publication co-citation graph

Click the Co-citations button in the Works section to draw the publication co-citation graph. In this graph, the publications are shown as nodes which are connected only if they were cited together in another paper. The nodes are drawn as circles whose size is proportional to the number of co-citations of a given publication, whereas color denotes its relative age: from blue (the oldest) to red (the latest).

5.5. Author citation graph

Click the Citations button in the Authors section to draw the author citation graph. In this graph, the authors are shown as nodes and citations are edges. The nodes are drawn as circles whose size is proportional to the number of works written by a given author, and the color depends on the number of works citing the author: from blue (the least) to red (the most).

5.6. Co-authorship graph

Click the Co-authors button in the Authors section to draw the co-authorship graph. In this graph, the authors are shown as nodes which are connected only if the two authors wrote together at least one paper. The nodes are drawn as circles whose size is proportional to the number of works written by a given author, and the color depends on the number of works citing the author: from blue (the least) to red (the most).

5.7. Keyword co-occurence graph

Click the Co-occurence button in the Keywords section to draw the keyword co-occurence graph. In this graph, the keywords are shown as nodes which are connected only if they were used together in at least one paper. The node circle size is determined by keyword popularity, whereas its color by the year the keyword was used for the first time: from blue (the oldest) to red (the latest).
