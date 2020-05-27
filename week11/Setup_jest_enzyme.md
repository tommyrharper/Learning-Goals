#  How to set it up

```
npm i --save-dev enzyme enzyme-adapter-react-16
npm install --save-dev jest-enzyme
```

And then you're ready to go! In your test files you can simply require or import enzyme:

ES6:

```javascript
// setup file
import { configure } from 'enzyme';
import Adapter from 'enzyme-adapter-react-16';
import "jest-enzyme";

configure({ adapter: new Adapter() });
```

```javascript
// test file
import { shallow, mount, render } from 'enzyme';

const wrapper = shallow(<Foo />);
```
Then you can create tests like this:

```javascript
// using enzyme
import React from 'react';
import { shallow } from "enzyme";

// using react-testing-library
import { render } from "@testing-library/react";

import Posts from './Posts.js';

it("renders without crashing", () => {
  shallow(<Posts />);
});

it("has h1 with Posts in it (enzyme)", () => {
  const wrapper = shallow(<Posts />);
  const title = <h1>Posts</h1>;
  expect(wrapper).toContainReact(title);
});

it("has h1 with Posts in it (rtl)", () => {
  const { getByText } = render(<Posts />);
  expect(getByText("Posts")).toBeInTheDocument();
});
```