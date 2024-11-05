## Markdown

* **Headlines**: Use pound signs (#) for different levels of headlines, or use equal signs and hyphens for level one and two headlines, respectively.

        # Headline level 1

        ## Headline level 2
        ### Headline level 3
        #### Headline level 4
        ##### Headline level 5
        ###### Headline level 6

* **Text Formatting**: Use asterisks or underscores for bold and italic text. Double tildes (~~) create strikethrough text.

        **bold**
        __bold__

        *italics*
        _italics*

        ~~strike through~~

        > Quotation

        --- Horizontal rule
        *** Asterisks
        ___ Underscores

* **Lists**: Create lists with hyphens, asterisks, or plus signs. Use numbers for ordered lists. 

        - Hyphens
        * Asterisks
        + Plus sign

        1. First ordered list item
            * unordered sub-list
        1. Numbers don't really matter

* **Links**: Links are created with brackets for the link name and parentheses for the URL.

        https://www.linkedin.com
        [Website](https://www.linkedin.com "Linkedin)

        [Linkedin]
        [Learning][1]

        [linkedin]: https://www.linkedin.com
        [1]: https://www.linkedin.com/learning

* **Code and Images**: Use tick marks for inline code and triple 'tick' marks for code blocks. Add an exclamation point before brackets to insert images.

        ![Image](https://pixelprowess.com/i/stragazers/tomolor.png)


* Piece of code:

        ''' 
        x = 15
        '''

* **Footnotes and Tables**: GitHub Flavored Markdown (GFM) includes support for footnotes and tables, allowing for more structured and referenced content.

        This is a footnote[^1]. Another footnote[^2]

        [^1]: My reference
        [^2]: Another footnote


        | Left | Center | Right |
        | ---- | :----: | ----: |
        | One  | Two    | $1.00 |
        | Three| Four   | $120.00|
        | Five | Six    | $.99  |

* **Task Lists and Collapsible Sections**: You can create task lists with checkable boxes and collapsible sections using HTML tags for better content organization.

        - [x] First
           - [x] One
           - [ ] Two
        - [ ] Second


        <details>
        <summary>collapsed</summary>

        # Header

        This is a copy of the collapsed text.
        </details>

* **Enhanced Formatting**: GFM supports additional formatting options like drag-and-drop for various file types, hashtags for referencing issues, and @mentions for tagging people in pull requests and issues.

* **Mermaid Graphs and Emojis**: GFM allows for the inclusion of mermaid graphs for flowcharts and other diagrams, as well as emojis for enhanced communication.

        '''mermaid
        graph TD:
            A --> B;
            A --> C;
        '''

* Alert Syntax: Only work in pull request

        > [!NOTE]
        > [!IMPORTANT]
        > [!WARNING]