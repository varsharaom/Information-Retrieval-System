# Information-Retrieval-System
Source code for the Information Retrieval Project<br>
Information Retrieval System:<br>
	<p>This project includeds the methodology to build and compare multiple information systems. Which includes:
	<ol>
		<li> BM25.</li>
		<li> Smoothed Query Likelihood. </li>
		<li> Lucene based search.</li>
		<li> TFIDF.</li>
		</ol>
	</p>
	<p>These are known as retrieval models, which are used to retrieve documents based on their Term Frequencies of the query terms.
	Also, each model modifies the term weighting in a manner to either include or exclude relevance judgements. Though our retrieval
	models are not yet advanced to read the relevance judgments at real-time, we have ignored them during the effectiveness evaluation.
	</p>
	<p>
	The Query Expansion is another technique to improve the input to these, in which, we have psuedo-relevance feedback to generate the terms which have higher probability to co-occur.</p>
<p>
	The user-results are displayed in an HTML page, where the resultant document's content can be viewed in an snippet. The important   terms or in other words, highly frequent terms are highlighted in the displayed snippets.
</p>
	<p>The evaluation of these information retrieval models are performed on basis of three criterias:
	<ol>
		<li> Mean Average Precision </li>
		<li> Mean Reciprocal Rank </li>
		<li> Precision at rank = 5 and rank = 20. </li>
		</ol>
<br>
	Their respective precision and recall values are also displayed in the seperate text file for any future evaluation purposes.
</p>
Folder Structure: (ordered by their name)
<ul>
	<li>Corpuses :	This folder consists of files which act as the Corpus for the above mentioned 
						information retrieval system.</li>
	<li>Evaluation 	:	This folder consists of files which are used to evaluate the systems.</li>
		<ul>
		<li>Files :	This sub-folder consists of intermediatory files which are used to calculate the effectiveness results of the systems </li>
		<li>Output :	This sub-folder consists of the files which are the result of performing effectiveness calculation as mentioned above. Each system is prefixed with their measure.For example:
						<ul>
						
							<li>evaluation_results.txt 	: consists of the evaluation values of Mean Avergae Precision and Mean Reciprocal Rank.</li>
						<li>	precision_at_rank_5_20_BM25 : reflects the file which consists of precision values at rank = 5 and rank = 20 for the all the queries given as input to the BM25.</li>
			</ul>
     </li>                         
     </ul>
	<li>Extra_Credit	:	This folder consists of the code and output files generated for the project's extra-credit task.
		<ul>
	<li>Noise-Generator	:	This folder consists of the python scripts and output files which are the representation of noise-generator model.</li>
	<li>Noise-Minimizer	:	This folder consists of the python scripts and output files which are the representation of the noise-minimizer model.</li>
			
  </ul>
  </li>
	<li>Indexes	:	This folder consists of the intermediate files which are used to calculate the resultant scores for a query by any
						search system.</li>
<li>
	Retrieval :	This folder is a representation of the core activites of all the information retrieval systems.
<ul><li>
		Query_Expansion	:	This folder represents the python scripts and output files which are used to generate the Query-time stemming
								model.</li>		
	<li>	Retrieval_Model	: This folder consists of the core search information and tasks for all the information retrieval systems.</li>
  <li>Stemming_and_Stopping :	This folder consists of the files which represent the python scripts used to perform the stemming and stopping on the corpus and induce those as the input to the information retrieval systems.</li>
</ul></li>
	<li>Snippet_Generation : This folder consists of the pythin scripts which are used to generate snippets and publish the results of a query in an HTML file.</li>
	<li>utilities	:	This folder represents the intermediate python scripts and queries which are used to provide as an input to the retrieval systems tasks.</li>

</ul>
Execution: <br>
<ul>
	<li>Third-Party Libraries
	 <ul>
		<li>Our project uses the nltk library to perform few key operations within the process.
		So, to execute our project, install nltk library from:
			https://www.nltk.org/install.html</li>
               <li> Our project uses the BeautifulSoup library to perform few parsing tasks. So, to execute our
		project, install BeautifulSoup using the pip tool:
			$ pip install beautifulsoup4 </li>
		<li>The Lucene Search has few core JARs which are present in the "utilities" folder. Reference them to
		your Java file before performing a build of the Java program. </li>
	</ul>
        </li>
<li>	Initially execute the files 
	<ul>
		<li>$python corpus_generator.py</li>
		<li>$python inverted_index_generator.py</li>
		<li>$python corpus_statistics.py</li>
	</ul>	
	</li>	
	<li>In the Retrieval/Retrieval_Model Folder of the project, 
		<ol>
	<li> Executing BM25_Information system:
		$python preprocessor.py<br>
		$python search.py</li>
	<li>Executing TFIDF Information System:<br>
		$python TF_IDF_Retrieval.py</li>
	<li>Executing the Smoothed Query Likelihood Model<br>
		$python SQ_Likelihood_Calculator.py</li>
	<li>Executing the Lucene Search Engine:<br>
		$javac -cp *; LuceneSearchEngine.java<br>
		$java -cp *; LuceneSearchEngine
			</li>
		</ol>
        </li>
	<li>To execute the Query_Expansion Model, redirect to Retrieval/Query_Expansion from the project root directory,<br>
	$python Task-2.py
</li>
	<li>To execute the Snippet_Highlighting, redirect to Snippet_Generation from the project root directory<br>
		$python SnippetGeneration_Highlighting.py
        </li>
	<li>To execute the Stemming and Stopping runs, redirect to Retrieval/Stemming_and_Stopping/ and execute
		<ul>
			<li>
		for stemming: <br>
			$python stemmed_corpus_generator.py<br>
			and execute the retrieval models by modifying the commented lines in each core file.<br>
			</li>
			<li>
		for stopping:
			$python stopped_corpus_generator.py
			$python stopped_query_generator.py
	 		and execute the retrieval models by modifying the commented lines in each core file.
			</li>
		</ul>
        </li>
	<li>To execute the Evaluation files, redirect to the Evaluation folder from the project root and execute <br>
		$python evaluation_script.py
        </li>
	<li>To execute the Noise Generator Model, redirect to the Extra_Credit/ folder from the root folder 
		<ul>
   <li>to generate noise<br>
			execute<br>
	   $python noise_generator.py</li>
	<li>	to minimize the noise<br>
			execute<br>
		$python noise_minimizer.py</li>
		</ul>
		</li>
</ul>
