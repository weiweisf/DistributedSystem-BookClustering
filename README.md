# DistributedSystem-BookClustering 


## Overview

The purpose of this project is to find out similar books according to the Amazon reviews. We could help the library improve its books management ecosystem and user experience by recommending those books that should’ve been checked out more but because of unsatisfying management, they were not noticed by people. 

Our method is to get the feature vectors of each book by applying TFIDF to collections of the texts of corresponding books and use these feature vectors to cluster the books. Once we get the clusters, we would have some sense of book similarities. We can even try calculating distances between every two books in one cluster. In this way, we can recommend similar books to the library to help them purchase new books and manage existing books.

The large scale of dataset makes this pipeline and approach impractical to implement on the local machine due to the limit of memory and computing performances. Consequently, we built a data pipeline with a distributed system. Amazon Web Services (AWS) provides high availability and scalability and makes its components including storage and processing engines to be compatible. Thus, for this project, we selected it as the primary platform to store data in the data lake(S3), load data into the distributed database **(MongoDB on EC2)** and apply machine learning algorithms **(Spark on EMR)**. 
