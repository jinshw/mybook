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
4. `.rich_media_content p` css替换：
   
        .rich_media_content p {
            clear: both;
            min-height: 1em;
            white-space: normal;// 浏览器空白忽略(待定)
        }  
    
5. 测试问题：
    - `<video>`视频标签在微信中，Android手机刚进入时是视频位置显示是灰色，点击一下才可以播放。iPhone6 不显示视频。
    - `<iframe>` 视频标签微信中显示：Android手机可以显示播放，iPhone6 也可以显示播放，限制:`data-src`和`src` 属性必须是可访问视频页面。







