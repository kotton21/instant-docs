##Summary:

instant-docs is an extension for VS Code which allows instant access to the python documentation rather than the traditional aproach, where a user is required to switch windows, and manually enter search terms. 

##Detailed:

The user may type as usual into the editor. A key combination triggers the extension to search the docs for a word or phrase

The extension will pick the search terms based on the following heierarchy:
  1. A highlighted word or phrase
  2. The word including the cursor
  3. The last entered word, if the cursor is not in the editor.
  
If the query obtains a page with a module, class, or method, the extension immediately switches to a browser and open the page. Otherwise, display a list of pages returned by the query and allow user to select one.

##Functionality:

One posibility is to simply query the online search terms on the documentation website. This would require an internet connection, but would be simple to make. 

Offline functionality requires a full index of the python documentation to be built for a given version:

+Create Metadata and document vectors for each page in the documentation. 
  Title, date, python version, doc(without tags?)
  
+Create an Index, database statistics, and document statistics.
  Term Frequency, document frequency, etc
  
+Pay special attention to words following "class", "method", or "module".
+Give priority to terms within heading tags.

During the query, compute a score based on the search terms and the document statistics. 

If the score is high enough, open the document directly. Otherwise, open a list to allow the user to pick one. 
