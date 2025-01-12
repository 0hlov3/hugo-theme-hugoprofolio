# Hugo Profolio

Hugo Profolio is a minimalist, responsive Hugo theme designed for developers, designers, and professionals to showcase their resumes, blogs, and portfolios with a clean and modern aesthetic. Inspired by the [Jekyll theme minimal-resume](https://github.com/murraco/jekyll-theme-minimal-resume), this theme adds blogging capabilities and extended configuration options.

## Features
- 🖋 **Blogging support**: Publish articles easily.
- 📄 **Resume builder**: Display your resume in a professional format.
- 🖼 **Portfolio**: Highlight your projects and achievements.
- 🎨 **Minimalist design**: Clean and responsive layout for a professional look.
- 🛠 **Easy customization**: Update configurations with a few edits.
- 📱 **Responsive design**: Looks great on desktop, tablet, and mobile.
- 🧩 **Support for menus**: Define and organize navigation menus easily.

## Installation

1. Clone the repository into your Hugo site's `themes` directory:
```bash
git clone https://github.com/0hlov3/hugo-theme-hugoprofolio.git themes/hugo-profolio
```
2. Update your `hugo.toml` to use the theme:
```toml
theme = "hugo-profolio"
```
3. Build and run your Hugo site:
```bash
hugo server
```

Visit http://localhost:1313 to see your site live.

## Configuration
Configure the theme in your Hugo site's `hugo.toml`. Below is a sample configuration:
```toml
baseURL = "https://example.com/"
languageCode = "en-us"
title = "My Portfolio"
theme = "hugo-profolio"

[params]
  description = "Showcasing my portfolio and blog"
  github_username = "your-username"
  linkedin_username = "your-linkedin"
  contact_email = "your-email@example.com"

[[menus.main]]
  name = "Home"
  pageRef = "/"
  weight = 10

[[menus.main]]
  name = "Posts"
  pageRef = "/posts"
  weight = 20

[[menus.main]]
  name = "Portfolio"
  pageRef = "/portfolio"
  weight = 30

[[menus.main]]
  name = "Resume"
  pageRef = "/resume"
  weight = 40



```

## Dependencies
Hugo Profolio has minimal dependencies to ensure ease of use. Make sure you have the following installed:

 - [Hugo](https://gohugo.io/) (version 0.55.0 or higher): Download from gohugo.io.
 - A modern web browser for testing.

## Contributing

We welcome contributions! Please fork the repository and submit a pull request. Ensure your changes align with the project's goals and design philosophy.

## License

This project is licensed under the [MIT License](./LICENSE). Feel free to use, modify, and distribute.