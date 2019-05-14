# Baidu-AIP-OCR
主要基于百度文字识别SDK(C#),做了二次封装，生成COM,供Delphi 调用

1、window系统必须安装 Microsoft .NET Framework 4.5  
2、封装了 身份证正面、身份证反面、银行卡、驾驶证、行驶证、车牌识别、普通文字识别、网路图片文字识别和高精度识别。
如果想看百度关于图片识别C# Sdk 请链接 http://ai.baidu.com/docs#/OCR-Csharp-SDK/top

3、 将baiduOcr.tlb 加入到delphi 中， component-> import component->import a type Library中 会生成一个 BaiduOCR_TLB.Pas

4、引入 BaiduOCR_TLB 到项目中

5、调用接口函数

function GetBaiduOCRInf: Baidu_OcrInf;
var
 Baidu_OcrImp: _Baidu_OcrImp;
begin
  if not Assigned(Baidu_OcrImp) then
  begin
    Baidu_OcrImp:= CoBaidu_OcrImp.Create;
  end;
  Result:= (Baidu_OcrImp as Baidu_OcrInf);
end;

 6、百度 的key 和 SECRET_KEY 赋值    
 //请输入baidu API_KEY  必填项目
 
  GetBaiduOCRInf.Api_KEY:= 'baidu API_KEY';
  
   //请输入baidu SECRET_KEY 必填项目
   
  GetBaiduOCRInf.SECRET_KEY:= 'baidu SECRET_KEY';
  
7、调用 BaiduOCR_TLB 中的函数
