1) Check Instance Health on AWS (right now it is a small instance) so do not index all documents.
2) The format of data in Central Acts has changed significantly. Create a new "iterate val" function for those. State Acts remain in the same format as of now.
3) While bulk importing data to ElasticSearch use small batches of documents or it might crash midway due to too many requests.
4) IMPORTANT:- The format for Elasticsearch is an index first and then the document. Example: -"index = {"index":{"_index":"acts","_id":str(i)}}".
5) We will need atleast three indexes as of now. 
	a) Where each Act is indexed as one document and a query returns the whole act.
	b) Where each Chapter of an act is indexed as one document an a query returns a particular Chapter of the Act.
	c) Where each Section (inside Chapter) is indexed as one document and a query returns a particular Section of the Act.
