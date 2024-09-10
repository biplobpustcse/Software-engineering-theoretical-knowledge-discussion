# Software engineering theoretical knowledge discussion
## MongoDB

<ol>
<li><strong> What is MongoDB?</strong></li>
</ol>
<p><strong>Answer:</strong>&nbsp;MongoDB is a cross-platform, document-oriented, NoSQL database. It stores data in a type of JSON format called BSON. A record in MongoDB is a document, which is a data structure composed of key value pairs similar to the structure of JSON objects. It&rsquo;s designed for scalability and flexibility, making it ideal for applications that handle large volumes of unstructured data.</p>
<p>MongoDB is a document database and can be <strong>installed locally or hosted in the cloud.</strong></p>
<ol start="2">
<li><strong> How does MongoDB differ from traditional relational databases (RDBMS)?</strong></li>
</ol>
<p><strong>Answer:</strong></p>
<ul>
<li><strong>Schema:</strong> MongoDB is schema-less, while RDBMS databases have a fixed schema.</li>
<li><strong>Data Format:</strong> MongoDB stores data as documents (BSON), while RDBMS stores data in tables with rows and columns.</li>
<li><strong>Relationships:</strong> RDBMS supports joins to represent relationships between entities; MongoDB uses embedded documents or references.</li>
<li><strong>Scalability:</strong> MongoDB is built for horizontal scaling (sharding), whereas RDBMS typically scales vertically.</li>
</ul>
<ol start="3">
<li><strong> What is a replica set in MongoDB?</strong></li>
</ol>
<p><strong>Answer:</strong> A replica set is a group of MongoDB instances that maintain the same dataset, providing redundancy and high availability. It consists of:</p>
<ul>
<li><strong>Primary:</strong> Receives all write operations.</li>
<li><strong>Secondary:</strong> Replicates data from the primary and can become the new primary if the current primary fails.</li>
<li><strong>Arbiter:</strong> Does not store data but helps in the election of a new primary if necessary.</li>
</ul>
<ol start="4">
<li><strong> Explain Sharding in MongoDB.</strong></li>
</ol>
<p><strong>Answer:</strong> Sharding is MongoDB's approach to horizontal scaling, allowing it to distribute data across multiple servers or clusters. Each shard holds a portion of the data. A sharded cluster consists of:</p>
<ul>
<li><strong>Shards:</strong> Store data.</li>
<li><strong>Config Servers:</strong> Store metadata and configuration settings.</li>
<li><strong>Mongos:</strong> Acts as a query router between the application and the shards.</li>
</ul>
<ol start="5">
<li><strong> What are the different types of indexes in MongoDB?</strong></li>
</ol>
<p><strong>Answer:</strong></p>
<ul>
<li><strong>Single Field Index:</strong> Indexes on a single field.</li>
<li><strong>Compound Index:</strong> Indexes on multiple fields.</li>
<li><strong>Multikey Index:</strong> Used for indexing arrays.</li>
<li><strong>Text Index:</strong> Allows text search within string content.</li>
<li><strong>Geospatial Index:</strong> Used for location-based queries.</li>
<li><strong>Hashed Index:</strong> Used for sharded collections, supporting hash-based sharding.</li>
</ul>
<ol start="6">
<li><strong> How does MongoDB ensure data consistency?</strong></li>
</ol>
<p><strong>Answer:</strong> MongoDB provides tunable consistency levels:</p>
<ul>
<li><strong>Write Concerns:</strong> Allows control over the acknowledgment of writes. E.g., w=1 ensures the write reaches the primary, w=majority ensures it reaches the majority of nodes.</li>
<li><strong>Read Concerns:</strong> Control the consistency of data when reading from a replica set. Options include local, majority, and linearizable.</li>
</ul>
<ol start="7">
<li><strong> What is aggregation in MongoDB?</strong></li>
</ol>
<p><strong>Answer:</strong> Aggregation is a process in MongoDB that processes data records and returns computed results. It&rsquo;s similar to GROUP BY in SQL but more powerful. MongoDB supports various stages in its aggregation pipeline such as $match, $group, $project, $sort, $lookup, and $unwind.</p>
<ol start="8">
<li><strong> What is the difference between </strong><strong>find()</strong><strong> and </strong><strong>aggregate()</strong><strong> in MongoDB?</strong></li>
</ol>
<p><strong>Answer:</strong></p>
<ul>
<li><strong>find()</strong> is used for simple querying of documents that match specific criteria.</li>
<li><strong>aggregate()</strong> is used for more complex operations, such as data transformation and analysis, using stages in a pipeline.</li>
</ul>
<ol start="9">
<li><strong> What is MongoDB&rsquo;s transaction model, and how is it implemented?</strong></li>
</ol>
<p><strong>Answer:</strong> MongoDB supports multi-document ACID transactions, ensuring atomicity, consistency, isolation, and durability across multiple documents and collections. Transactions can span across multiple shards. They are used with the startTransaction(), commitTransaction(), and abortTransaction() methods.</p>
<ol start="10">
<li><strong> Explain the purpose of </strong><strong>$lookup</strong><strong> in MongoDB.</strong></li>
</ol>
<p><strong>Answer:</strong> The $lookup stage in MongoDB&rsquo;s aggregation pipeline is used to perform a left outer join between two collections. This is akin to joining tables in SQL.</p>
<ol start="11">
<li><strong> How do you optimize MongoDB performance?</strong></li>
</ol>
<p><strong>Answer:</strong></p>
<ul>
<li><strong>Indexing:</strong> Proper use of indexes can greatly speed up queries.</li>
<li><strong>Sharding:</strong> For large-scale applications, using sharding helps distribute the load across multiple servers.</li>
<li><strong>Avoid Unnecessary Writes:</strong> Minimize the frequency of write operations and use bulk writes when possible.</li>
<li><strong>Use Embedded Documents Carefully:</strong> Although embedded documents can reduce the need for joins, they should be used only when it makes sense from a data modeling perspective.</li>
<li><strong>Projection:</strong> Only fetch the fields you need by using projections to limit the data returned by queries.</li>
</ul>
<ol start="12">
<li><strong> What are capped collections in MongoDB?</strong></li>
</ol>
<p><strong>Answer:</strong> Capped collections are fixed-size collections that maintain insertion order and automatically delete the oldest documents when the collection reaches its maximum size. These are useful for logging and caching scenarios.</p>
<ol start="13">
<li><strong> What is the WiredTiger storage engine in MongoDB?</strong></li>
</ol>
<p><strong>Answer:</strong> WiredTiger is the default storage engine for MongoDB, providing efficient compression, concurrency control, and support for document-level locking. It improves performance, especially for write-heavy workloads.</p>
<ol start="14">
<li><strong> How does MongoDB handle large data volumes?</strong></li>
</ol>
<p><strong>Answer:</strong> MongoDB can handle large data volumes by:</p>
<ul>
<li><strong>Sharding:</strong> Distributing data across multiple servers.</li>
<li><strong>Indexes:</strong> Creating efficient indexes to reduce query times.</li>
<li><strong>Capped Collections:</strong> Managing collections with limited size.</li>
<li><strong>Efficient Data Modeling:</strong> Optimizing the structure of collections and documents.</li>
</ul>
<ol start="15">
<li><strong> What are the benefits and drawbacks of using MongoDB?</strong></li>
</ol>
<p><strong>Answer:</strong> <strong>Benefits:</strong></p>
<ul>
<li>Flexible schema.</li>
<li>Scales horizontally via sharding.</li>
<li>Easy integration with cloud services.</li>
<li>Rich querying capabilities with an aggregation framework.</li>
</ul>
<p><strong>Drawbacks:</strong></p>
<ul>
<li>Lacks strong ACID guarantees compared to traditional RDBMS (though multi-document transactions are supported).</li>
<li>Less efficient for complex joins compared to relational databases.</li>
<li>Indexing strategy needs to be carefully planned for optimal performance.</li>
</ul>
<ol start="16">
<li><strong> What is MongoDB Atlas?</strong></li>
</ol>
<p><strong>Answer:</strong> MongoDB Atlas is a fully managed cloud database service that handles deployment, maintenance, and scalability. It allows developers to focus on building applications without worrying about managing infrastructure.</p>
<ol start="17">
<li><strong> How do you handle schema migrations in MongoDB?</strong></li>
</ol>
<p><strong>Answer:</strong></p>
<ul>
<li><strong>Schema-less nature:</strong> MongoDB doesn&rsquo;t have built-in schema migration tools like traditional RDBMS.</li>
<li><strong>Migration Tools:</strong> Tools like mongomigrate or custom scripts can be used to handle schema migrations.</li>
<li><strong>Rolling Migrations:</strong> Schema changes can be handled in a rolling manner by updating documents over time, allowing backward compatibility with older documents.</li>
</ul>
<ol start="18">
<li><strong> Explain GridFS in MongoDB.</strong></li>
</ol>
<p><strong>Answer:</strong> GridFS is a MongoDB specification for storing and retrieving large files, such as images or videos, that exceed the BSON-document size limit of 16MB. GridFS splits the file into chunks and stores each chunk as a separate document.</p>
<ol start="19">
<li><strong> How do you ensure high availability in MongoDB?</strong></li>
</ol>
<p><strong>Answer:</strong> High availability is ensured by:</p>
<ul>
<li><strong>Replica Sets:</strong> Using replica sets to replicate data across multiple servers. If the primary fails, one of the secondaries is automatically promoted to primary.</li>
<li><strong>Automated Failover:</strong> MongoDB automatically handles failovers in the event of a node failure.</li>
</ul>
<ol start="20">
<li><strong> How would you scale MongoDB for write-heavy workloads?</strong></li>
</ol>
<p><strong>Answer:</strong></p>
<ul>
<li><strong>Sharding:</strong> Distribute the write load across multiple shards.</li>
<li><strong>Write Concerns:</strong> Optimize write concerns to balance between speed and data safety.</li>
<li><strong>Bulk Writes:</strong> Use bulk operations to improve write performance.</li>
<li><strong>Schema Design:</strong> Design your schema to minimize the number of writes and updates required.</li>
</ul>
<p>&nbsp;</p>


