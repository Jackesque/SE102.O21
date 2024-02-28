# Buổi 1

Clone github của thầy về bằng terminal của windows. Chạy lệnh: 

```console
git clone https://github.com/dungdna2000/SE102.O21.TestGit
```

Mở visual studio, mở project (chọn file đuôi .sln hay .vcxproj)

Gặp lỗi thiếu d3d10.

Code | Description
|---|---|
E1696 | cannot open source file "d3dx10.h"

Giải: trong solution explorer, chuột phải project (cái tên project đc in đậm một tí), chọn properties (ở cuối cùng), linker -> input -> additional dependency -> edit -> nhập d3d10.lib.
Cái dòng additional dependencies trông ntn:
Additional Dependencies: d3d10.lib;%(AdditionalDependencies)

Sau đó cài cái này bằng NuGet:

HOW TO INSTALL Microsoft.DXSDK.D3DX
===================================
1) Tools > NuGet package manager > Package Manager Console
2) execute command :  Install-Package Microsoft.DXSDK.D3DX

Gặp thêm lỗi kỳ quặc:

Code | Description
|---|---|
LNK2019 | unresolved external symbol main referenced in function "int __cdecl invoke_main(void)" (?invoke_main@@YAHXZ)
LNK1120 | 1 unresolved externals	

Giải: mở lại cái linker lúc nãy (chuột phải project -> properties -> linker), chọn all options, tìm cái SubSystem. Hiện tại nó đang là Console. Chuyển nó sang Windows.

Chạy: ctrl+F5 hoặc nhấn cái nút play tam giác màu xanh.
Mẹo: trong Solution Explorer, alt+enter cho lẹ.
