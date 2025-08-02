
document.addEventListener('DOMContentLoaded',function(){
	//定义全局函数
    window.render = function(a){
	    const span = document.createElement("span");
		span.innerHTML=a;
		document.body.appendChild(span);
	};
	// 1. 获取所有 type 为 text/my-syntax 的脚本
	document.querySelectorAll('script[type="text/guang"]').forEach(function(script){
		//2. 读取自定义语法内容
		let customCode = script.textContent;
		//3. 处理自定义语法部分
		const macthCode = customCode.matchAll(/\<\w+\>/g);
		for(const squ of macthCode){
			 const tmp = squ[0];
			 let tmp2 = tmp.replace("<","").replace(">","");
			 tmp2 = tmp2+"*"+tmp2;
			 customCode=customCode.replace(tmp,tmp2);
		}
		//动态插入编译后的代码，原生script
		 const newScript = document.createElement('script');
		 newScript.textContent = `${customCode}`;
		 document.body.appendChild(newScript);
	});
});
