[View code on GitHub](https://github.com/solana-labs/solana/blob/master/docs/src/pages/getstarted.jsx)

The `GetStartedPage` function is a React component that renders a page with quick start guides for developers who want to build on the Solana blockchain. The page is composed of several sections, each containing a `Card` component that provides a brief description of a specific guide and a link to access it. 

The `CardLayout` component is used to provide a consistent layout for the page, with a sidebar and a title. The `sidebarKey` prop specifies which sidebar to use, while the `title` and `description` props provide a heading and a brief description for the page. The `path` prop specifies the URL path for the page.

The first section of the page contains a heading and a brief description of what the quick start guides are about. It also contains a link to the "Hello World" guide, which is the first guide that developers are encouraged to try. 

The second section of the page contains three `Card` components, each with a header and a body. The `to` prop specifies the URL path for each guide. The `header` prop provides a label for the guide, while the `body` prop provides a brief description