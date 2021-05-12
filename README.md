# npm-template-html

Tool tạo file .html tĩnh từ file template và các file content .

    1 : Kế thừa ý tưởng thiết kế từ https://github.com/grit96/template-html .
    2 : Nâng cấp và tối ưu .

## Installation
```sh
$ npm install -g npm-template-html
or
$ npm install -g https://github.com/mana147/npm-template-html.git
```
## Help
```sh
Tool tạo file .html tĩnh từ file template và các file content .

Installation : npm install -g npm-template-html 

Syntax : npm-template-html name_file_template.html

-h|--help        hiển thị help
-v|--version     hiển thị version number
```

## Sample usage

Hướng dẫn sử dụng cơ bản :
-   tạo file index.html chứa các thẻ build tag  `<!-- build:nametag -->` , 
-   tạo thư mục `template` chứa các file content , bắt buộc tạo thư mục này vì tool sẽ quét các file trong đây
-   tạo các file content chứa cặp thẻ `<!-- build:nametag -->` và `<!-- /build:nametag -->` 
-   tool run build sẽ tự động tạo thư mục `build` chứa file sau khi đã build

- xem ví dụ `examples/examples2/index.html` để hiểu về tách một dự án thực tế nhiều lớp và nhiều folder con chứa các file content

`index.html`
```html
<!DOCTYPE html>

<html lang="en">

<head>
    <meta charset="utf-8">
    <title>
        <!-- build:title -->
    </title>
</head>

<body>
    <div id="content">
        <!-- build:content -->
    </div>
</body>

</html>
```

`template/title.html`
```
<!-- build:title -->

    Lorem ipsum 

<!-- /build:title -->
```

`template/content.html`
```
<!-- build:content -->

    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor
    incididunt ut labore et dolore magna aliqua.

<!-- /build:content -->
```

`build/index.html`
```html
<!DOCTYPE html>

<html lang="en">

<head>
    <meta charset="utf-8">
    <title>
        Lorem ipsum

    </title>
</head>

<body>
    <div id="content">

        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor
        incididunt ut labore et dolore magna aliqua.

    </div>
</body>

</html>
```