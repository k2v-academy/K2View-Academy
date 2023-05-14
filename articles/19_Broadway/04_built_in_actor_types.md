# Built-In Actor Types

Broadway has a large list of built-in [Actors](03_broadway_actor.md#actor-overview) that can be added to a flow to create various types of activities. Broadway's built-in Actors are split into categories, where each category includes several Actor types.

The following table presents a list of Actors categories with examples of each category. This is not an exhaustive list of Actors.

[Click for more information about the most useful Actors and code examples](actors/README.md).

<table style="width: 900px; height: 4040px;">
<tbody>
<tr style="height: 54px;">
<td style="height: 54px; width: 295.969px;">
<h3><strong>Category Name &amp; Description</strong></h3>
</td>
<td style="height: 54px; width: 588.031px;">
<h3><strong>Examples per Category</strong></h3>
</td>
</tr>
<tr style="height: 242px;">
<td style="vertical-align: top; height: 242px; width: 295.969px;">
<p>Category Name: <strong>Favorites</strong>&nbsp;</p>
<p>Description: Most commonly used Actors.</p>
<p>Favorites is not a separate category. Each Actor in Favorites belongs to a category.</p>
<p>Click <img src="images/99_favorites.PNG" alt="lev" /> in an Actor's description in the Add Actors window to add the Actor to Favorites.</p>
<p>Actors in Favorites have a <img src="images/99_favorites1.PNG" alt="lev" /></p>
</td>
<td style="vertical-align: top; height: 242px; width: 588.031px;">
<p><strong>Const</strong> Actor, copies the input value argument to the output value argument. A Const Actor can:</p>
<ul>
<li>Pass a constant value to the next Actor.</li>
<li>Receive its input from the output of a previous Actor and transfer it to the next Actor.</li>
<li>Receive an external flow argument and transfer it to the next Actor.</li>
</ul>
<strong>Concat</strong> Actor, concatenates an array of strings and joins them with the given delimiter. <strong><br /></strong><strong>JavaScript</strong> Actor, executes the JavaScript provided in the script parameter. The script returns the value of the last line. <a href="actors/01_javascript_actor.md">Click for more information about the JavaScript Actor.</a></td>
</tr>
<tr style="height: 247px;">
<td style="vertical-align: top; height: 247px; width: 295.969px;">
<p>Category Name:<strong>basic</strong></p>
<p>Description: Actors serve as the basic building blocks for creating a Broadway flow.</p>
</td>
<td style="vertical-align: top; height: 247px; width: 588.031px;">
<p><strong>ForLoop</strong> Actor, iterates over a range of numbers.</p>
<p><strong>Logger</strong> Actor, writes a message to the log file referencing entries from params and Actor inputs.</p>
<p><strong>InnerFlow</strong> Actor, executes a Broadway flow.</p>
<p><strong>LuFunction</strong> Actor, executes Studio function logic. Parameters for the function's execution are taken from input arguments or from the params input argument.</p>
<p><strong>Email</strong> Actor, sends an email using SMTP interface. Supports email body in HTML format and can send attachments.</p>
</td>
</tr>
<tr style="height: 82px;">
<td style="vertical-align: top; height: 82px; width: 295.969px;">
<p>Category Name: <strong>data</strong></p>
<p>Description: Various data manipulations, such as accumulate values into a map, build an array or sort the input collection.</p>
</td>
<td style="vertical-align: top; height: 82px; width: 588.031px;">
<p><strong>MapBuild</strong> Actor, accumulates key/value pairs into a map. Duplicate keys are handled according to the duplicateKeys mode field.</p>
</td>
</tr>
<tr style="height: 270px;">
<td style="vertical-align: top; height: 270px; width: 295.969px;">
<p>Category Name: <strong>date/time</strong></p>
<p>Description:Various Date and Time manipulation functions, such as DateAdd, DateFormat or Now.</p>
</td>
<td style="height: 270px; width: 588.031px;">
<p><strong>DateFormat</strong> Actor, formats a date into a string.</p>
<ul>
<li>Input values: Date, Output Format (following a predefined pattern) and Time Zone.</li>
<li>Initial format: yyyy-MM-dd HH:mm:ss.SSS.</li>
<li>Initial value of the time zone: UTC.</li>
<li>Output: a string.</li>
</ul>
<p>For example:</p>
<ul>
<li>To display a day of a year in the output, add <strong>D</strong> to the format.</li>
<li>To display a day of the week in the output, add<strong> E</strong> to the format.</li>
</ul>
</td>
</tr>
<tr style="height: 411px;">
<td style="vertical-align: top; height: 411px; width: 295.969px;">
<p>Category Name: <strong>db</strong></p>
<p>Description: Actions to be performed on a DB interface, such as creating a new table, loading data or executing a DB command.</p>
</td>
<td style="width: 588.031px; vertical-align: top; height: 411px;">
<p><strong>DbCommand</strong> Actor, performs database commands on a DB command interface. The interface used as input can be:</p>
<ul>
<li>A JDBC URL.</li>
<li>Reference to a predefined interface.</li>
<li>Others, like the schema, table name, fields definition, SQL dialect to use and append text appended to the CREATE command.</li>
</ul>
<p>The DbCommand can be used to create the WITH section where required.</p>
<p><strong>DbLoad</strong> Actor, loads data into a database using INSERT, UPDATE or UPSERT (if supported). The interface used as input can be the same as for <strong>DbCommand</strong> Actor.</p>
<ul>
<li>The Actor supports named parameters with the parameter name inside ${}. Values are taken from the Actor's input parameters.</li>
<li>In an INSERT command, the Actor also supports ordered parameters using the <strong>?</strong> as a replacement for the parameter.</li>
</ul>
<p><a href="actors/05_db_actors.md">Click for more information about DB Command Actors.</a></p>
</td>
</tr>
<tr style="height: 165px;">
<td style="vertical-align: top; height: 165px; width: 295.969px;">
<p>Category Name: <strong>fabric</strong></p>
<p>Description: Actors which execute the Fabric commands.</p>
</td>
<td style="width: 588.031px; vertical-align: top; height: 165px;">
<p><strong><span class="md-pair-s md-expand"><span class="md-plain">FabricGet</span></span></strong><span class="md-plain md-expand"> Actor performs the GET command on the current Fabric session.</span></p>
<p><span class="md-plain md-expand"><strong>FabricSet</strong> Actor sets a value on the Fabric session.</span></p>
<p><span class="md-plain md-expand"><strong>BatchWait</strong> Actor waits for a batch process to complete or throw an error if the batch does not complete successfully or does not complete within the predefined time.</span></p>
</td>
</tr>
<tr style="height: 78px;">
<td style="vertical-align: top; width: 295.969px; height: 78px;">
<p>Category Name: <strong>generators</strong></p>
<p>Description: Actors for generating various types of fake but valid values such as: SSN, email, credit card number.&nbsp;</p>
</td>
<td style="width: 588.031px; vertical-align: top; height: 78px;">
<p><strong><span class="md-pair-s md-expand"><span class="md-plain">RandomDistribution </span></span></strong><span class="md-pair-s md-expand"><span class="md-plain">Actor generates random values according to the given distribution. The supported distributions are: Normal, Uniform and Weighted.</span></span></p>
<p><span class="md-pair-s md-expand"><span class="md-plain"><strong>RandomRegexGenerator</strong> Actor generates random string matching the input regular expression.</span></span></p>
</td>
</tr>
<tr style="height: 133px;">
<td style="vertical-align: top; height: 133px; width: 295.969px;">
<p>Category Name: <strong>images</strong></p>
<p>Description: Image manipulation Actors that allow to perform various activities, such as:</p>
<ul>
<li>Load an image into a flow.</li>
<li>Write text on a given image.</li>
<li>Clone an image in memory.</li>
</ul>
</td>
<td style="width: 588.031px; vertical-align: top; height: 133px;">
<p><strong>ImageLoad</strong> Actor, receives a buffer or buffer stream, and loads the image into memory.</p>
<p><strong>ImageSave</strong> Actor, encodes the image to a byte buffer with the given format. This can then be transported or saved using DbLoad, FileWrite, Http or other Actors.</p>
</td>
</tr>
<tr style="height: 55px;">
<td style="vertical-align: top; height: 55px; width: 295.969px;">
<p>Category Name: <strong>jobs</strong></p>
<p>Description: Actors that create Fabric jobs.&nbsp;</p>
</td>
<td style="width: 588.031px; vertical-align: top; height: 55px;">
<p><strong>BroadwayJob</strong>, Actor that creates a Broadway job</p>
<p><strong>InterfaceListener</strong>, Actor that creates an Interface Listener job.</p>
</td>
</tr>
<tr style="height: 205px;">
<td style="vertical-align: top; height: 205px; width: 295.969px;">
<p>Category Name: <strong>logic</strong></p>
<p>Description: Logical operation on Actors<strong> A</strong> and <strong>B</strong> which returns a <strong>True</strong> or <strong>False</strong> boolean result.</p>
<p>Broadway converts the following types of input parameters to booleans:</p>
<ul>
<li>Null/no input, False.</li>
<li>Integer/double, True if not 0.</li>
<li>String, True if not empty/0/False.</li>
<li>Array/Map, True if not empty.</li>
</ul>
</td>
<td style="width: 588.031px; vertical-align: top; height: 205px;">
<p><strong>And</strong> Actor, returns&nbsp;True&nbsp;if and only&nbsp;if both A and B&nbsp;are&nbsp;True. Both A and B must be boolean values or a value that can be converted to a boolean.&nbsp;&nbsp;</p>
<p><strong>Elvis</strong> Actor, returns&nbsp;A&nbsp;if converted to boolean is&nbsp;True. Otherwise returns B.</p>
<p><strong>IfElse</strong> Actor, includes the&nbsp;test&nbsp;input to be validated as either True or False.&nbsp;If test is True, return&nbsp;A, else return&nbsp;B.&nbsp;</p>
</td>
</tr>
<tr style="height: 165px;">
<td style="vertical-align: top; height: 165px; width: 295.969px;">
<p>Category Name: <strong>masking</strong></p>
<p>Description: A group of Actors to mask sensitive information, such as SSN, credit card number, email. It also includes the Actors that can define a sequence.</p>
</td>
<td style="width: 588.031px; vertical-align: top; height: 165px;">
<p><strong>Masking</strong> is an Actor to generate a random/token data and keep it mapped to input original value. This Actor can wrap any data manufacturing Actor and add the hashing and caching capabilities on the top of it.</p>
<p>All other masking Actors are kept for backward compatibility, such as:</p>
<p><strong>MaskingCreditCard</strong> Actor,&nbsp;generates a fake but valid credit card number similar to the original card's type.</p>
<p><strong>MaskingSequence</strong> Actor, &nbsp;implements a unique sequence number.</p>
</td>
</tr>
<tr style="height: 169px;">
<td style="width: 295.969px; vertical-align: top; height: 169px;">
<p>Category Name: <strong>math</strong></p>
<p>Description: Various mathematical functions, such as MathMax, MathMin, Aggregate.</p>
</td>
<td style="height: 169px; width: 588.031px;">
<p><strong>Aggregate</strong> Actor, aggregates values.&nbsp;It receives a number or collection of numbers and calculates the Sum, Count, Average, Min and Max values of this collection. This Actor maintains its state across multiple loop iterations.&nbsp;&nbsp;</p>
<p><strong>MathDivMod</strong> Actor, returns the divisor and modulo factor of&nbsp;A&nbsp;and&nbsp;B.&nbsp;For example, if A=10 and B=3 then div=3 and mod=1.&nbsp;</p>
</td>
</tr>
<tr style="height: 132px;">
<td style="width: 295.969px; vertical-align: top; height: 132px;">
<p>Category Name: <strong>mtable</strong></p>
<p>Description: A group of Actors that enable looking up the MTable data either by keys or without them, or loading data to an MTable.</p>
</td>
<td style="width: 588.031px; vertical-align: top; height: 132px;">
<p><strong>MTableLookup</strong> Actor, fetches data from the mtable, creating indices as needed.</p>
<p><a href="actors/09_MTable_actors.md">Click for more information about MTable Actors.</a></p>
</td>
</tr>
<tr style="height: 100px;">
<td style="vertical-align: top; height: 100px; width: 295.969px;">
<p>Category Name: <strong>parsers</strong></p>
<p>Description: Various parsers which can be received as input stream in different types of formats, for example, CSV, JSON or XML.</p>
</td>
<td style="height: 100px; width: 588.031px;">
<p><strong>XmlParser</strong> Actor, receives an input stream represented via an iterable collection of blobs or strings. The parser runs until the end of the stream is detected. It returns a collection of parsed objects or a single object if Single is set to True.</p>
</td>
</tr>
<tr style="height: 133px;">
<td style="vertical-align: top; height: 133px; width: 295.969px;">
<p>Category Name: <strong>queue</strong></p>
<p>Description: Publish / subscribe messages to the queue.</p>
</td>
<td style="width: 588.031px; vertical-align: top; height: 133px;">
<p><strong>Publish</strong> Actor, publishes messages using a message broker.&nbsp;The inputs are:</p>
<ul>
<li>Broker interface to use.</li>
<li>Topic to publish to.</li>
<li>Message.&nbsp;</li>
</ul>
<p><a href="actors/04_queue_actors.md">Click for more information about Pub/Sub Actors.</a></p>
</td>
</tr>
<tr style="height: 284px;">
<td style="vertical-align: top; height: 284px; width: 295.969px;">
<p>Category Name: <strong>stats</strong></p>
<p>Description: Actors that gather the flow statistics.</p>
</td>
<td style="width: 588.031px; vertical-align: top; height: 284px;">
<p><strong>StatsWriter</strong> Actor, sets or increments statistics that can then be read by the StatsReader.</p>
<p><strong>StatsReader</strong> Actor, reads statistics written by other Actors such as StatsWriter, DbCommand or ErrorHandler. The Actor has two outputs:</p>
<ul>
<li>Flow, returns the flow level statistics map.</li>
<li>Global, returns the global/session level statistics map.</li>
</ul>
<p>For example, if <strong>StatsReader</strong> is added to the flow after the <strong>DbCommand</strong> Actor that executes an INSERT query, the <strong>StatsReader</strong> displays the number of executed and the number of affected records.</p>
</td>
</tr>
<tr style="height: 292px;">
<td style="height: 292px; width: 295.969px;">
<p>Category Name: <strong>streams</strong></p>
<p>Description: Various stream manipulation functions, such as Compress, FileRead or Http.</p>
</td>
<td style="height: 292px; width: 588.031px;">
<p><strong>FileRead</strong> Actor, reads data from a file given in an interface and path. The file is opened lazily when an Actor reads the output stream. Once the file has been fully read, it is closed. If the file is not fully read, it is closed at the end of the flow.</p>
<p><strong>Http/HttpJson</strong> Actors, send a request to a Web Server. Support streaming payload and results, sending and receiving header parameters. Using this Actor you can call a Web Service and parse its results.</p>
<p><strong>StringsToBytes</strong> Actor, reads an iterable of strings (or string representation) and converts them to byte arrays using the given character set (for example, UTF-8). The <strong>byteOrderMark</strong> input argument should be set to true if you need the BOM to be written at the beginning of the buffer, according to the given character set.</p>
</td>
</tr>
<tr style="height: 379px;">
<td style="vertical-align: top; height: 379px; width: 295.969px;">
<p>Category Name: <strong>strings</strong></p>
<p>Description: Various string manipulation functions, such as Concat, Split or Trim.</p>
<p>Graphit and JsonStringify Actors are also included in this category.</p>
</td>
<td style="height: 379px; width: 588.031px;">
<p><strong>Regex</strong> Actor, finds sub-strings in an input string using a regular expression. The Actor tries to find all matches of the pattern within the input string and return them. When using matching groups, the result is the content of the matching group instead of the full match. For example, in the ABCDEF string, the C.E pattern returns [CDE], whereas C(.)E returns [D].</p>
<p><strong>Graphit</strong> Actor, executes Graphit logic for data serialization. Parameters for the Graphit execution are taken from input arguments or from the params input argument.</p>
<p><a href="/articles/15_web_services_and_graphit/17_Graphit/01_graphit_overview.md">Click for more information about Graphit.</a></p>
</td>
</tr>
<tr style="height: 215px;">
<td style="vertical-align: top; height: 215px; width: 295.969px;">
<p>Category Name: <strong>system</strong></p>
<p>Description: System processes and commands to be performed in the file system.</p>
</td>
<td style="height: 215px; width: 588.031px;">
<p><strong>cp</strong> Actor, copies a file. The interface used as input can be:</p>
<ul>
<li>JDBC URL.</li>
<li>Reference to a predefined interface.</li>
<li>Path of the sourcefile (from).</li>
<li>Destination (to).</li>
</ul>
<p>The output is a number of affected files.</p>
<p><strong>Exec</strong> Actor, executes a system process and waits for it to be completed.</p>
</td>
</tr>
<tr style="height: 229px;">
<td style="vertical-align: top; height: 229px; width: 295.969px;">
<p>Category Name: <strong>testing</strong></p>
<p>Description: Actors that check a condition and throw an assersion exception if the condition is not met.</p>
</td>
<td style="height: 229px; width: 588.031px;">
<p><strong>assertNotNull</strong> Actor, throws an assertion error if supplied object is null.</p>
<p><strong>assertContains</strong> Actor, throws an assertion error if substring cannot be found in string.</p>
<p><strong>assertEquals, </strong>throws an assertion exceptions if actual does not equal expected.</p>
</td>
</tr>
</tbody>
</table>













[![Previous](/articles/images/Previous.png)](03_broadway_actor_window.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](05_data_types.md)
