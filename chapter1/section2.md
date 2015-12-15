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
    - `<iframe>` 视频标签微信中显示：Android手机可以显示播放，iPhone6P 也可以显示播放，限制:`data-src`和`src` 属性必须是可访问视频页面 。
    - iphone5、iPhone6 优酷`iframe`视频不显示 
    - 腾讯视频获取外链
    
        *方案一：flash外链*
        http://v.qq.com/cover/0/0n27nmk72me0ymg.html?vid=n0176p10sc0 （腾讯视频网站真正视频地址）

        http://cache.tv.qq.com/qqplayerout.swf?vid=n0176p10sc0  （？前内容 加上 vid后的内容）  移动端不支持（浏览器和微信都不支持）
        
        *方案二：iframe（使用方案二）*
        事例：把vid=后内容换成实际视频地址内容。
            <iframe  " src="http://v.qq.com/iframe/player.html?vid=n0176p10sc0&amp;width=300&amp;height=200&amp;auto=0" allowfullscreen="" frameborder="0" style="width:100%;height:3rem"></iframe>
        







