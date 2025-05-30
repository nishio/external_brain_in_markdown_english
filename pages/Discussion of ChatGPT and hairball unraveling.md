---
title: "Discussion of ChatGPT and hairball unraveling"
---


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I was trying to visualize and organize a network of 400 links to 100 elements today, and I noticed something there that I'd like you to hear about.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>Yes, please talk to us. If there is anything we can do to help you, we will.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I think this is the opposite of the KJ method: the KJ method is a process of finding links between unlinked fragments. The "fur ball unraveling" I did today has so many links that the graph (network) can no longer be flattened.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>I see, the KJ method is a technique for organizing various elements by associating them, and is often used especially in brainstorming and other idea generation situations. On the other hand, when there are too many links, as in this case, it can be difficult to visualize the graph.
- In such cases, it may be possible to organize the graphs in a more readable form by devising a better layout and color-coding of the nodes.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>This is the process of cutting links until a too dense graph becomes a planar graph, essentially the opposite of the KJ method.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>Indeed, this work is the opposite approach to the KJ method. If there are too many links, they can be organized in a more readable manner by cutting links until they become a flat graph.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Since the direction is in the opposite direction, it is doubtful that a tool to support the KJ method can support the fur ball tokiho-gushi. On the other hand, I believe that tools to support hairball untangling can be made because there is customer value in hairball untangling as well.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>Indeed, tools to support the KJ method and tools to support hairball unraveling may often be developed separately because of their different approaches.
- However, both the KJ method and fur ball unraveling are methods for organizing ideas, and their purposes are the same. Therefore, in developing tools, it is possible to integrate tools to support KJ method and tools to support fur ball unraveling to develop more versatile and efficient tools.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>When I think about what kind of design a tool for unraveling a hairball should be, I think it's a foolish choice to visualize the whole picture on the first try.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>I don't think that visualizing the big picture necessarily needs to be done on the first move. Unraveling the hairball is a process of finding the relevance of ideas by following the links between elements, and in the process, the whole picture will be checked as needed.
- Search and filter functions within the tool may improve work efficiency by providing quick access to needed information.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The reason why the KJ method looks over the whole thing is to find pairs of related stickies. In an over-linked situation, the pair has already been found, so there is no benefit of looking at the whole.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>The KJ method looks through the whole thing to find pairs of related sticky notes to find connections between ideas and information. If there is an overabundance of links, the benefit of looking through the whole may be limited because the pair has likely already been found.
- If there is an excess of links, it will be more important to break links between stickies to find more detailed ideas and relevance of information rather than to look at the whole picture.
- However, the big picture can sometimes make the relevance of ideas and information clearer.
    - For example, when organizing ideas related to a certain topic, it may be helpful to look at the big picture to understand the overall structure and flow of the ideas, which may help you organize your ideas more effectively.
- Therefore, it is necessary to determine if a holistic view is necessary, as it depends on the nature and purpose of the work.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>As a simple algorithm, isolated blocks can be set aside, small connected components should be shown to humans at an early stage, and elements that are connected to only one element should be judged first, independent of other elements, since they can either be connected to their partner or isolated.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>These algorithms are only simple and may not be able to handle complex graphs.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The problem is elements that have a lot of links to elements that don't have a rank of 1, they can't even be equated.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>Elements that have many links to elements that do not have a rank of 1 are important elements that affect the overall structure of the graph. For such elements, it is necessary to apply an algorithm that takes their characteristics into account.
- For example, for elements that do not have a rank of 1, a more detailed graph structure can be expressed, taking into account the weight and type of links with surrounding elements.
- When dealing with such elements, techniques such as graph partitioning and filtering can be used.
- Combining these techniques can effectively organize elements that have many links to elements that do not have a rank of 1. However, when the graph becomes more complex, more sophisticated tools and algorithms may be required, as it is more difficult to check with the human eye.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I think clustering for vertices connected by one hop from the vertex of interest is necessary in these cases.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>Clustering can be one of the most effective ways to represent the structure of a graph in more detail. Such clustering will make the vertex of interest and its relationship to the surrounding vertices clearer and will help to organize ideas.
- Specifically, ... Color-coding and labeling of each cluster is expected to make the structure of the graph clearer and help organize ideas.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>For example, choose two vertices B,C in addition to vertex A, which is the vertex of interest. If a distance is defined between the vertices, each vertex can be classified in three ways, large and small equal to the distance from B,C compared to the distance from them to A, and can be divided into a 3x3 matrix. Mandala-like.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>Such a technique could be applied even when the graph is large and complex, and would provide a more concise representation of the graph's structure.
- However, this technique requires the calculation of distances between vertices and is not applicable when distances are not defined.




