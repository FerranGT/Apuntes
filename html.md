#HTML5: HyperText Markup Language version 5

Lenguaje de marcado para la elaboración de páginas web, define una estructura básica y un código (HTML) para la definición de contenido de una página. HTML5 especifica dos variantes de sintaxis para HTML: una «clásica», HTML (text/html), conocida como HTML5, y una variante XHTML conocida como sintaxis XHTML5 que deberá servirse con sintaxis XML (application/xhtml+xml).

#The Three Layers of Web Development

**Structure or content layer**
The  structure or content layer of a web page is the underlying HTML code of that page. Like a house's frame creates a strong foundation upon which the rest of the house is built, so does a solid foundation of HTML create a platform upon which a website can be created. HTML structure can consist of text or images and it includes the hyperlinks that visitors will use to navigate around that web site. 

1. **Style or presentation layer**

    - The style or presentation layer dictates how a structured HTML document will look to a site's visitors. 
    - This layer is defined by CSS (Cascading Style Sheets). These files contain styles that indicate how the document should be displayed in a web browser. 
    - On today's Web, the style layer can also include Media Queries that can change a site's display based on different screen sizes and devices.


**Behavior**
The behavior layer is the layer of a Web page that can respond to different user actions or make changes to a page based on a set of conditions. For most Web pages, the behavior level would be the JavaScript interactions on the page. 



Web documents are ordinary text files (ASCII) that:
Contain tags, which are used to "mark-up" text.
Are named with a ".html" extension.
Are placed in a "www-data" directory within AFS public space.

Tags are just text with a special format:
Each individual tag begins with the character "<"
Each individual tag ends with the character ">"
A tag may contain keywords, the first of which is the name of the tag. 
e.g., <XYZ KEY=VALUE> would be called an "XYZ-tag."
Most tags come in pairs: an opening tag, and a closing tag, which has the same name preceded by a "/".
The text between the two tags is affected by them.

The tags we have discussed are:
<HTML> First tag in a document (unpaired).
<HEAD> Marks the head section (paired).
<BODY> Marks the body section (paired).
<TITLE> Title (goes in head section) (paired).
<P> Paragraph break (unpaired).
<BR> Line break (unpaired).
<HR> Horizontal rule (line) (unpaired).
<PRE> Preformatted text (paired).
<EM> Emphasis (usually italics) (paired).
<STRONG> Stronger emphasis (paired).
<B> Bold (text attribute) (paired).
<I> Italics (text attribute) (paired).
<H1> Level 1 (e.g., document) heading (paired).
<H2> Level 2 (e.g., part) heading (paired).
<H3> Level 3 (e.g., chapter) heading (paired).
<H4> Level 4 (e.g., section) heading (paired).
<H5> Level 5 (e.g., subsection) heading (paired).
<H6> Level 6 (e.g., paragraph) heading (paired).
<del> Texto tachado
<nav> represents a section of a page that links to other pages or to parts within the page: a section with navigation links
<header> represents a group of introductory or navigational aids
<aside> epresents a section of a page that consists of content that is tangentially related to the content around the aside element, and which could be considered separate from that content. Such sections are often represented as sidebars in printed typography.
<article>  represents a complete, or self-contained, composition in a document, page, application, or site. This could be a magazine, newspaper, technical or scholarly article, an essay or report, a blog or other social media post.
<hgroup> used for grouping series of <h#>
<figure> used to enclose some flow content, optionally with a caption, that is self-contained and is typically referenced as a single unit from the main flow of the document.
<section> represents a generic document section and a section is a thematic grouping of content
<ol> an ordered list of articles, every element un list goes with <li>
<ul> an unordered list of articles, every element un list goes with <li>
<footer> pie de pagina
<abbr> element represents an abbreviation or acronym
<a> element has an href attribute, then it represents a hyperlink (a hypertext anchor) labeled by its contents. If the <a> element has no href attribute, then the element represents a placeholder for where a link might otherwise have been placed, if it had been relevant, consisting of just the element’s contents.
<span> tag is used to group inline-elements in a document.tag provides no visual change by itself.tag provides a way to add a hook to a part of a text or a part of a document.
<nav> tag defines a set of navigation links.



#Building Forms

<form action="/login" method="post">
  ...
</form>

