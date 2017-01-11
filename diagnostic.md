# Ember Components Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  Give an example of a visual hierarchy that could be modeled with components. Explain why each piece might be it's own component.

    ```md
    Hear me out, let's say we are making a list app. A list has a title and
    items in the list. Both the title and the list could be components. So, when
    we are looking at the differesnt lists, each title is rendered as a component
    and when you click on them, it renders that list. Each item of that list is
    also a component.
    ```

1.  What is the command to generate a new component called '`my-map`'?

    ```sh
    ember g component my-map
    ```

1.  What files are created and/or edited to produce a component, and what are their responsibilities?

    ```md
    `component.js` and  `template.hbs` are rendered. Template handles what the user
    does. So in our hypothetical list app, template handles the data from the model
    and displays it on screen. It is also where we could put links and buttons
    to provide user interaction. Component handles most of the work that happens on the backend. It
    can send data back up the ember chain and it does all this by `extend`ing the
    existing ember object
    ```

1.  Suppose you have a component '`my-contact`', which is loaded from
    '`app/contacts/template.hbs`' when visiting the `/contacts` route. What is
    the syntax (code that is written) to render this component inside that template?

    ```html
  {{#each model as |contacts|}}
    {{my-contact contact=contact}}
  {{/each}}

    ```

1.  Each contact has multiple phone numbers. Suppose you also have '`my-phone`'
    nested under '`my-contact`'. What is the code you would write in
    '`app/components/my-contact/template.hbs`' to load the nested component and
    pass it data?

    ```html
    {{each contact.phone as |phone|}}
      {{my-contact phone=phone}}
    {{/each}}
    ```
