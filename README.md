# Stable Diffusion web UI
基於用於穩定擴散的 Gradio 庫的瀏覽器界面。

![](screenshot.png)

## Features
[帶有圖像的詳細功能展示](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features):
- 原始的 txt2img 和 img2img 模式
- 一鍵安裝並運行腳本（但您仍然必須安裝 python 和 git）
- 塗裝
- 修復
- 彩色素描
- 提示矩陣
- 穩定擴散高檔
- 注意，指定模型應該更多注意的文檔部分
     - 穿著 `((tuxedo))` 的男人 - 會更加註意燕尾服
     - 穿著 `(tuxedo:1.21)` 的男人 - 替代語法
     - 選擇文本並按 `Ctrl+Up` 或 `Ctrl+Down` 自動調整對所選文本的關注（代碼由匿名用戶提供）
- Loopback，多次運行img2img處理
- X/Y/Z 圖，一種繪製具有不同參數的 3 維圖像圖的方法
- 文本倒置
     - 擁有任意數量的嵌入，並為它們使用任何你喜歡的名稱
     - 使用每個標記具有不同數量向量的多個嵌入
     - 適用於半精度浮點數
     - 在 8GB 上訓練嵌入（還有 6GB 工作報告）
- 附加選項卡：
     - GFPGAN，修復人臉的神經網絡
     - CodeFormer，面部修復工具作為 GFPGAN 的替代品
     - RealESRGAN，神經網絡升級器
     - ESRGAN，具有大量第三方模型的神經網絡升級器
     - SwinIR 和 Swin2SR（[參見此處](https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/2092)），神經網絡升頻器
     - LDSR，潛在擴散超分辨率升級
- 調整寬高比選項
- 取樣方法選擇
     - 調整採樣器 eta 值（噪聲倍增器）
     - 更高級的噪音設置選項
- 隨時中斷處理
- 4GB 視頻卡支持（還有 2GB 工作報告）
- 正確的批次種子
- 實時提示令牌長度驗證
- 生成參數
      - 用於生成圖像的參數與該圖像一起保存
      - 在 PNG 的 PNG 塊中，在 JPEG 的 EXIF 中
      - 可將圖片拖拽至PNG信息標籤，恢復生成參數並自動複製到UI中
      - 可以在設置中禁用
      - 將圖像/文本參數拖放到提示框
- 讀取生成參數按鈕，將提示框中的參數加載到 UI
- 設置頁面
- 從 UI 運行任意 python 代碼（必須使用 `--allow-code` 運行才能啟用）
- 大多數 UI 元素的鼠標懸停提示
- 可以通過文本配置更改 UI 元素的默認值/混合/最大/步進值
- 平鋪支持，用於創建可以像紋理一樣平舖的圖像的複選框
- 進度條和實時圖像生成預覽
     - 可以使用單獨的神經網絡來生成幾乎沒有 VRAM 或計算要求的預覽