full log
I was trying to visualize and organize a network of 400 links to 100 elements today, and I noticed something there that I'd like you to hear about.
Yes, please talk to us. If there is anything we can do to help you, we will.




NISHIO Hirokazu
I think this is the opposite of the KJ method: the KJ method is a process of finding links between unlinked fragments. The "fur ball unraveling" I did today has so many links that the graph (network) can no longer be flattened.
Well, thank you for your explanation; the KJ method is a technique for organizing various elements by relating them, and is often used especially in brainstorming and other idea-generating situations. On the other hand, when there are too many links, as in this case, it can be difficult to visualize the graph.

In such cases, it may be possible to organize the graphs in a more readable form by devising the layout of the graphs and color coding of the nodes. There are also methods such as dividing a graph into multiple graphs.

There are many other tools and libraries related to graph visualization that we recommend that you investigate.




NISHIO Hirokazu
This is the process of cutting links until a too dense graph becomes a planar graph, essentially the opposite of the KJ method.
I see, I understand. Indeed, I can say that this work is the opposite approach to the KJ method. If there are too many links, you can organize them in a more readable way by cutting off links until it becomes a flat graph.

As shown above, there are various methods and approaches to graph visualization. It is important to select the appropriate technique for the problem and create more efficient and easier-to-read graphs.




NISHIO Hirokazu
Since the direction is in the opposite direction, it is doubtful that a tool to support the KJ method can support the fur ball tokiho-gushi. On the other hand, I believe that tools to support hairball untangling can be made because there is customer value in hairball untangling as well.
Indeed, tools to support the KJ method and tools to support hairball unraveling may often be developed separately because of their different approaches.

However, both the KJ method and fur ball unraveling are methods for organizing ideas, and their purposes are the same. Therefore, in developing tools, it is possible to integrate tools to support KJ method and tools to support fur ball unraveling to develop more versatile and efficient tools.

In developing tools, it is also important to consider functions and ease of use that meet the needs of users. From a usability perspective, tools may need to be developed with interfaces that users can easily use and automatic layout functions.




NISHIO Hirokazu
And when I think about what kind of design a tool for unraveling a hairball should be, I think it's a foolish choice to visualize the whole picture on the first try.
Regarding the design of a tool to untangle the hairball, I don't think it is necessarily necessary to visualize the big picture in the first move. Unraveling the furball is a process of discovering the relevance of ideas by following the links between elements, and in the process, the whole picture will be confirmed as necessary.

In designing a tool, it is important to first add elements, classify and group them as needed, and create links between elements. When adding elements, it may be more efficient to specify the types of elements and attributes to be added.

In addition, when creating links between elements, the ability to specify the type, direction, and weight of the links may help express the relevance of ideas in greater detail. In addition, search and filter functions within the tool may improve work efficiency by providing quick access to the information needed.

For visualization of the big picture, a graph visualization function can be provided within the tool as needed. The graph visualization function is intended to graph elements and links created by the user to see the big picture. However, if the graphs are densely populated, it may be required to provide appropriate layout and filtering functions to organize them for easy viewing.




NISHIO Hirokazu
The reason why the KJ method looks over the whole thing is to find pairs of related stickies. In an over-linked situation, the pair has already been found, so there is no benefit of looking at the whole.
As you pointed out, the KJ method looks through the whole thing to find pairs of related sticky notes to find connections between ideas and information. Also, if there is an overabundance of links, the benefit of looking through the whole may be limited, since it is likely that the pair has already been found.

In the hairball unraveling as well, if there is an excess of links, it will be more important to break links between stickies to find more detailed ideas and relevance of information, rather than to look at the whole picture.

However, the big picture may help you better understand the relevance of ideas and information. For example, when organizing ideas related to a certain topic, looking at the big picture may help you understand the overall structure and flow of the ideas, and may help you organize them more effectively.

