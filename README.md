# React Form Actions Examples

Form Actions is a new feature that is available in React 19 or higher.

When a function is used as the target of the `action` prop of a React form, the FormData object is passed to the function by default.  This is different behaviour than would be observed when using the `onSubmit` prop.  When using the `onSubmit` prop, an event would be the default input parameter.

Remember to add the `name` prop to all elements of the form.

```ts
export default function myFn() {
    function handleForm(formData) {
        // some logic here
    }
    return (
        <form action={myFn}>
            {/* ...some logic and elements here */}
        </form>
    )
}
```

## References

- [useActionState](https://react.dev/reference/react/useActionState)
- [React 19 Actions – How to Simplify Form Submission and Loading States](https://www.freecodecamp.org/news/react-19-actions-simpliy-form-submission-and-loading-states/)