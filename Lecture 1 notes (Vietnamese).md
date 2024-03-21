# Buổi 1

Mở visual studio, tạo project mới. Tick vào `Place solution and project in the same directory`. Chọn `Windows Desktop Wizard`. `Application type` là `Desktop Application (.exe)`. `Additional options` chỉ tick mỗi `Empty project`, còn lại không tick.

Thêm tất cả files từ folder `sample00`: chuột phải Resource Files -> Add existing items... Di chuyển file `main.cpp` sang Source Files.

Gặp lỗi thiếu d3d10.

| Code  | Description                        |
| ----- | ---------------------------------- |
| E1696 | cannot open source file "d3dx10.h" |

Giải: trong solution explorer, chuột phải project (cái tên project đc in đậm một tí), chọn properties (ở cuối cùng), linker -> input -> additional dependency -> edit -> nhập d3d10.lib.

Cái dòng additional dependencies trông ntn:

Additional Dependencies: d3d10.lib;%(AdditionalDependencies)

Sau đó cài cái này bằng NuGet:

**HOW TO INSTALL Microsoft.DXSDK.D3DX**

1. Tools > NuGet package manager > Package Manager Console
2. execute command : Install-Package Microsoft.DXSDK.D3DX

Nếu gặp thêm lỗi kỳ quặc:

| Code    | Description                                                                                                    |
| ------- | -------------------------------------------------------------------------------------------------------------- |
| LNK2019 | unresolved external symbol main referenced in function "int \_\_cdecl invoke_main(void)" (?invoke_main@@YAHXZ) |
| LNK1120 | 1 unresolved externals                                                                                         |

Giải: mở lại cái linker lúc nãy (chuột phải project -> properties -> linker), chọn all options, tìm cái SubSystem. Hiện tại nó đang là Console. Chuyển nó sang Windows.

Chạy: ctrl+F5 hoặc nhấn cái nút play tam giác màu xanh.

Expected: viên gạch đi từ trái sang phải từ góc giữa trái màn hình.

Mẹo: chỗ Resource Files, shift+alt+a. Còn trong Solution Explorer, sau khi chọn Project, alt+enter cho lẹ.

Bài tập: làm cho viên gạch đi từ trên xuống từ góc trên giữa màn hình.
