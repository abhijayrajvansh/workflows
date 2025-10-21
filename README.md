# ComfyUI Workflow Catalog

This catalog summarizes every workflow in the repository. Workflows are split into safe-for-work (SFW) and explicit (NSFW) groups, while still noting the generation use case, primary model stacks, and one-line intent.

## SFW Workflows

Workflows that are not flagged for explicit content. Use the `Use Case` column to quickly locate text-to-video, image editing, dataset prep, and other categories.

| Workflow | Use Case | Summary | Models |
| --- | --- | --- | --- |
| `ft-tts/ft-tts-comfy.json` | Audio & Speech | FastTrack TTS graph generating narration-ready audio from text prompts. | TTS |
| `FP8/3.2_Dataset_Generation_NanoBanana.json` | Dataset & Finetuning | NanoBanana dataset generator that batches Wan renders with caption helpers for finetuning. | FP8, NANO, WAN |
| `FP8/3.3_Data_Preparation_Workflow.json` | Dataset & Finetuning | FP8 data prep pipeline that cleans and structures image sets for training. | FP8 |
| `FP8/4.2_Data_Prep_Finetune_Workflow.json` | Dataset & Finetuning | End-to-end FP8 finetune prep combining captioning, tagging, and packaging routines. | FP8 |
| `FP8/7.5_Wan22_Image_Gen_FP8.json` | Dataset & Finetuning | Wan 2.2 FP8 image sweep that creates raw datasets for downstream video finetunes. | FP8, HUNYUAN, WAN |
| `FP8/7.5_Wan22_Image_Gen_FP8_Joy_Caption.json` | Dataset & Finetuning | Wan 2.2 FP8 dataset builder enriched with Joy Caption metadata. | FLORENCE, FP8, HUNYUAN, JOY, WAN |
| `FP8/7.5_Wan22_Image_Gen_FP8_SimpleLLMCaption.json` | Dataset & Finetuning | Wan 2.2 FP8 dataset builder using lightweight LLM captions. | FP8, HUNYUAN, WAN |
| `FP8/Archived Lessons/3 - Dataset Prep.json` | Dataset & Finetuning | Archived FP8 lesson documenting dataset preparation fundamentals. | FP8 |
| `FP8/Archived Lessons/3.3_Dataset_Prep_Joy_Caption.json` | Dataset & Finetuning | Archived FP8 Joy Caption walkthrough for dataset tagging. | FP8, JOY |
| `FP8/Archived Lessons/4.2_Data_Prep_Finetune_Workflow.json` | Dataset & Finetuning | Archived FP8 finetune prep flow kept as a reference. | ACE, FP8, JOY |
| `FP8/Archived Lessons/5 - Lora XY Plot (FP8) Updated.json` | Dataset & Finetuning | Archived FP8 LoRA XY plot tool for evaluating finetune sweeps. | FLUX, FP8, GGUF |
| `Flux Ultrea Realistic Workflow/ultrareal-finetune workflow (runpod).json` | Dataset & Finetuning | Ultrareal Flux finetune workflow tailored for RunPod deployments. | FLUX, GGUF |
| `GGUF/3.2_PixelaiLabs_Dataset_Generation_NanoBanana.json` | Dataset & Finetuning | GGUF NanoBanana dataset generator for quantized Wan runs. | GGUF, NANO, WAN |
| `GGUF/3.3_Data_Preparation_Workflow.json` | Dataset & Finetuning | GGUF data preparation stack cleaning assets ahead of training. | GGUF |
| `GGUF/4.2_Data_Prep_Finetune_Workflow.json` | Dataset & Finetuning | GGUF finetune prep template orchestrating tagging and packaging. | GGUF |
| `GGUF/7.5_Wan22_Image_Gen_GGUF.json` | Dataset & Finetuning | Wan 2.2 GGUF dataset generator producing stills for video finetune. | GGUF, HUNYUAN, WAN |
| `GGUF/7.5_Wan22_Image_Gen_GGUF_Joy_Caption.json` | Dataset & Finetuning | Wan 2.2 GGUF dataset generator with Joy Caption annotation. | FLORENCE, GGUF, HUNYUAN, JOY, WAN |
| `GGUF/7.5_Wan22_Image_Gen_GGUF_SimpleLLMCAption.json` | Dataset & Finetuning | Wan 2.2 GGUF dataset generator using lightweight LLM captions. | GGUF, HUNYUAN, WAN |
| `GGUF/Archived Lessons/3 - Dataset Prep.json` | Dataset & Finetuning | Archived GGUF dataset prep primer retained for study. | GGUF |
| `GGUF/Archived Lessons/3.3_PixelaiLabs_Dataset_Prep_Joy_Caption.json` | Dataset & Finetuning | Archived GGUF Joy Caption dataset prep walkthrough. | GGUF, JOY |
| `GGUF/Archived Lessons/4.2_Data_Prep_Finetune_Workflow.json` | Dataset & Finetuning | Archived GGUF finetuning prep pipeline for reference. | ACE, GGUF, JOY |
| `GGUF/Archived Lessons/5 - Lora XY Plot (GGUF) Updated.json` | Dataset & Finetuning | Archived GGUF LoRA XY plot utility for comparing checkpoint sweeps. | FLUX, GGUF |
| `HunyuanVideo/hunyuan video lora.json` | Dataset & Finetuning | Hunyuan LoRA authoring graph that precomputes latents and scheduling for video finetunes. | FLUX, HUNYUAN |
| `Wan 2.2 Instagirl/wan2.2-instagirl (1).json` | Dataset & Finetuning | Wan 2.2 Instagirl preset for generating consistent fashion datasets. | GGUF, HUNYUAN, WAN |
| `Qwen Image Edit/qwen-edit.json` | Image Editing (Qwen) | Qwen-based instruction editor that applies natural-language tweaks to uploaded images. | FLUX, QWEN |
| `FP8/5.3_Instagram Ready Workflow Florence 2(Flux Batch FP8).json` | Image Editing (SDXL) | Batch SDXL Florence 2 enhancer that polishes Flux outputs for social-ready deliveries. | ACE, FLORENCE, FLUX, FP8, SDXL |
| `FP8/5.3_Instagram Ready Workflow Joy Caption 2 (Flux Batch FP8).json` | Image Editing (SDXL) | Batch Joy Caption 2 pipeline blending SDXL clean-up with automated captions. | ACE, FLORENCE, FLUX, FP8, JOY, SDXL |
| `FP8/5.3_Instagram Ready Workflow Simple LLM Caption (Flux Batch FP8).json` | Image Editing (SDXL) | Batch SDXL post-process with lightweight LLM captions for each render. | ACE, FLUX, FP8, SDXL |
| `FP8/5.4_Flux Skin Enhancer V2 (SDXL).json` | Image Editing (SDXL) | SDXL-based skin retouch preset for portrait refinement. | ACE, FLUX, FP8, SDXL |
| `GGUF/5.3_Instagram Ready Workflow Florence 2 (Flux Batch GGUF).json` | Image Editing (SDXL) | GGUF Florence 2 batch polisher that tidies Flux galleries in one pass. | ACE, FLORENCE, FLUX, GGUF, SDXL |
| `GGUF/5.3_Instagram Ready Workflow Joy Caption 2 (Flux Batch GGUF).json` | Image Editing (SDXL) | GGUF Joy Caption 2 batch enhancer combining SDXL cleanup and caption automation. | ACE, FLORENCE, FLUX, GGUF, JOY, SDXL |
| `GGUF/5.3_Instagram Ready Workflow Simple LLM Caption (Flux Batch GGUF).json` | Image Editing (SDXL) | GGUF batch finisher pairing SDXL clean-up with light captioning. | ACE, FLUX, GGUF, SDXL |
| `GGUF/5.4_Flux Skin Enhancer V2 (SDXL).json` | Image Editing (SDXL) | GGUF SDXL skin smoothing preset for polished portraits. | ACE, FLUX, GGUF, SDXL |
| `Pulid Instantid SDXL Sticker/sdxl-pulid-sticker-final-single.ai.json` | Image Editing (SDXL) | Pulid InstantID sticker builder that feeds SDXL for bold decal exports. | ACE, INSTANTID, PULID, SDXL |
| `SDXL/sdxl-turbo-face-swap.json` | Image Editing (SDXL) | SDXL Turbo face swap rig for rapid identity transfers within portraits. | ACE, SDXL |
| `flux-shou-xin-sketch-style-pulid/flux-shou-xin-sketch-style-pulid.json` | Image Editing (SDXL) | Sketch-to-style Pulid workflow combining Flux control with SDXL finishing touches. | ACE, FLORENCE, FLUX, PULID, SDXL |
| `Ace plus plus/ace++ reference with target.json` | Image Generation & Editing (Flux/Ace++) | Ace++ reference-to-target alignment kit for capturing identity embeddings before swaps. | ACE, FLUX |
| `FP8/3.1_FaceGen_V2_FP8.json` | Image Generation & Editing (Flux/Ace++) | FP8 face generator mixing Ace++ reference control for detailed portrait synthesis. | ACE, FLUX, FP8 |
| `FP8/3.4_Ace++ Face Swap (FP8).json` | Image Generation & Editing (Flux/Ace++) | Ace++ face swap routine tuned for FP8 checkpoints to transfer identities cleanly. | ACE, FLUX, FP8 |
| `FP8/4.2_Single_Image_Generator_Finetune.json` | Image Generation & Editing (Flux/Ace++) | Finetuned FP8 single-image generator that bootstraps new looks from text prompts. | ACE, FLUX, FP8 |
| `FP8/5.1_InstaReady_V2_FluxKrea_(JoyCaption2)FP8.json` | Image Generation & Editing (Flux/Ace++) | Single-shot InstaReady V2 Joy Caption flow framing Flux Krea renders for social media. | ACE, FLORENCE, FLUX, FP8, JOY, KREA, WAN |
| `FP8/5.1_InstaReady_V2_FluxKrea_FP8_SimpleLLMCaption.json` | Image Generation & Editing (Flux/Ace++) | Single-shot Flux Krea workflow with lightweight LLM captioning baked in. | ACE, FLUX, FP8, KREA, WAN |
| `FP8/5.2_Instagram Ready Workflow Florence 2 (Single Image FP8).json` | Image Generation & Editing (Flux/Ace++) | Single-image Insta-ready variant using Florence 2 for descriptive tagging. | ACE, FLORENCE, FLUX, FP8 |
| `FP8/5.2_Instagram Ready Workflow Joy Caption 2 (Single Image FP8).json` | Image Generation & Editing (Flux/Ace++) | Single-image Joy Caption 2 pipeline layering captions over Flux shots. | ACE, FLORENCE, FLUX, FP8, JOY |
| `FP8/5.2_Instagram Ready Workflow Simple LLM Caption (Single Image FP8).json` | Image Generation & Editing (Flux/Ace++) | Single-image Insta workflow using simple LLM captions on Flux renders. | ACE, FLUX, FP8 |
| `FP8/5.4_Flux Skin Enhancer V2 (SD1.5).json` | Image Generation & Editing (Flux/Ace++) | Flux skin enhancer V2 running on SD1.5 for gentle complexion cleanup. | ACE, FLUX, FP8 |
| `FP8/Archived Lessons/1 - Face Gen (FP8).json` | Image Generation & Editing (Flux/Ace++) | Archived lesson demonstrating the baseline FP8 face generation setup. | ACE, FLUX, FP8 |
| `FP8/Archived Lessons/1 - FaceGen Upscaler (FP8).json` | Image Generation & Editing (Flux/Ace++) | Archived FP8 face generator paired with upscaling for sharper portraits. | ACE, FLUX, FP8 |
| `FP8/Archived Lessons/2 - Inpainting (FP8).json` | Image Generation & Editing (Flux/Ace++) | Archived FP8 inpainting lesson for targeted region edits. | FLUX, FP8 |
| `Flux Fill FLux Redux Swap Clothes/swap clothes workflow.json` | Image Generation & Editing (Flux/Ace++) | Flux Redux clothing swap that repaints outfits on a supplied subject. | FLUX |
| `Flux Kontext/flux kontext dev with upscaler and face detailer.json` | Image Generation & Editing (Flux/Ace++) | Flux Kontext dev build combining face detailing and upscaling in one graph. | ACE, FLUX, GGUF |
| `Flux Kontext/flux kontext pro, max.json` | Image Generation & Editing (Flux/Ace++) | Flux Kontext pro configuration with max-quality refinement stages. | ACE, FLUX, GGUF |
| `GGUF/3.1_PixelaiLabs_FaceGen_V2_GGUF.json` | Image Generation & Editing (Flux/Ace++) | GGUF PixelaiLabs FaceGen V2 for identity-consistent portrait synthesis. | ACE, FLUX, GGUF |
| `GGUF/3.4_Ace++ Face Swap (GGUF).json` | Image Generation & Editing (Flux/Ace++) | GGUF Ace++ face swap pipeline for local quantized checkpoints. | ACE, FLUX, GGUF |
| `GGUF/4.2_Single_Image_Generator_Finetune.json` | Image Generation & Editing (Flux/Ace++) | GGUF finetuned single-image generator for bespoke looks. | ACE, FLUX, GGUF |
| `GGUF/5.1_InstaReady_V2_FluxKrea_JoyCaption(GGUF).json` | Image Generation & Editing (Flux/Ace++) | GGUF InstaReady Joy Caption single-shot setup for social-ready exports. | ACE, FLORENCE, FLUX, GGUF, JOY, KREA, WAN |
| `GGUF/5.1_InstaReady_V2_FluxKrea_SimpleLLMCaption(GGUF).json` | Image Generation & Editing (Flux/Ace++) | GGUF InstaReady variant with lightweight LLM captioning for quick posts. | ACE, FLUX, GGUF, KREA, WAN |
| `GGUF/5.2_ Instagram Ready Workflow Joy Caption 2 (Single Image GGUF).json` | Image Generation & Editing (Flux/Ace++) | GGUF single-image Joy Caption 2 workflow for captioned portraits. | ACE, FLORENCE, FLUX, GGUF, JOY |
| `GGUF/5.2_Instagram Ready Workflow Florence 2(Single Image GGUF).json` | Image Generation & Editing (Flux/Ace++) | GGUF single-image Florence 2 pipeline layering descriptive tags. | ACE, FLORENCE, FLUX, GGUF |
| `GGUF/5.2_Instagram Ready Workflow Simple LLM Caption (Single Image GGUF).json` | Image Generation & Editing (Flux/Ace++) | GGUF single-image Insta-ready run using simple LLM captions. | ACE, FLUX, GGUF |
| `GGUF/5.4_Flux Skin Enhancer V2 (SD1.5).json` | Image Generation & Editing (Flux/Ace++) | GGUF SD1.5-based skin enhancer for smoothing complexion. | ACE, FLUX, GGUF |
| `GGUF/Archived Lessons/1 - Face Gen (GGUF).json` | Image Generation & Editing (Flux/Ace++) | Archived GGUF lesson covering the base face generation stack. | ACE, FLUX, GGUF |
| `GGUF/Archived Lessons/1 - FaceGen Upscaler (GGUF).json` | Image Generation & Editing (Flux/Ace++) | Archived GGUF face generator plus upscaler combo for clean detail. | ACE, FLUX, GGUF |
| `GGUF/Archived Lessons/2 - Inpainting (GGUF).json` | Image Generation & Editing (Flux/Ace++) | Archived GGUF inpainting lesson focused on localized edits. | FLUX, GGUF |
| `GGUF/Archived Lessons/4 - Kontext Face_Swapper_V2 (GGUF).json` | Image Generation & Editing (Flux/Ace++) | Archived GGUF Kontext face swapper V2 for dependable identity transfers. | ACE, FLUX, GGUF |
| `ghibli/ghibli-flux-diffusion.json` | Image Generation & Editing (Flux/Ace++) | Ghibli-styled Flux diffusion setup mixing Pulid guidance for painterly looks. | ACE, FLORENCE, FLUX, GHIBLI, PULID |
| `ghibli/ghibli-gpt-lora.json` | Image Generation & Editing (Flux/Ace++) | Ghibli GPT LoRA workflow combining FlowEdit controls for stylized transfers. | FLUX, GGUF, GHIBLI |
| `hyperlora/hyperlora - instantid + controlnet + facedetailer.json` | Image Generation & Editing (Flux/Ace++) | HyperLoRA stack with InstantID, ControlNet, and face detailer for guided portraits. | ACE, HYPERLORA, INSTANTID |
| `pulid face swap/flux face swap individual faces.json` | Image Generation & Editing (Flux/Ace++) | Pulid-enabled Flux face swap for handling multiple individual identities. | ACE, FLUX, GGUF, PULID |
| `FP8/7.1_Image to video Wan 2.1 (GGUF).json` | Image-to-Video | Wan 2.1 GGUF image-to-video template that animates a single frame with Wan motion priors. | ACE, FP8, GGUF, WAN |
| `FP8/7.1_Image to video Wan 2.1 (No Teacache Max Quality GGUF).json` | Image-to-Video | Quality-first variant of the Wan 2.1 image-to-video graph with tea-cache disabled. | ACE, FP8, GGUF, WAN |
| `FP8/7.6_Wan22_I2V_Lightning_FP8.json` | Image-to-Video | Wan 2.2 Lightning image-to-video flow tuned for fast still-to-motion conversion. | FP8, WAN |
| `FP8/7.6_Wan22_I2V_Lightning_FP8_(RunPod).json` | Image-to-Video | RunPod-ready Wan 2.2 Lightning I2V preset with environment-safe defaults. | FP8, WAN |
| `Framepack/Flux - First and Last frame.json` | Image-to-Video | Flux-based Framepack helper that generates and stitches keyframes into a starter video. | FLORENCE, FLUX, FRAMEPACK, WAN |
| `Framepack/framepack first and last frame.json` | Image-to-Video | Alternate Framepack rig for blending generated keyframes and exporting the final clip package. | FRAMEPACK |
| `GGUF/7.1_Image to video Wan 2.1 (GGUF).json` | Image-to-Video | GGUF-native Wan 2.1 image-to-video base graph for local inference rigs. | ACE, GGUF, WAN |
| `GGUF/7.1_Image to video Wan 2.1 (No Teacache Max Quality GGUF).json` | Image-to-Video | GGUF image-to-video preset prioritizing quality by skipping tea-cache acceleration. | ACE, GGUF, WAN |
| `GGUF/7.6_Wan22_I2V_Lightning_GGUF.json` | Image-to-Video | Wan 2.2 Lightning image-to-video build compiled for GGUF pipelines. | GGUF, WAN |
| `LTXVideo/LTXV-LiminalSpace-Image-To-Video.json` | Image-to-Video | LTXVideo liminal-space preset that turns concept art into slow camera passes. | ACE, LTX |
| `Wan fusion X/Wan 2.1 fusionX image to video.json` | Image-to-Video | FusionX branch that grows Wan 2.1 stills into cinematic motion clips. | WAN |
| `Bulk Generate Flux Dev/workflow/flux-dev bulk with prompt file.json` | Text-to-Image & Bulk Renders | Flux Dev bulk renderer that reads prompt lists and outputs batched image sets. | FLUX |
| `FP8/7.2_Wan_Video_21_InfiniteTalk.json` | Text-to-Video | Wan 2.1 InfiniteTalk text-to-video setup that sequences multi-speaker dialogue with automated lip-sync cues. | FP8, WAN |
| `FP8/Archived Lessons/10 -PixelaiLabs_WanVideo_MultiTalk_GGUF_RunPod.json` | Text-to-Video | Archived RunPod variant of the InfiniteTalk Wan text-to-video workflow with GGUF acceleration settings baked in. | FP8, GGUF, WAN |
| `GGUF/7.2_Wan_Video_21_InfiniteTalk.json` | Text-to-Video | GGUF-tuned InfiniteTalk graph for Wan 2.1 that generates conversational videos straight from script prompts. | GGUF, WAN |
| `GGUF/Archived Lessons/10 - WanVideo_MultiTalk_GGUF_RunPod.json` | Text-to-Video | Legacy InfiniteTalk pipeline for Wan video on RunPod, kept for reference with older GGUF checkpoints. | GGUF, WAN |
| `HunyuanVideo/hunyuanvideo_text_to_video.json` | Text-to-Video | Native HunyuanVideo text-to-video template covering model, VAE, sampler, and prompt scheduling defaults. | HUNYUAN |
| `LTXVideo/ltxv 0.9.6 distilled.json` | Text-to-Video | Distilled LTXVideo 0.9.6 text-to-video rig with guide tracks and CLIP conditioning for consistent scenes. | LTX |
| `Phantom/phantom_wan_workflow.json` | Text-to-Video | Wan Phantom edition text-to-video stack that layers tea-cache management and phantom embeddings for stylized motion. | PHANTOM, WAN |
| `Wan fusion X/Wan_FusionX_t2v_native_WF_V2.json` | Text-to-Video | FusionX V2 text-to-video flow using Wan 2.1 with native sampler presets for cinematic camera moves. | HUNYUAN, WAN |
| `FP8/7.3_Wan 2.1 Vace Fast GGUF.json` | Video-to-Video | Wan VACE fast video restyle blending depth and canny cues for quick conversions. | ACE, FP8, GGUF, VACE, WAN |
| `FP8/7.4_Wan 2.1 Phantom Fast (GGUF).json` | Video-to-Video | Wan Phantom fast variant applying tea-cache-managed restyling with RIFE smoothing. | FP8, GGUF, PHANTOM, WAN |
| `GGUF/7.3_Wan 2.1 Vace Fast GGUF.json` | Video-to-Video | Pure GGUF Wan VACE fast pipeline for accelerated video rehousing. | ACE, GGUF, VACE, WAN |
| `GGUF/7.4_Wan 2.1 Phantom Fast (GGUF).json` | Video-to-Video | GGUF Wan Phantom fast restyler with optional interpolation for smoother outputs. | GGUF, PHANTOM, WAN |
| `HunyuanVideo/hunyuanvideo_video_to_video.json` | Video-to-Video | Hunyuan video-to-video stylizer that transfers prompts onto source footage while echoing motion. | HUNYUAN |

## NSFW Workflows

Workflows intended for adult or explicit imagery. Review model requirements carefully before running them.

| Workflow | Use Case | Summary | Models |
| --- | --- | --- | --- |
| `FP8/8.1_PixelaiLabs_NSFW_V1_FP8.json` | Image Generation & Editing (Flux/Ace++) | FP8 PixelaiLabs NSFW preset for mature-themed portrait generation. | ACE, FLUX, FP8 |
| `GGUF/8.1_PixelaiLabs_NSFW_V1_GGUF.json` | Image Generation & Editing (Flux/Ace++) | GGUF PixelaiLabs NSFW preset targeting adult-oriented imagery. | ACE, FLUX, GGUF |
| `GGUF/Archived Lessons/11 - PixelaiLabs_NSFW_Kontext_V2_GGUF.json` | Image Generation & Editing (Flux/Ace++) | Archived GGUF Kontext V2 NSFW workflow maintained for reference. | ACE, FLORENCE, FLUX, GGUF, JOY |
| `NSFW/workflow-take-off-clothes-wan22-i2v-a799LjeO0VdL10vY48UG-bbs_revenger-openart.ai.json` | Image-to-Video | Explicit Wan 2.2 image-to-video workflow that removes clothing for adult-oriented renders. | WAN |