The **action** attribute contains the URL to which information included within the form will be sent for processing by the server. The **method** attribute is the HTTP method browsers should use to submit the form data. 


#Text Fields

One of the primary elements used to obtain text from users is the <input> element. The <input> element uses the type attribute to define what type of information is to be captured within the control. The most popular type attribute value is text, which denotes a single line of text input.

Along with setting a type attribute, it is best practice to give an <input> element a name attribute as well. The name attribute value is used as the name of the control and is submitted along with the input data to the server.


<input type="text" name="username">

<input type="date" name="birthday">
<input type="time" name="game-time">
<input type="email" name="email-address">
<input type="url" name="website">
<input type="number" name="cost">
<input type="tel" name="phone-number">


#Textarea

Another element that’s used to capture text-based data is the <textarea> element. The <textarea> element differs from the <input> element in that it can accept larger passages of text spanning multiple lines. The <textarea> element also has start and end tags that can wrap plain text. Because the <textarea> element only accepts one type of value, the type attribute doesn’t apply here, but the name attribute is still used.


<textarea name="comment">Add your comment here</textarea>


#Multiple Choice Inputs & Menus

**Radio Buttons**

Radio buttons are an easy way to allow users to make a quick choice from a small list of options. Radio buttons permit users to select one option only, as opposed to multiple options.

To create a radio button, the <input> element is used with a type attribute value of radio. Each radio button element should have the same name attribute value so that all of the buttons within a group correspond to one another.

With text-based inputs, the value of an input is determined by what a user types in; with radio buttons a user is making a multiple choice selection. Thus, we have to define the input value. Using the value attribute, we can set a specific value for each <input> element.

Additionally, to preselect a radio button for users we can use the Boolean attribute checked.


<input type="radio" name="day" value="Friday" checked> Friday
<input type="radio" name="day" value="Saturday"> Saturday
<input type="radio" name="day" value="Sunday"> Sunday

**Check Boxes**

Check boxes are very similar to radio buttons. They use the same attributes and patterns, with the exception of checkbox as their type attribute value. The difference between the two is that check boxes allow users to select multiple values and tie them all to one control name, while radio buttons limit users to one value.


<input type="checkbox" name="day" value="Friday" checked> Friday
<input type="checkbox" name="day" value="Saturday"> Saturday
<input type="checkbox" name="day" value="Sunday"> Sunday


**Drop-Down Lists**

Drop-down lists are a perfect way to provide users with a long list of options in a practi- cal manner. A long column of radio buttons next to a list of different options is not only visually unappealing, it’s daunting and difficult for users to comprehend, especially those on a mobile device. Drop-down lists, on the other hand, provide the perfect format for a long list of choices.

To create a drop-down list we’ll use the <select> and <option> elements. The <select> element wraps all of the menu options, and each menu option is marked up using the <option> element.

The name attribute resides on the <select> element, and the value attribute resides on the <option> elements that are nested within the <select> element. The value attribute on each <option> element then corresponds to the name attribute on the <select> element.

Each <option> element wraps the text (which is visible to users) of an individual option within the list.

Much like the checked Boolean attribute for radio buttons and check boxes, drop-down menus can use the selected Boolean attribute to preselect an option for users.

<select name="day">
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select>


**Multiple Selections**

The Boolean attribute multiple, when added to the <select> element for a standard drop-down list, allows a user to choose more than one option from the list at a time. Additionally, using the selected Boolean attribute on more than one <option> element within the menu will preselect multiple options.

The size of the <select> element can be controlled using CSS and should be adjusted appropriately to allow for multiple selections. It may be worthwhile to inform users that to choose multiple options they will need to hold down the Shift key while clicking to make their selections.


<select name="day" multiple>
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select>


#Form Buttons
After a user inputs the requested information, buttons allow the user to put that infor- mation into action. Most commonly, a submit input or submit button is used to process the data.

**Submit Input**

Users click the submit button to process data after filling out a form. The submit button is created using the <input> element with a type attribute value of submit. The value attribute is used to specify the text that appears within the button.

<input type="submit" name="submit" value="Send">


**Submit Button**

As an <input> element, the submit button is self-contained and cannot wrap any other content. If more control over the structure and design of the input is desired—along with the ability to wrap other elements—the <button> element may be used.