- 否定提示，一個額外的文本字段，允許您列出您不想在生成的圖像中看到的內容
- 樣式，一種保存部分提示並稍後通過下拉菜單輕鬆應用它們的方法
- 變體，一種生成相同圖像但有微小差異的方法
- 調整種子大小，一種生成相同圖像但分辨率略有不同的方法
- CLIP 詢問器，一個嘗試從圖像中猜測提示的按鈕
- Prompt Editing，一種改變prompt mid-generation的方法，說開始製作西瓜併中途切換到動漫女孩
- 批處理，使用 img2img 處理一組文件
- Img2img Alternative, reverse Euler method of cross attention control
- Highres Fix，一個方便的選項，可以一鍵生成高分辨率圖片而不會出現通常的失真
- 即時重新加載檢查點
- 檢查點合併，一個允許您將最多 3 個檢查點合併為一個的選項卡
- [Custom scripts](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Custom-Scripts) with many extensions from community
- [Composable-Diffusion](https://energy-based-model.github.io/Compositional-Visual-Generation-with-Composable-Diffusion-Models/), a way to use multiple prompts at once
     - separate prompts using uppercase `AND`
     - also supports weights for prompts: `a cat :1.2 AND a dog AND a penguin :2.2`
- 提示沒有令牌限制（原始穩定擴散讓您最多使用 75 個令牌）
- DeepDanbooru 集成，為動漫提示創建 danbooru 風格標籤
- [xformers](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Xformers)，選擇卡片的主要速度提升：（添加 `--xformers` 到命令行參數）
- 通過擴展：[歷史選項卡](https://github.com/yfszzx/stable-diffusion-webui-images-browser)：在 UI 中方便地查看、定向和刪除圖像
- 生成永久選項
- 培訓標籤
      - 超網絡和嵌入選項
      - 預處理圖像：使用 BLIP 或 deepdanbooru（用於動漫）裁剪、鏡像、自動標記
- 剪輯跳過
- 超級網絡
- Loras（與 Hypernetworks 相同但更漂亮）
- 一個單獨的 UI，您可以在其中選擇帶有預覽的嵌入、超網絡或 Loras 以添加到您的提示中
- 可以選擇從設置屏幕加載不同的 VAE
- 進度條中的預計完成時間
- API
- 支持 RunwayML 的專用[修復模型](https://github.com/runwayml/stable-diffusion#inpainting-with-stable-diffusion)
- 通過擴展：[Aesthetic Gradients](https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients)，一種通過使用剪輯圖像嵌入生成具有特定美感的圖像的方法（[https: //github.com/vicgalle/stable-diffusion-aesthetic-gradients](https://github.com/vicgalle/stable-diffusion-aesthetic-gradients))
- [穩定擴散 2.0](https://github.com/Stability-AI/stablediffusion) 支持 - 請參閱 [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#stable- diffusion-20) 的說明
- [Alt-Diffusion](https://arxiv.org/abs/2211.06679) 支持 - 參見 [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#alt-diffusion) 對於指示
- 現在沒有任何不良信件！
- 以安全張量格式加載檢查點
- 放寬分辨率限制：生成圖像的維度必須是 8 的倍數而不是 64
- 現在有了執照！
- 從設置屏幕重新排序 UI 中的元素

## Installation and Running
確保滿足所需的 [dependencies](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Dependencies) 並遵循適用於 [NVidia](https://github.com/AUTOMATIC1111) 的說明 /stable-diffusion-webui/wiki/Install-and-Run-on-NVidia-GPUs）（推薦）
和 [AMD](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and -在 AMD-GPU 上運行）GPU。

或者，使用在線服務（如 Google Colab）：

- [List of Online Services](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Online-Services)

### Automatic Installation on Windows
1. 安裝[Python 3.10.6](https://www.python.org/downloads/release/python-3106/)（較新版本的Python不支持torch），勾選“Add Python to PATH”。
2. 安裝 [git](https://git-scm.com/download/win)。
3. 下載 stable-diffusion-webui 存儲庫，例如通過運行 `git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git`。
4. 以普通非管理員用戶身份從 Windows 資源管理器運行 `webui-user.bat`。

### Automatic Installation on Linux
1.安裝依賴：
```bash
# Debian-based:
sudo apt install wget git python3 python3-venv
# Red Hat-based:
sudo dnf install wget git python3
# Arch-based:
sudo pacman -S wget git python3
```
2. 導航到您希望安裝 webui 的目錄並執行以下命令：
```bash
bash <(wget -qO- https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh)
```
3. 運行`webui.sh`。
4. 檢查 `webui-user.sh` 的選項。
### Installation on Apple Silicon

Find the instructions [here](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Installation-on-Apple-Silicon).

## Contributing
Here's how to add code to this repo: [Contributing](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Contributing)

## Documentation
The documentation was moved from this README over to the project's [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki).

## Credits
Licenses for borrowed code can be found in `Settings -> Licenses` screen, and also in `html/licenses.html` file.

- Stable Diffusion - https://github.com/CompVis/stable-diffusion, https://github.com/CompVis/taming-transformers
- k-diffusion - https://github.com/crowsonkb/k-diffusion.git
- GFPGAN - https://github.com/TencentARC/GFPGAN.git
- CodeFormer - https://github.com/sczhou/CodeFormer
- ESRGAN - https://github.com/xinntao/ESRGAN
- SwinIR - https://github.com/JingyunLiang/SwinIR
- Swin2SR - https://github.com/mv-lab/swin2sr
- LDSR - https://github.com/Hafiidz/latent-diffusion
- MiDaS - https://github.com/isl-org/MiDaS
- Ideas for optimizations - https://github.com/basujindal/stable-diffusion
- Cross Attention layer optimization - Doggettx - https://github.com/Doggettx/stable-diffusion, original idea for prompt editing.
- Cross Attention layer optimization - InvokeAI, lstein - https://github.com/invoke-ai/InvokeAI (originally http://github.com/lstein/stable-diffusion)
- Sub-quadratic Cross Attention layer optimization - Alex Birch (https://github.com/Birch-san/diffusers/pull/1), Amin Rezaei (https://github.com/AminRezaei0x443/memory-efficient-attention)
- Textual Inversion - Rinon Gal - https://github.com/rinongal/textual_inversion (we're not using his code, but we are using his ideas).
- Idea for SD upscale - https://github.com/jquesnelle/txt2imghd
- Noise generation for outpainting mk2 - https://github.com/parlance-zz/g-diffuser-bot
- CLIP interrogator idea and borrowing some code - https://github.com/pharmapsychotic/clip-interrogator
- Idea for Composable Diffusion - https://github.com/energy-based-model/Compositional-Visual-Generation-with-Composable-Diffusion-Models-PyTorch
- xformers - https://github.com/facebookresearch/xformers
- DeepDanbooru - interrogator for anime diffusers https://github.com/KichangKim/DeepDanbooru
- Sampling in float32 precision from a float16 UNet - marunine for the idea, Birch-san for the example Diffusers implementation (https://github.com/Birch-san/diffusers-play/tree/92feee6)
- Instruct pix2pix - Tim Brooks (star), Aleksander Holynski (star), Alexei A. Efros (no star) - https://github.com/timothybrooks/instruct-pix2pix
- Security advice - RyotaK
- UniPC sampler - Wenliang Zhao - https://github.com/wl-zhao/UniPC
- Initial Gradio script - posted on 4chan by an Anonymous user. Thank you Anonymous user.
- (You)
