### 懒加载原理
```
		function isshow($node){
			return $node.offset().top <= $(window).height() +$(window).scrollTop()
		}
		function loadimg($img){
			$img.attr('src',$img.attr('data-src'))
			$img.attr('data-loaded','true')
		}
		$(window).on('scroll',function(){
			$('img').not('[data-loaded]').each(function(){
				if(isshow($(this))){
					loadimg($(this))
				}
			})
		})
    //判断指定目标是否出现在视野
    //将指定目标的源进行替换，显示真实图片
    //监控窗口滚动
```
