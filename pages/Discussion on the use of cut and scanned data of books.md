---
title: "Discussion on the use of cut and scanned data of books"
---

[[NISHIO Hirokazu's Assistant]] was created and I tried using it.
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>In summary, the key points of the discussion regarding the use of cut and scanned book data are as follows
1. it is important not only to collect scanned data, but also how to connect it to intellectual production. For example, a method of utilization such as extracting and comparing related topics from multiple books has been proposed.
2. specific implementation steps to efficiently extract useful information from the data using techniques such as fractal summarization and cross-book analysis tools are being considered.
3. the advantages (e.g., structuring information, collaborative editing) and disadvantages (e.g., difficulty in hierarchical classification) of using Scrapbox to manage data are discussed. The possibility of a public project using public domain literature to avoid copyright issues is also noted.
4. specific methods are proposed to handle data more effectively on Scrapbox, such as generating fractal summaries that match the chapter and section structure of books, and mapping summaries to detailed information.

These discussions indicate that it is important not only to collect scanned data, but also to structure and summarize the information and develop analysis tools to utilize it for intellectual production. In addition, ways are being explored to take advantage of existing platforms such as Scrapbox, while taking copyright issues into consideration.

# Conversation
[raw log](https://chat.openai.com/share/fe2d3370-86b5-49de-96d0-22b8b2271901)

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What was the discussion about the use of book cutting and scanning data like?

<img src='https://scrapbox.io/api/pages/nishio-en/nihia/icon' alt='nihia.icon' height="19.5"/>According to Yasukazu Nishio's discussion on the use of cut and scanned book data, it is important not only to scan the data, but also how to connect the data to intellectual production. For example, there is a discussion on how to utilize scanned book data, and the method of extracting and comparing related topics from different books through the process of "deconstructing and reconstructing" is considered effective. This allows readers to gain deeper knowledge and understanding through books (from [[AI Considerations 2024-04-27]]).

In addition, when leveraging scanned data, ways are being explored to effectively extract useful information from the data using specific techniques, such as fractal summarization and the development of cross-book analysis tools (from [[AI Considerations 2024-05-01]]).

These considerations indicate that there is a need to do more than simply digitize cut and scanned data from books, but to construct new knowledge from it.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Find the page you are considering and let me know how exactly I should implement it.

<img src='https://scrapbox.io/api/pages/nishio-en/nihia/icon' alt='nihia.icon' height="19.5"/>A discussion of specific applications of cut and scanned book data is described on the "AI Considerations 2024-05-01" page by Yasukazu Nishio. The page suggests the following implementation steps

- Apply fractal summarization: plan how you will apply fractal summarization to existing scanned book data, clearly defining which techniques you will use and in what format you will obtain your output.
- Organizing and Expanding Scrapbox: We will look at ways to organize pages within Scrapbox and integrate new summarization technologies. In particular, we will focus on enhancements to improve work efficiency, such as the ability to automatically insert a summary for every 50 pages.
- Develop a cross-book analysis tool: develop a tool or method for extracting and comparing content related to the same topic from different books. This tool is expected to facilitate thematic comparison and analysis and provide deeper insights.
- Test prototypes and collect feedback: actually test the prototypes of the summary and analysis tools you develop, collect feedback from yourself and other users, and make improvements based on that feedback.
- Documentation and Sharing: Document how the tool is used and the findings obtained, and share them with other researchers and users as needed. This facilitates knowledge sharing and suggestions for tool improvements within the community.

These steps will help you develop a concrete plan for utilizing book cutting and scanning data and proceed with implementation.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I think I had organized the keywords fromPDF in terms of the amount of information from PDF, but I'll have to search and put it all together.

<img src='https://scrapbox.io/api/pages/nishio-en/nihia/icon' alt='nihia.icon' height="19.5"/>The page titled "[[fromPDF]]" by Yasukazu Nishio describes the process of transferring information from PDF to Scrapbox. The focus here is on how to make information retrieved from PDF available in Scrapbox. The following steps are possible concrete implementation methods:

- Text Extraction from PDF: Extract text information from PDF using a tool like pdf2txt. This provides text-based data and facilitates subsequent processing.
- Import to Scrapbox: Import the extracted text data into Scrapbox. This step may require some processing to organize the information and adapt it to the Scrapbox format.
- Organize and expand data: further organize data within Scrapbox and create richer content by linking related information and additional metadata.

These steps will allow the information from the PDFs to be efficiently reused within Scrapbox, creating a foundation for knowledge sharing and organization. This process is intended to improve accessibility of information and facilitate knowledge reuse.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>There is some question as to whether it is appropriate to have data in Scrapbox format.

<img src='https://scrapbox.io/api/pages/nishio-en/nihia/icon' alt='nihia.icon' height="19.5"/>There are several considerations by Yasukazu Nishio regarding the advantages and disadvantages of using Scrapbox to hold data. The main points are summarized below.

advantage
- Structuring Information: Scrapbox allows you to record information in any format while easily structuring it with links and tags. This makes it easy to see connections between related information and facilitates navigation.
- Collaborative Editing: Scrapbox supports simultaneous editing by multiple people, facilitating team collaboration. This is very useful for knowledge sharing in projects or research groups.
- Automatic saving and import/export: Data is automatically saved and can be exported or imported in JSON format. This facilitates data backup and migration to other platforms.

drawback
- Difficulty with hierarchical categorization: Scrapbox is not good at categorizing pages in a hierarchical manner. This may make it more difficult for some users to use compared to traditional wikis or databases.
- Difficulty in machine handling of data: Scrapbox allows free editing in natural language, but once data is edited in wiki format, it may be difficult to convert it back to a form that can be easily handled mechanically (e.g., CSV format).

Given these advantages and disadvantages, it is important to carefully consider whether the use of Scrapbox is appropriate for your project and personal needs. Depending on how you use and manage your data, Scrapbox's flexibility and functionality may be a major benefit, while certain limitations may be problematic.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The second advantage, collaborative editing, is becoming difficult to achieve because of book copyrights. However, it is possible to reverse the situation and create a public Scrapbox project using books and classics that are not under copyright. As for the disadvantages, it is difficult to create a hierarchical structure by default. This can be solved by defining a microformat. Flexible modification is an advantage to facilitate trial and error.

<img src='https://scrapbox.io/api/pages/nishio-en/nihia/icon' alt='nihia.icon' height="19.5"/>You are right, copyright issues are a major challenge when using Scrapbox, but projects using classics and public domain literature whose copyrights have expired are very interesting as an effective solution. By using such literature, we can take full advantage of the collaborative editing features and facilitate the sharing of scholarly discussions and educational content.

Difficulties in handling hierarchical structures in Scrapbox may also be partially resolved by designing appropriate microformats. Microformats allow for consistent structure within a document, while still taking advantage of Scrapbox's flexibility for management.

These approaches are effective in maximizing the advantages of Scrapbox while mitigating its disadvantages. Through trial and error, a more efficient and user-friendly environment for intellectual production can be created.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The hierarchical structure includes the inclusion of chapters and sections in the book itself and the hierarchical structure of the fractal summary. The current fractal summary is engraved without considering the structure, but there is an option to adapt this to the structure of the book. Next, there is the mapping between the terminal information and its summary.

<img src='https://scrapbox.io/api/pages/nishio-en/nihia/icon' alt='nihia.icon' height="19.5"/>The approach of constructing a fractal summary that reflects the structure of the book is very effective in helping readers understand the content. By clarifying the inclusion of chapters and sections, it becomes easier for the reader to grasp the flow of the entire document and its important points. The following steps can be considered as concrete implementation methods:

- Chapter and Section Analysis: Develop algorithms to automatically identify chapters and sections of a book, structuring the bulk of the document. This might include parsing table of contents information or identifying heading patterns within the text.
- Apply fractal summarization: Apply fractal summarization to each chapter or section to summarize the content in a hierarchical manner. This allows the main points of each part to be conveyed concisely and aids in overall comprehension.
- Corresponding with Terminal Information: Ensure traceability of information by linking terminal information, such as specific data, citations, and examples, to chapter and section summaries. This facilitates readers' access to detailed information and promotes in-depth understanding.
- Visualization and Navigation: Provide a visual representation of the book's structure so that users can easily navigate through it. For example, it may provide an interactive table of contents and links connecting chapters and sections.

Through these methods, book content can be more effectively managed and deployed on platforms such as Scrapbox. This will also improve the quality of intellectual production and create greater value in education and research.

---
This page is auto-translated from [/nishio/書籍の裁断スキャンデータの活用に関する議論](https://scrapbox.io/nishio/書籍の裁断スキャンデータの活用に関する議論) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.