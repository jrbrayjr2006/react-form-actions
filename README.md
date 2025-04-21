# React Form Actions Examples

Form Actions is a new feature that is available in React 19 or higher.

When a function is used as the target of the `action` prop of a React form, the FormData object is passed to the function by default.  This is different behaviour than would be observed when using the `onSubmit` prop.  When using the `onSubmit` prop, an event would be the default input parameter.

Remember to add the `name` prop to all elements of the form.

```js
import { useActionState } from "react";
export default function SomeForm() {
    function myActionFn(previousFormState, formData) {
        // some logic here
    }

    const [formState, formAction] = useActionState(myActionFn, {errors: null});

    return (
        <form action={formAction}>
            {/* ...some logic and elements here */}
            {formState.errors && <ul></ul>}
        </form>
    )
}
```

**NOTE:** As of April 21, 2025, there is a React bug that does not populate the defaultValue properly for drop-down lists when using `useActionState`.  The maintainers of the React library will need to address this.

## References

- [useActionState](https://react.dev/reference/react/useActionState)
- [React 19 Actions – How to Simplify Form Submission and Loading States](https://www.freecodecamp.org/news/react-19-actions-simpliy-form-submission-and-loading-states/)