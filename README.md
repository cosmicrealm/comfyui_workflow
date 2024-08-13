# comfyui_workflows

- 基础工作流
- 工具
- 高级工作流
- comfyui 插件说明

tips: can be directly dragged into comfyui

### 基础工作流

- sd15 basic, 官方示例
  <img src="workflows/basic/sd15_basic.png">
- sdxl basic 1
  <img src="workflows/basic/sdxl_basic_001.png">
- sdxl basic 2
  <img src="workflows/basic/sdxl_basic_002.png">
- svd basic
  <img src="workflows/basic/svd_basic.png">
  ![svd example](resource/basic/svd_00001.gif)
  <!-- <video width="320" height="240" controls>
    <source src="resource/basic/svd_00001.mp4" type="video/mp4">
  </video> -->
<!-- - sd cascade
  <img src="workflows/basic/sd_cascade_basic.png"> -->
- sd3 medium
  <img src="workflows/basic/sd3_medium_basic.png">

### 工具
- reactor, 换脸简单示例
   <img src="workflows/tools/reactor_basic.png">
- dwpose keypoints detect
   <img src="workflows/tools/dwpose.png">
- depth map
- yolo 
  - yolo face detect
    <img src="workflows/tools/yolo_face_detect.png">
  - yolo face seg [model ref from](https://huggingface.co/jags/yolov8_model_segmentation-set/tree/main)，选择不同的模型得到不同区域，适用于人脸，人体等
    <img src="workflows/tools/yolo_face_seg.png">
  - yolo worlds
  - yolo hands detect
- super resolution
  - basic sr model with img
    <img src="workflows/tools/super_resolution_basic_1.png">
- face landmarks seg
- clothes seg
- background remove
  - BRIA 1.4（could deal with video）
  <img src="workflows/tools/background_remove_BRIA.png">
- inpaint model, inpaint mouth
  <img src="workflows/tools/inpaint_mouth.png">


### 高级工作流
- 接入sd3 medium 的中文版肖像大师，ref from [zho-zho-zho](https://github.com/ZHO-ZHO-ZHO/ComfyUI-Workflows-ZHO)
  <img src="workflows/advanced/portrait_zh_sd3_medium_blue.png">
- style align 风格一致性生成 [style align](https://github.com/brianfitzgerald/style_aligned_comfy)  [教学](https://www.youtube.com/watch?v=itBiBOYWHF8)
  - 在一个batch内, 可以生成朝向一致且风格一致的结果
  <img src="workflows/advanced/style_align_in_batch.png">
- 人脸修复 适用 facedetailer 模块进行重采样，注意此处会修复过大，失真可能严重，谨慎使用
  - 模型生成的人脸
    <img src="workflows/advanced/face_detailer_with_sd_gened.png">
  - 输入人脸
    <img src="workflows/advanced/face_detailer_with_sd.png">
- ipadapter 多元素组合，全图作用
  <img src="workflows/advanced/ipadapter_combine_multi_items.png">
- ipadapter faceid, sd15 模型, 注意 prompt 不能过于复杂
  <img src="workflows/advanced/ipadapter_faceid_01.png">
- ipadapter 使用 mask 对图片进行换衣，需要使用 inpaint 模型
  <img src="workflows/advanced/ipadapter_image_change_cloth_with_mask.png">
- 自动视频换装，使用 ipadapter + animatediff 进行视频换装
  - 此处计算比较耗时，酌情运行，可以降低图像分辨率，主要思想是利用 ipadapter 的 attn mask 功能对视频进行局部重绘
  - 需要注意不同 base 模型对视频效果影响挺大，这里使用的是 [麦橘v7](https://civitai.com/models/43331/majicmix-realistic)
  <img src="workflows/advanced/auto_clothes_with_attn_masked_ipadapter_and_animatediff.png">
  <img src="resource/advanced/clothes.jpg" width="384" height="512">
  <img src="resource/advanced/auto_clothes_combine.gif" width="540" height="960" alt="auto clothes example">
- InstantID 和 ipadapter 结合，生成特定风格的任务，感谢大佬 [cubiq](https://github.com/cubiq/ComfyUI_InstantID/blob/main/examples/InstantID_IPAdapter.json)
  <img src="workflows/advanced/instantID_with_ipadapter.png">
- InstantID 和 controlnet depth 结合，生成指定动作的任务形象
  <img src="workflows/advanced/instantID_with_depth.png">
- sdxl + ipadapter, 强风格转换
  <img src="workflows/advanced/ipadapter_strong_style_transfer.png">
- easyanimate，图像到视频或者 文本到视频, ref from [easyanimate](https://github.com/aigc-apps/EasyAnimate/blob/main/comfyui/README.md)
  <img src="workflows\advanced\easyanimate.png">
  <img src="resource/advanced/easyanimate.gif" width="960" height="576" alt="easyanimatediff example">

### 常见 prompt

- positive
  -  high quality, and the view is very clear. High quality, masterpiece, best quality, highres, ultra-detailed, fantastic.
  -  
- negative
  -  strange motion trajectory, a poor composition and deformed video, low resolution, duplicate and ugly, strange body structure, long and strange neck, bad teeth, bad eyes, bad limbs, bad hands, rotating camera, blurry camera, shaking camera. Deformation, low-resolution, blurry, ugly, distortion.
  -  

### comfyui 插件说明

- https://github.com/ltdrdata/ComfyUI-Impact-Pack
- https://github.com/WASasquatch/was-node-suite-comfyui
- https://github.com/rgthree/rgthree-comfy
- https://github.com/pythongosssss/ComfyUI-Custom-Scripts
- https://github.com/Suzie1/ComfyUI_Comfyroll_CustomNodes
- 