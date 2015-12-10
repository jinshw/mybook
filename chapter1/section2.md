# 第二节 微信端标签替换
- 微信端固有的代码  
    img {
        height: auto!important;
    }      
    .rich_media_content p {
        clear: both;
        min-height: 1em;
        white-space: pre-wrap;
    }   
    .rich_media_content * {
        max-width: 100%!important;
        box-sizing: border-box!important;
        -webkit-box-sizing: border-box!important;
        word-wrap: break-word!important;
    }   
    body {
        -webkit-touch-callout: none;
        font-family: "Helvetica Neue",Helvetica,"Hiragino Sans GB","Microsoft   YaHei",Arial,sans-serif;
        background-color: #f3f3f3;
        line-height: inherit;
    }   
    html {
        -ms-text-size-adjust: 100%;
        -webkit-text-size-adjust: 100%;
        line-height: 1.6;
    }   
****
## 需要转化标签方案
1. 在内联CSS中添加 `!important`
2. 替换`.rich_media_content p` `img` `body` `html` 样式
3. 在JS中用正则表达式替换字符串







