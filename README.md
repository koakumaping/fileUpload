# fileUpload
html5文件上传插件,支持多文件上传。

# 用法

## 文件控件发生变化时，调用uploadFile函数，触发上传功能

file.onchange = function() {
    fileUpload(this.files, '/picuploads/', function(data){
	    console.log(data);
	    if(data.ResultCode == '0'){
	        $('.info-avatar-img').attr('src', data.Data.Path);
	    }
	});
};

## 在区域内释放拖入文件时，调用文件上传函数
area.ondrop = function(ev) {
    ev.preventDefault();
    var dt = ev.dataTransfer;
    fileUpload(this.files, '/picuploads/', function(data){
	    console.log(data);
	    if(data.ResultCode == '0'){
	        $('.info-avatar-img').attr('src', data.Data.Path);
	    }
	});
};
