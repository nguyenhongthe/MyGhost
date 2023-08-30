# My Ghost

A minimal, ghost theme for [Nguyễn Hồng Thế Blog](https://nguyenhongthe.net).

# Instructions

1. [Download this theme](https://github.com/nguyenhongthe/myghost/archive/main.zip)
2. Log into Ghost, and go to the `Design` settings area to upload the zip file

# Development

Edition styles are compiled using Gulp/PostCSS to polyfill future CSS spec. You'll need [Node](https://nodejs.org/), [Yarn](https://yarnpkg.com/) and [Gulp](https://gulpjs.com) installed globally. After that, from the theme's root directory:

```bash
# Install
yarn

# Run build & watch for changes
yarn dev
```

Now you can edit `/assets/css/` files, which will be compiled to `/assets/built/` automatically.

To run a theme locally, you need to symlink a theme to your local Ghost site.

```bash
# run a theme locally
ln -s /dir/to/your/themes/myghost /dir/to/your/ghost-site/content/themes/myghost
```

Restart your Ghost instance and the theme will be listed in the Design settings.

The `zip` Gulp task packages the theme files into `dist/myghost.zip`, which you can then upload to your site.

```bash
yarn zip
```

# Copyright & License

Copyright (c) 2013-2023 Nguyen Hong The Dev - Released under the [MIT license](LICENSE).