The <button> element performs the same way as the <input> element with the type attribute value of submit; however, it includes opening and closing tags, which may wrap other elements. By default, the <button> element acts as if it has a type attribute value of submit, so the type attribute and value may be omitted from the <button> element if you wish.

Rather than using the value attribute to control the text within the submit button, the text that appears between the opening and closing tags of the <button> element will appear.


<button name="submit">
  <strong>Send Us</strong> a Message
</button>


#Organizing Form Elements

Knowing how to capture data with inputs is half the battle. Organizing form elements and controls in a usable manner is the other half. When interacting with forms, users need to understand what is being asked of them and how to provide the requested information.

By using labels, fieldsets, and legends, we can better organize forms and guide users to properly complete them.

**Label**

Labels provide captions or headings for form controls, unambiguously tying them together and creating an accessible form for all users and assistive technologies. Created using the <label> element, labels should include text that describes the inputs or controls they pertain to.

Labels may include a for attribute. The value of the for attribute should be the same as the value of the id attribute on the form control the label corresponds to. Matching up the for and id attribute values ties the two elements together, allowing users to click on the <label> element to bring focus to the proper form control.


<label for="username">Username</label>
<input type="text" name="username" id="username">

<label>
  <input type="radio" name="day" value="Friday" checked> Friday
</label>
<label>
  <input type="radio" name="day" value="Saturday"> Saturday
</label>
<label>
  <input type="radio" name="day" value="Sunday"> Sunday
</label>


**Fieldset**

Fieldsets group form controls and labels into organized sections. Much like a <section> or other structural element, the <fieldset> is a block-level element that wraps related elements, specifically within a <form> element, for better organization. Fieldsets, by default, also include a border outline, which can be modified using CSS.


<fieldset>
  <label>
    Username
    <input type="text" name="username">
  </label>
  <label>
    Password
    <input type="text" name="password">
  </label>
</fieldset>

**Legend**

A legend provides a caption, or heading, for the <fieldset> element. The <legend> element wraps text describing the form controls that fall within the fieldset. The markup should include the <legend> element directly after the opening <fieldset> tag. On the page, the legend will appear within the top left part of the fieldset border.

<fieldset>
  <legend>Login</legend>
  <label>
    Username
    <input type="text" name="username">
  </label>
  <label>
    Password
    <input type="text" name="password">
  </label>
</fieldset>


#Form & Input Attributes

To accommodate all of the different form, input, and control elements, there are a number of attributes and corresponding values. These attributes and values serve a handful of different functions, such as disabling controls and adding form validation. Described next are some of the more frequently used and helpful attributes.

**Disabled**

The disabled Boolean attribute turns off an element or control so that it is not available for interaction or input. Elements that are disabled will not send any value to the server for form processing.

￼Applying the disabled Boolean attribute to a <fieldset> element will disable all of the form controls within the fieldset. If the type attribute has a hidden value, the hidden Boolean attribute is ignored.


<label>
  Username
  <input type="text" name="username" disabled>
</label>


**Placeholder**

The placeholder HTML5 attribute provides a hint or tip within the form control of an <input> or <textarea> element that disappears once the control is clicked in or gains focus. This is used to give users further information on how the form input should be filled in, for example, the email address format to use.


<label>
  Email Address
  <input type="email" name="email-address" placeholder="name@domain.com">
</label>

The main difference between the placeholder and value attributes is that the value attribute value text stays in place when a control has focus unless a user manually deletes it. This is great for pre-populating data, such as personal information, for a user but not for providing suggestions.


**Required**

The required HTML5 Boolean attribute enforces that an element or form control must contain a value upon being submitted to the server. Should an element or form control not have a value, an error message will be displayed requesting that the user complete the required field. Currently, error message styles are controlled by the browser and cannot be styled with CSS. Invalid elements and form controls, on the other hand, can be styled using the :optional and :required CSS pseudo-classes.

Validation also occurs specific to a control’s type. For example, an <input> element with a type attribute value of email will require not only that a value exist within the control, but also that it is a valid email address.

<label>
  Email Address
  <input type="email" name="email-address" required>
</label>


**Additional Attributes**

Other form and form control attributes include, but are not limited to, the following. Please feel free to research these attributes as necessary.

accept  autocomplete    autofocus   formaction  formenctype formmethod  formnovalidate  formtarget  max maxlength   min pattern readonly    selectionDirection  step












