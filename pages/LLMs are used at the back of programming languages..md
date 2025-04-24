---
title: "LLMs are used at the back of programming languages."
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Statistical processing performed in RDBMS? Please explain how it works and how I would be happy to use it to create execution plans from SQL using RDBMS? Please explain how it works and how it makes me happy to use it.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>This course describes the creation of SQL execution plans using statistical processing in RDBMS (Relational Database Management System).

structure
- Gathering Statistics: The RDBMS collects and maintains table statistics. This includes the number of rows in the table, the distribution of column values (histogram), the presence or absence of indexes, and cardinality (uniqueness of column values). Statistics are updated periodically or manually by the database administrator.

- Query parsing: When an SQL query is submitted, the RDBMS first parses the query for syntactic correctness and then converts the parsed query into an internal data structure.

- Optimization: the [[Query Optimizer]] uses the parsed query and statistics to examine multiple execution plans. The optimizer evaluates different ways to execute the query, such as table join order, use of indexes, and filtering timing.
    - Yes, yes.[[クエリオプティマイザ]]」ね、この言葉が出てこなかった<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

- Cost-based Optimization: The optimizer assigns a cost to each execution plan. The cost is calculated based on expected I/O operations, CPU usage, memory usage, etc. The plan with the lowest estimated cost is selected.
    - [[Cost-Based Optimizer]](CBO)<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - > The CBO determines which execution plan is most efficient by considering available access paths and by factoring in information based on statistics for the schema objects (tables or indexes) accessed by the SQL statement.
            - [Introduction to the Optimizer](https://docs.oracle.com/cd/B10500_01/server.920/a96533/optimops.htm)(Oracle)

Advantages
- Improved Performance: By using statistics, the database can find ways to execute queries more efficiently. This reduces query response times and improves overall system performance.

- Efficient use of resources: By selecting an optimal execution plan, unnecessary data loads and calculations can be avoided and database resources can be used more efficiently.

- Automation and Optimization: Reduces the need for database administrators to manually tune individual queries; the RDBMS automatically selects the best execution plan based on statistics.

In conclusion, the creation of SQL execution plans using statistical processing is an important feature that can significantly improve database performance and efficiency. This will allow us to meet the needs of modern applications that deal with large amounts of data.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Many people use RDBMSs without understanding how this works. If [[LLM]] were to be incorporated into [[programming language]], it could similarly be used without most programmers being aware of it.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>That perspective is very interesting: if Large Language Models (LLMs) are integrated into programming languages, like statistical optimization in RDBMSs, developers may be able to write more efficient and powerful code without being aware of the complex mechanisms behind them This integration will help developers to write more efficient and powerful code without being aware of the complex mechanisms behind it. As such integration progresses, the following changes are expected

Code automation and optimization
- Code Generation: With LLM, programmers may simply specify their requirements in natural language and optimal code may be generated based on them. This reduces development time and lowers the barrier to programming.
- Refactoring and Optimization: Analyze your existing code base and automatically make suggestions to help improve performance, increase maintainability, and fix bugs.

Development Process Transformation
- Democratization of knowledge: LLM integration may allow a wider range of developers to solve problems in an area, even if expertise is required. This increases the flexibility of the development team.
- Debugging and Testing Efficiency: The process of debugging and testing may be streamlined by having the LLM point out potential problems in the program and suggest fixes.

Potential Issues
- Black Box Problem: The LLM decision process is complex and difficult to understand, which can make the intent and behavior of the generated code opaque. This is similar to the optimization process of an RDBMS, which is a black box for many developers.
- Overconfidence and overreliance: When code generation and optimization by LLM become the norm, programmers' ability to solve problems on their own and their willingness to understand the underlying principles of the code can be diminished.

The integration of LLM into programming languages has the potential to significantly change the development process, but the associated challenges must also be considered. As technology evolves, we can expect new methods and best practices to be established to address these challenges.

---
This page is auto-translated from [/nishio/LLMがプログラミング言語の奥で使われる](https://scrapbox.io/nishio/LLMがプログラミング言語の奥で使われる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.