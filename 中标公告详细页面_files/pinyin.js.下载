/**
 * 获取拼音简码
 * 参数：
 * 	str：目标字符串
 * 	ids：接收输出值得控件id，如果有多个id，用"-"分隔。
 * 	upperCase：输出的字符串是否为大写，值为true或false，可以不传或传入null，默认为false。
 */
function getPYCode(str, ids, upperCase) 
{
	if(upperCase == undefined || upperCase == null) upperCase = false;
    var result = "";
    for (var index = 0; index < str.length; index++) 
    {
        result += getPY(str.charAt(index).toString());
    }

    if(upperCase) result = result.toUpperCase();

    var fields = ids;
    if(fields.indexOf("-") != -1)
    {
        var field = fields.split("-");
        for(var index = 0; index < field.length; index++)
        {
        	document.getElementById(field[index]).value = result;
        }
    }
    else
    {
    	document.getElementById(ids).value = result;
    }
}

/**
 * 获取单个字符的拼音简码
 */
function getPY(s)
{
    if (s != "")
    {
       execScript("tmp=asc(\"" + s + "\")", "vbscript");
        tmp = 65536 + tmp;
        var py = "";
        if (tmp >= 45217 && tmp <= 45252) py = "a";
        else if (tmp >= 45253 && tmp <= 45760) py = "b";
        else if (tmp >= 45761 && tmp <= 46317) py = "c";
        else if (tmp >= 46318 && tmp <= 46825) py = "d";
        else if (tmp >= 46826 && tmp <= 47009) py = "e";
        else if (tmp >= 47010 && tmp <= 47296) py = "f";
        else if ((tmp >= 47297 && tmp <= 47613) || (tmp == 63193)) py = "g";
        else if (tmp >= 47614 && tmp <= 48118) py = "h";
        else if (tmp >= 48119 && tmp <= 49061) py = "j";
        else if (tmp >= 49062 && tmp <= 49323) py = "k";
        else if (tmp >= 49324 && tmp <= 49895) py = "l";
        else if (tmp >= 49896 && tmp <= 50370) py = "m";
        else if (tmp >= 50371 && tmp <= 50613) py = "n";
        else if (tmp >= 50614 && tmp <= 50621) py = "o";
        else if (tmp >= 50622 && tmp <= 50905) py = "p";
        else if (tmp >= 50906 && tmp <= 51386) py = "q";
        else if (tmp >= 51387 && tmp <= 51445) py = "r";
        else if (tmp >= 51446 && tmp <= 52217) py = "s";
        else if (tmp >= 52218 && tmp <= 52697) py = "t";
        else if (tmp >= 52698 && tmp <= 52979) py = "w";
        else if (tmp >= 52980 && tmp <= 53688) py = "x";
        else if (tmp >= 53689 && tmp <= 54480) py = "y";
        else if (tmp >= 54481 && tmp <= 62289) py = "z";
        else py = s.charAt(0);
        return py;
    }
    else
    {
    	return "";
    }
}
