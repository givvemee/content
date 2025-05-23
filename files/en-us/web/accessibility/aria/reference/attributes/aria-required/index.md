---
title: "ARIA: aria-required attribute"
short-title: aria-required
slug: Web/Accessibility/ARIA/Reference/Attributes/aria-required
page-type: aria-attribute
spec-urls: https://w3c.github.io/aria/#aria-required
sidebar: accessibilitysidebar
---

The `aria-required` attribute indicates that user input is required on the element before a form may be submitted.

## Description

When a semantic HTML {{htmlelement("input")}}, {{htmlelement("select")}}, or {{htmlelement("textarea")}} must have a value, it should have the [`required`](/en-US/docs/Web/HTML/Reference/Elements/input#required) attribute applied to it. The HTML `required` attribute disables submitting the form unless the required form controls have valid values, while ensuring those navigating with the aid of assistive technologies understand which semantic form controls need valid content.

When form controls are created using non-semantic elements, such as a {{HTMLElement('div')}} with a [role](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles) of [`checkbox`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/checkbox_role), the `aria-required` attribute should be included, with a value of `true`, to indicate to assistive technologies that user input is required on the element for the form to be submittable. The `aria-required` attribute can be used with HTML form elements; it is not limited to elements that have an ARIA role assigned.

Similar to the HTML `required` attribute set on semantic HTML form controls, the `aria-required` attribute explicitly conveys to assistive technologies that the element is required before a form may be submitted. The `required` attribute on a semantic HTML form control will prevent the form control from being submitted if no value is present — providing native error messaging in some browsers if a required value is invalid when the user attempts to submit the form. The `aria-required` attribute, like all ARIA states and properties, has no impact on element functionality. Functionality and behavior must be added in with JavaScript.

> [!NOTE]
> ARIA only modifies the accessibility tree, modifying how assistive technology presents content to users. ARIA does not change anything about an element's function or behavior. When not using semantic HTML elements for their intended purpose and default functionality, you must use JavaScript to manage behavior, focus, and ARIA states.

The CSS {{CSSXRef(':required')}} and {{CSSXRef(':optional')}} pseudoclasses match {{htmlelement("input")}}, {{htmlelement("select")}}, and {{htmlelement("textarea")}} elements based on whether they are required or optional, respectively. When using non-semantic elements as form controls, you don't get this CSS pseudoclass selector benefit. You can, however, use attribute selectors if the attribute is present: `[aria-required="true"]` or `[aria-required="false"]`.

If a form contains both required and optional form elements, the required elements should be indicated visually using a treatment that does not rely solely on color to convey meaning. Typically, descriptive text and/or an icon are used.

> [!NOTE]
> Which elements are required should be apparent to all users. Ensure the visual presentation indicates the form control is required in a consistent, visible manner, remembering that color is not enough to convey information.

## Examples

The attribute should be added to the form-control role. If the user needs to fill in an email address [`textbox`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/textbox_role), include `aria-required="true"` on the textbox.

```html
<div id="tbLabel">Email Address *</div>
<div
  role="textbox"
  contenteditable
  aria-labelledby="tblabel"
  aria-required="true"
  id="email1"></div>
```

> [!NOTE]
> If the field's label already contains the word "required", it is recommended to leave out the `aria-required` attribute. This avoids that screen readers read out the term "required" twice.

In this example, JavaScript must be used to prevent the containing form from being submitted if the textbox has no content.

This could be written semantically, without the need for JavaScript:

```html
<label for="email1">Email Address (required)</label>
<input type="email" id="email1" required />
```

## Values

- `true`
  - : The element requires a value or must be checked for the form to be submittable.
- `false`
  - : The element is not required.

## Associated interfaces

- {{domxref("Element.ariaRequired")}}
  - : The [`ariaRequired`](/en-US/docs/Web/API/Element/ariaRequired) property, part of the {{domxref("Element")}} interface, reflects the value of the `aria-required` attribute.
- {{domxref("ElementInternals.ariaRequired")}}
  - : The [`ariaRequired`](/en-US/docs/Web/API/ElementInternals/ariaRequired) property, part of the {{domxref("ElementInternals")}} interface, reflects the value of the `aria-required` attribute.

## Associated roles

Used in roles:

- [`checkbox`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/checkbox_role)
- [`combobox`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/combobox_role)
- [`gridcell`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/gridcell_role)
- [`listbox`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/listbox_role)
- [`radiogroup`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/radiogroup_role)
- [`spinbutton`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/spinbutton_role)
- [`textbox`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/textbox_role)
- [`tree`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/tree_role)

Inherits into roles:

- [`columnheader`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/columnheader_role)
- [`rowheader`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/rowheader_role)
- [`searchbox`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/searchbox_role)
- [`switch`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/switch_role)
- [`treegrid`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/treegrid_role)

## Specifications

{{Specifications}}

## See also

- HTML [`required`](/en-US/docs/Web/HTML/Reference/Elements/input#required) attribute
- [`:optional` pseudoclass](/en-US/docs/Web/CSS/:optional)
- [`:required` pseudoclass](/en-US/docs/Web/CSS/:required)
- [`aria-invalid` attribute](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-invalid)
- [MDN Understanding WCAG, Guideline 3.3 explanations](/en-US/docs/Web/Accessibility/Guides/Understanding_WCAG/Understandable#guideline_3.3_%e2%80%94_input_assistance_help_users_avoid_and_correct_mistakes)
- [Understanding Success Criterion 3.3.2 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/minimize-error-cues.html)