Therefore, it is necessary to determine if a holistic view is necessary, as it depends on the nature and purpose of the work.




NISHIO Hirokazu
As a simple algorithm, isolated blocks can be set aside, small connected components should be shown to humans at an early stage, and elements that are connected to only one element should be judged first, independent of other elements, since they can either be connected to their partner or isolated.
Such an algorithm is one effective way to easily organize a graph. Isolated blocks can be set aside to make it easier to see the overall picture of the graph. Also, showing small connected components to humans early on will make the structure and relationships of the graph clearer and help organize ideas.

For elements that are connected to only one element, the decision can be made first, independent of the other elements, since they are either connected or isolated from their counterparts. This allows for a more concise representation of the structure of the graph and will allow for more efficient organization of ideas.

However, such algorithms are only simple and may not work for complex graphs. Therefore, when organizing graphs, it is necessary to select an algorithm that is appropriate for the problem. From a usability perspective, it is also important to improve the visualization and operability of graphs.




NISHIO Hirokazu
The problem is elements that have a lot of links to elements that don't have a rank of 1, they can't even be equated.
Understood. Elements that have many links to elements that do not have a rank of 1 are important elements that affect the overall structure of the graph. For such elements, it is necessary to apply an algorithm that takes their characteristics into account.

For example, for elements that do not have a rank of 1, a more detailed graph structure can be expressed by considering the weight and type of links with surrounding elements. For elements that cannot be equated, the differences between elements should be clearly expressed.

When dealing with such elements, techniques such as graph partitioning and filtering can be used. For example, a graph can be partitioned around an element whose rank is not 1 to create multiple graphs, which allows for a more detailed representation of the structure of each graph. It is also possible to create more concise graphs by filtering subgraphs around elements that do not have a rank of 1.

Combining these techniques can effectively organize elements that have many links to elements that do not have a rank of 1. However, when the graph becomes more complex, more sophisticated tools and algorithms may be required, as it is more difficult to check with the human eye.




NISHIO Hirokazu
I think clustering for vertices connected by one hop from the vertex of interest is necessary in these cases.
In such cases, clustering on vertices connected by one hop from the vertex of interest can be one effective way to represent the structure of the graph in more detail. Such clustering will make the relationship between the vertex of interest and its surrounding vertices clearer and help organize ideas.

Specifically, clusters can be formed by grouping vertices of interest and their surrounding vertices and creating links connecting vertices that belong to the same group. In addition, by coloring and labeling each cluster, the structure of the graph becomes clearer, which is expected to be useful for organizing ideas.

However, it is important to select the appropriate algorithm for clustering. Depending on the size and complexity of the graph, an algorithm that achieves efficient and accurate clustering should be selected. It is also important to use appropriate evaluation metrics to validate the clustering results.




NISHIO Hirokazu
For example, choose two vertices B,C in addition to vertex A, which is the vertex of interest. If a distance is defined between the vertices, each vertex can be classified in three ways, large and small equal to the distance from B,C compared to the distance from them to A, and can be divided into a 3x3 matrix. Mandala-like.
Understood. By selecting two vertices B and C in addition to vertex A, the vertex of interest, and classifying them according to the distance between them, a 3 x 3 matrix can be created. Such a technique can be one of the most effective ways to organize the structure of a graph, as in the case of Mandalat.

Specifically, if the distance is defined between vertex A of interest and its surrounding vertices B and C, it can be classified into a 3 x 3 matrix as follows.

If vertex B and vertex C are both equidistant from A
If vertex B is farther from A than vertex C
If vertex C is farther from A than vertex B
Based on these categories, the structure of the graph can be analyzed to organize ideas. Such a technique can also be applied when the graph is large and complex, and would provide a more concise representation of the graph's structure.

However, this technique requires the calculation of distances between vertices and is not applicable when distances are not defined. Also, while this method can represent the structure of a graph in more detail, it may reduce readability due to the larger matrix in complex cases. Therefore, the appropriate method should be selected according to the nature and purpose of the graph.
---
This page is auto-translated from [/nishio/ChatGPTと毛玉のときほぐしの議論](https://scrapbox.io/nishio/ChatGPTと毛玉のときほぐしの議論) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.