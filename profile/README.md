






## [@WEVER]() &middot; [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/) [![npm version](https://img.shields.io/npm/v/xeonjs.svg?style=flat)](https://www.npmjs.com/package)

**A fully customizable, flexible, declarative,
component-based JavaScript framework & library to build
complex and incredible UI (User Interface).**

It makes developing web-applications **easy, fast &
painless**. It allows you to create component view in
your application and easily manage them.
Writing both HTML & Javascript together without
template litrals makes the **application declarative,
easier to manage and faster**.

* ***Javascript XML:***
Write both HTML and Javascript together in a single
Javascript file. Rather than using template literals,
here you are allowed to use Javascript XML expression (JSX).

* ***Component Based:***
Create your own XEON Component to create and manage
complicated User Interfaces. Those components are
reusable and can be used in multiple places.

* ***In-built Router:***
XEON JS comes with a built-in router that helps you to
navigate between different pages. It's a very simple but
powerfull router, including url parameters to make your
application more dynamic.
<hr />


## **_Example_**
```jsx
import xeon from "xeon";
import Remarkable from "remarkable";

export default function App(props) {
	var md = new Remarkable();

	// Create unique ids.
	const id = xeon.uuid(["input", "result"]);

	const handleChange = e => {
		var value = e.target.value;
		const result = document.getElementById(id.result);

		result.innerHTML = md.render(value);
	}

	// this function will execute only when the component is rendered.
	xeon.onInit(() => {
		document.getElementById(id.result).innerHTML = md.render(document.getElementById(id.input).value);
	});

	// Return JSX or XSET.
	return (
		<div style={{height: "100%" }}>
			<h2 style={{ textAlign: "center" }}>Live Markdown Editor</h2>
			<div style={{ padding: "10px" }}>
				<textarea style={{
						width: "100%",
						resize: "vertical",
						minHeight: "100px",
						maxHeight: "300px",
						padding: "10px"
					}}
					id={id.input}
					onKeyPress={handleChange}
					onChange={handleChange}
					onKeyUp={handleChange}
				># Hello</textarea>

				<div style={{
						width: "100%",
						border: "1px solid",
						padding: "10px"
				}}>
					<h3 style={{ textAlign: "center" }}>Output</h3>
					<div id={id.result}></div>
				</div>
			</div>
		</div>
	);
}
```
### The above code example simply render this.
<img style="width: 100%;" src="./docs/assets/md-example.png" />












### License
@wever is [MIT licensed](./LICENSE).
