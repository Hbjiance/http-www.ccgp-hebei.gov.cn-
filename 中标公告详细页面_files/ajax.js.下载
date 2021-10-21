/**
 * 用于支持AJAX请求的JS
 * 需求基础类库：
 * 		1.jQuery
 * 		2.QUI
 * 作者：王亦鹏
 */
var ajax = {
	/**
	 * 异步请求远程服务器资源
	 * url： 资源地址
	 * method: 请求方式
	 * params: 参数
	 * funSuccess：成功回调函数 function(string data) 可以不传或传入null
	 * funError：失败回调函数 function(jqXHR jqXHR, String textStatus, String errorThrown) 可以不传或传入null
	 * showWaiting：是否显示等待对话框，可以可以不传或传入null，默认为true
	 * _async：如果要发送同步请求，将此值设置为false，可以不传或传入null，默认为true
	 */
	go: function(url, method, params, funSuccess, funError, showWaiting, _async)
	{
		if(funSuccess == undefined || funSuccess == null)
		{
			funSuccess = function(data) { top.Dialog.alert(data); };
		}
		if(funError == undefined || funError == null)
		{
			funError = function(jqXHR, textStatus, errorThrown) { };
		}
		if(showWaiting == undefined || showWaiting == null)
		{
			showWaiting = true;
		}
		if(_async == undefined || _async == null) _async = true;
		if(showWaiting)
		{
			ajax.showWaitingBox();
		}
		$.ajax({
			url: url,
			type: method,
			data: params,
			success: funSuccess,
			error: funError,
			async: _async,
			complete: function(jqXHR, textStatus){
				if(showWaiting)
				{
					ajax.hideWaitingBox();
				}
			}
		});
	},
	
	/**
	 * 显示等待对话框
	 */
	showWaitingBox: function()
	{
		showProgressBar();
	},
	
	/**
	 * 隐藏等待对话框
	 */
	hideWaitingBox: function()
	{
		closeProgress();
	}
}