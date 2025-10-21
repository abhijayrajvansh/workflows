# ComfyUI Workflow Catalog

This catalog summarizes every workflow in the repository, grouped by generation task. Each entry links to the JSON graph, highlights the intended use, the primary model stack, and indicates whether it is flagged for NSFW content.

## Text-to-Video

Prompt-driven video generation pipelines that start from text and render motion clips.

| Workflow | Summary | Models | NSFW |
| --- | --- | --- | --- |
| `FP8/7.2_Wan_Video_21_InfiniteTalk.json` | Wan 2.1 InfiniteTalk text-to-video setup that sequences multi-speaker dialogue with automated lip-sync cues. | FP8, WAN | no |
| `FP8/Archived Lessons/10 -PixelaiLabs_WanVideo_MultiTalk_GGUF_RunPod.json` | Archived RunPod variant of the InfiniteTalk Wan text-to-video workflow with GGUF acceleration settings baked in. | FP8, GGUF, WAN | no |
| `GGUF/7.2_Wan_Video_21_InfiniteTalk.json` | GGUF-tuned InfiniteTalk graph for Wan 2.1 that generates conversational videos straight from script prompts. | GGUF, WAN | no |
| `GGUF/Archived Lessons/10 - WanVideo_MultiTalk_GGUF_RunPod.json` | Legacy InfiniteTalk pipeline for Wan video on RunPod, kept for reference with older GGUF checkpoints. | GGUF, WAN | no |
| `HunyuanVideo/hunyuanvideo_text_to_video.json` | Native HunyuanVideo text-to-video template covering model, VAE, sampler, and prompt scheduling defaults. | HUNYUAN | no |
| `Phantom/phantom_wan_workflow.json` | Wan Phantom edition text-to-video stack that layers tea-cache management and phantom embeddings for stylized motion. | PHANTOM, WAN | no |
| `Wan fusion X/Wan_FusionX_t2v_native_WF_V2.json` | FusionX V2 text-to-video flow using Wan 2.1 with native sampler presets for cinematic camera moves. | HUNYUAN, WAN | no |
| `LTXVideo/ltxv 0.9.6 distilled.json` | Distilled LTXVideo 0.9.6 text-to-video rig with guide tracks and CLIP conditioning for consistent scenes. | LTX | no |

## Image-to-Video

Pipelines that animate reference images or keyframes into full motion clips.

| Workflow | Summary | Models | NSFW |
| --- | --- | --- | --- |
| `FP8/7.1_Image to video Wan 2.1 (GGUF).json` | Wan 2.1 GGUF image-to-video template that animates a single frame with Wan motion priors. | ACE, FP8, GGUF, WAN | no |
| `FP8/7.1_Image to video Wan 2.1 (No Teacache Max Quality GGUF).json` | Quality-first variant of the Wan 2.1 image-to-video graph with tea-cache disabled. | ACE, FP8, GGUF, WAN | no |
| `FP8/7.6_Wan22_I2V_Lightning_FP8.json` | Wan 2.2 Lightning image-to-video flow tuned for fast still-to-motion conversion. | FP8, WAN | no |
| `FP8/7.6_Wan22_I2V_Lightning_FP8_(RunPod).json` | RunPod-ready Wan 2.2 Lightning I2V preset with environment-safe defaults. | FP8, WAN | no |
| `GGUF/7.1_Image to video Wan 2.1 (GGUF).json` | GGUF-native Wan 2.1 image-to-video base graph for local inference rigs. | ACE, GGUF, WAN | no |
| `GGUF/7.1_Image to video Wan 2.1 (No Teacache Max Quality GGUF).json` | GGUF image-to-video preset prioritizing quality by skipping tea-cache acceleration. | ACE, GGUF, WAN | no |
| `GGUF/7.6_Wan22_I2V_Lightning_GGUF.json` | Wan 2.2 Lightning image-to-video build compiled for GGUF pipelines. | GGUF, WAN | no |
| `NSFW/workflow-take-off-clothes-wan22-i2v-a799LjeO0VdL10vY48UG-bbs_revenger-openart.ai.json` | Explicit Wan 2.2 image-to-video workflow that removes clothing for adult-oriented renders. | WAN | yes |
| `Wan fusion X/Wan 2.1 fusionX image to video.json` | FusionX branch that grows Wan 2.1 stills into cinematic motion clips. | WAN | no |
| `Framepack/Flux - First and Last frame.json` | Flux-based Framepack helper that generates and stitches keyframes into a starter video. | FLORENCE, FLUX, FRAMEPACK, WAN | no |
| `Framepack/framepack first and last frame.json` | Alternate Framepack rig for blending generated keyframes and exporting the final clip package. | FRAMEPACK | no |
| `LTXVideo/LTXV-LiminalSpace-Image-To-Video.json` | LTXVideo liminal-space preset that turns concept art into slow camera passes. | ACE, LTX | no |

## Video-to-Video

Workflows that accept existing video and restyle or enhance it while preserving motion.

| Workflow | Summary | Models | NSFW |
| --- | --- | --- | --- |
| `HunyuanVideo/hunyuanvideo_video_to_video.json` | Hunyuan video-to-video stylizer that transfers prompts onto source footage while echoing motion. | HUNYUAN | no |
| `FP8/7.3_Wan 2.1 Vace Fast GGUF.json` | Wan VACE fast video restyle blending depth and canny cues for quick conversions. | ACE, FP8, GGUF, VACE, WAN | no |
| `FP8/7.4_Wan 2.1 Phantom Fast (GGUF).json` | Wan Phantom fast variant applying tea-cache-managed restyling with RIFE smoothing. | FP8, GGUF, PHANTOM, WAN | no |
| `GGUF/7.3_Wan 2.1 Vace Fast GGUF.json` | Pure GGUF Wan VACE fast pipeline for accelerated video rehousing. | ACE, GGUF, VACE, WAN | no |
| `GGUF/7.4_Wan 2.1 Phantom Fast (GGUF).json` | GGUF Wan Phantom fast restyler with optional interpolation for smoother outputs. | GGUF, PHANTOM, WAN | no |

## Image Editing (Qwen)

Instruction-driven editing flows powered by the Qwen image editing model.

| Workflow | Summary | Models | NSFW |
| --- | --- | --- | --- |
| `Qwen Image Edit/qwen-edit.json` | Qwen-based instruction editor that applies natural-language tweaks to uploaded images. | FLUX, QWEN | no |

## Image Editing (SDXL)

SDXL-powered enhancement and editing stacks for post-processing Flux or Wan imagery.

| Workflow | Summary | Models | NSFW |
| --- | --- | --- | --- |
| `FP8/5.3_Instagram Ready Workflow Florence 2(Flux Batch FP8).json` | Batch SDXL Florence 2 enhancer that polishes Flux outputs for social-ready deliveries. | ACE, FLORENCE, FLUX, FP8, SDXL | no |
| `FP8/5.3_Instagram Ready Workflow Joy Caption 2 (Flux Batch FP8).json` | Batch Joy Caption 2 pipeline blending SDXL clean-up with automated captions. | ACE, FLORENCE, FLUX, FP8, JOY, SDXL | no |
| `FP8/5.3_Instagram Ready Workflow Simple LLM Caption (Flux Batch FP8).json` | Batch SDXL post-process with lightweight LLM captions for each render. | ACE, FLUX, FP8, SDXL | no |
| `FP8/5.4_Flux Skin Enhancer V2 (SDXL).json` | SDXL-based skin retouch preset for portrait refinement. | ACE, FLUX, FP8, SDXL | no |
| `GGUF/5.3_Instagram Ready Workflow Florence 2 (Flux Batch GGUF).json` | GGUF Florence 2 batch polisher that tidies Flux galleries in one pass. | ACE, FLORENCE, FLUX, GGUF, SDXL | no |
| `GGUF/5.3_Instagram Ready Workflow Joy Caption 2 (Flux Batch GGUF).json` | GGUF Joy Caption 2 batch enhancer combining SDXL cleanup and caption automation. | ACE, FLORENCE, FLUX, GGUF, JOY, SDXL | no |
| `GGUF/5.3_Instagram Ready Workflow Simple LLM Caption (Flux Batch GGUF).json` | GGUF batch finisher pairing SDXL clean-up with light captioning. | ACE, FLUX, GGUF, SDXL | no |
| `GGUF/5.4_Flux Skin Enhancer V2 (SDXL).json` | GGUF SDXL skin smoothing preset for polished portraits. | ACE, FLUX, GGUF, SDXL | no |
| `Pulid Instantid SDXL Sticker/sdxl-pulid-sticker-final-single.ai.json` | Pulid InstantID sticker builder that feeds SDXL for bold decal exports. | ACE, INSTANTID, PULID, SDXL | no |
| `SDXL/sdxl-turbo-face-swap.json` | SDXL Turbo face swap rig for rapid identity transfers within portraits. | ACE, SDXL | no |
| `flux-shou-xin-sketch-style-pulid/flux-shou-xin-sketch-style-pulid.json` | Sketch-to-style Pulid workflow combining Flux control with SDXL finishing touches. | ACE, FLORENCE, FLUX, PULID, SDXL | no |

## Image Generation & Editing (Flux/Ace++)

Flux, Ace++, Pulid, and related stacks for portrait creation, swaps, and general image refinement.

| Workflow | Summary | Models | NSFW |
| --- | --- | --- | --- |
| `Ace plus plus/ace++ reference with target.json` | Ace++ reference-to-target alignment kit for capturing identity embeddings before swaps. | ACE, FLUX | no |
| `FP8/3.1_FaceGen_V2_FP8.json` | FP8 face generator mixing Ace++ reference control for detailed portrait synthesis. | ACE, FLUX, FP8 | no |
| `FP8/3.4_Ace++ Face Swap (FP8).json` | Ace++ face swap routine tuned for FP8 checkpoints to transfer identities cleanly. | ACE, FLUX, FP8 | no |
| `FP8/4.2_Single_Image_Generator_Finetune.json` | Finetuned FP8 single-image generator that bootstraps new looks from text prompts. | ACE, FLUX, FP8 | no |
| `FP8/5.1_InstaReady_V2_FluxKrea_(JoyCaption2)FP8.json` | Single-shot InstaReady V2 Joy Caption flow framing Flux Krea renders for social media. | ACE, FLORENCE, FLUX, FP8, JOY, KREA, WAN | no |
| `FP8/5.1_InstaReady_V2_FluxKrea_FP8_SimpleLLMCaption.json` | Single-shot Flux Krea workflow with lightweight LLM captioning baked in. | ACE, FLUX, FP8, KREA, WAN | no |
| `FP8/5.2_Instagram Ready Workflow Florence 2 (Single Image FP8).json` | Single-image Insta-ready variant using Florence 2 for descriptive tagging. | ACE, FLORENCE, FLUX, FP8 | no |
| `FP8/5.2_Instagram Ready Workflow Joy Caption 2 (Single Image FP8).json` | Single-image Joy Caption 2 pipeline layering captions over Flux shots. | ACE, FLORENCE, FLUX, FP8, JOY | no |
| `FP8/5.2_Instagram Ready Workflow Simple LLM Caption (Single Image FP8).json` | Single-image Insta workflow using simple LLM captions on Flux renders. | ACE, FLUX, FP8 | no |
| `FP8/5.4_Flux Skin Enhancer V2 (SD1.5).json` | Flux skin enhancer V2 running on SD1.5 for gentle complexion cleanup. | ACE, FLUX, FP8 | no |
| `FP8/8.1_PixelaiLabs_NSFW_V1_FP8.json` | FP8 PixelaiLabs NSFW preset for mature-themed portrait generation. | ACE, FLUX, FP8 | yes |
| `FP8/Archived Lessons/1 - Face Gen (FP8).json` | Archived lesson demonstrating the baseline FP8 face generation setup. | ACE, FLUX, FP8 | no |
| `FP8/Archived Lessons/1 - FaceGen Upscaler (FP8).json` | Archived FP8 face generator paired with upscaling for sharper portraits. | ACE, FLUX, FP8 | no |
| `FP8/Archived Lessons/2 - Inpainting (FP8).json` | Archived FP8 inpainting lesson for targeted region edits. | FLUX, FP8 | no |
| `Flux Fill FLux Redux Swap Clothes/swap clothes workflow.json` | Flux Redux clothing swap that repaints outfits on a supplied subject. | FLUX | no |
| `Flux Kontext/flux kontext dev with upscaler and face detailer.json` | Flux Kontext dev build combining face detailing and upscaling in one graph. | ACE, FLUX, GGUF | no |
| `Flux Kontext/flux kontext pro, max.json` | Flux Kontext pro configuration with max-quality refinement stages. | ACE, FLUX, GGUF | no |
| `GGUF/3.1_PixelaiLabs_FaceGen_V2_GGUF.json` | GGUF PixelaiLabs FaceGen V2 for identity-consistent portrait synthesis. | ACE, FLUX, GGUF | no |
| `GGUF/3.4_Ace++ Face Swap (GGUF).json` | GGUF Ace++ face swap pipeline for local quantized checkpoints. | ACE, FLUX, GGUF | no |
| `GGUF/4.2_Single_Image_Generator_Finetune.json` | GGUF finetuned single-image generator for bespoke looks. | ACE, FLUX, GGUF | no |
| `GGUF/5.1_InstaReady_V2_FluxKrea_JoyCaption(GGUF).json` | GGUF InstaReady Joy Caption single-shot setup for social-ready exports. | ACE, FLORENCE, FLUX, GGUF, JOY, KREA, WAN | no |
| `GGUF/5.1_InstaReady_V2_FluxKrea_SimpleLLMCaption(GGUF).json` | GGUF InstaReady variant with lightweight LLM captioning for quick posts. | ACE, FLUX, GGUF, KREA, WAN | no |
| `GGUF/5.2_ Instagram Ready Workflow Joy Caption 2 (Single Image GGUF).json` | GGUF single-image Joy Caption 2 workflow for captioned portraits. | ACE, FLORENCE, FLUX, GGUF, JOY | no |
| `GGUF/5.2_Instagram Ready Workflow Florence 2(Single Image GGUF).json` | GGUF single-image Florence 2 pipeline layering descriptive tags. | ACE, FLORENCE, FLUX, GGUF | no |
| `GGUF/5.2_Instagram Ready Workflow Simple LLM Caption (Single Image GGUF).json` | GGUF single-image Insta-ready run using simple LLM captions. | ACE, FLUX, GGUF | no |
| `GGUF/5.4_Flux Skin Enhancer V2 (SD1.5).json` | GGUF SD1.5-based skin enhancer for smoothing complexion. | ACE, FLUX, GGUF | no |
| `GGUF/8.1_PixelaiLabs_NSFW_V1_GGUF.json` | GGUF PixelaiLabs NSFW preset targeting adult-oriented imagery. | ACE, FLUX, GGUF | yes |
| `GGUF/Archived Lessons/1 - Face Gen (GGUF).json` | Archived GGUF lesson covering the base face generation stack. | ACE, FLUX, GGUF | no |
| `GGUF/Archived Lessons/1 - FaceGen Upscaler (GGUF).json` | Archived GGUF face generator plus upscaler combo for clean detail. | ACE, FLUX, GGUF | no |
| `GGUF/Archived Lessons/11 - PixelaiLabs_NSFW_Kontext_V2_GGUF.json` | Archived GGUF Kontext V2 NSFW workflow maintained for reference. | ACE, FLORENCE, FLUX, GGUF, JOY | yes |
| `GGUF/Archived Lessons/2 - Inpainting (GGUF).json` | Archived GGUF inpainting lesson focused on localized edits. | FLUX, GGUF | no |
| `GGUF/Archived Lessons/4 - Kontext Face_Swapper_V2 (GGUF).json` | Archived GGUF Kontext face swapper V2 for dependable identity transfers. | ACE, FLUX, GGUF | no |
| `ghibli/ghibli-flux-diffusion.json` | Ghibli-styled Flux diffusion setup mixing Pulid guidance for painterly looks. | ACE, FLORENCE, FLUX, GHIBLI, PULID | no |
| `ghibli/ghibli-gpt-lora.json` | Ghibli GPT LoRA workflow combining FlowEdit controls for stylized transfers. | FLUX, GGUF, GHIBLI | no |
| `hyperlora/hyperlora - instantid + controlnet + facedetailer.json` | HyperLoRA stack with InstantID, ControlNet, and face detailer for guided portraits. | ACE, HYPERLORA, INSTANTID | no |
| `pulid face swap/flux face swap individual faces.json` | Pulid-enabled Flux face swap for handling multiple individual identities. | ACE, FLUX, GGUF, PULID | no |

## Text-to-Image & Bulk Renders

Direct text-to-image generators and batch render utilities.

| Workflow | Summary | Models | NSFW |
| --- | --- | --- | --- |
| `Bulk Generate Flux Dev/workflow/flux-dev bulk with prompt file.json` | Flux Dev bulk renderer that reads prompt lists and outputs batched image sets. | FLUX | no |

## Dataset & Finetuning

Pipelines that prepare datasets, captions, and training loops for custom model tuning.

| Workflow | Summary | Models | NSFW |
| --- | --- | --- | --- |
| `FP8/3.2_Dataset_Generation_NanoBanana.json` | NanoBanana dataset generator that batches Wan renders with caption helpers for finetuning. | FP8, NANO, WAN | no |
| `FP8/3.3_Data_Preparation_Workflow.json` | FP8 data prep pipeline that cleans and structures image sets for training. | FP8 | no |
| `FP8/4.2_Data_Prep_Finetune_Workflow.json` | End-to-end FP8 finetune prep combining captioning, tagging, and packaging routines. | FP8 | no |
| `FP8/7.5_Wan22_Image_Gen_FP8.json` | Wan 2.2 FP8 image sweep that creates raw datasets for downstream video finetunes. | FP8, HUNYUAN, WAN | no |
| `FP8/7.5_Wan22_Image_Gen_FP8_Joy_Caption.json` | Wan 2.2 FP8 dataset builder enriched with Joy Caption metadata. | FLORENCE, FP8, HUNYUAN, JOY, WAN | no |
| `FP8/7.5_Wan22_Image_Gen_FP8_SimpleLLMCaption.json` | Wan 2.2 FP8 dataset builder using lightweight LLM captions. | FP8, HUNYUAN, WAN | no |
| `FP8/Archived Lessons/3 - Dataset Prep.json` | Archived FP8 lesson documenting dataset preparation fundamentals. | FP8 | no |
| `FP8/Archived Lessons/3.3_Dataset_Prep_Joy_Caption.json` | Archived FP8 Joy Caption walkthrough for dataset tagging. | FP8, JOY | no |
| `FP8/Archived Lessons/4.2_Data_Prep_Finetune_Workflow.json` | Archived FP8 finetune prep flow kept as a reference. | ACE, FP8, JOY | no |
| `FP8/Archived Lessons/5 - Lora XY Plot (FP8) Updated.json` | Archived FP8 LoRA XY plot tool for evaluating finetune sweeps. | FLUX, FP8, GGUF | no |
| `Flux Ultrea Realistic Workflow/ultrareal-finetune workflow (runpod).json` | Ultrareal Flux finetune workflow tailored for RunPod deployments. | FLUX, GGUF | no |
| `GGUF/3.2_PixelaiLabs_Dataset_Generation_NanoBanana.json` | GGUF NanoBanana dataset generator for quantized Wan runs. | GGUF, NANO, WAN | no |
| `GGUF/3.3_Data_Preparation_Workflow.json` | GGUF data preparation stack cleaning assets ahead of training. | GGUF | no |
| `GGUF/4.2_Data_Prep_Finetune_Workflow.json` | GGUF finetune prep template orchestrating tagging and packaging. | GGUF | no |
| `GGUF/7.5_Wan22_Image_Gen_GGUF.json` | Wan 2.2 GGUF dataset generator producing stills for video finetune. | GGUF, HUNYUAN, WAN | no |
| `GGUF/7.5_Wan22_Image_Gen_GGUF_Joy_Caption.json` | Wan 2.2 GGUF dataset generator with Joy Caption annotation. | FLORENCE, GGUF, HUNYUAN, JOY, WAN | no |
| `GGUF/7.5_Wan22_Image_Gen_GGUF_SimpleLLMCAption.json` | Wan 2.2 GGUF dataset generator using lightweight LLM captions. | GGUF, HUNYUAN, WAN | no |
| `GGUF/Archived Lessons/3 - Dataset Prep.json` | Archived GGUF dataset prep primer retained for study. | GGUF | no |
| `GGUF/Archived Lessons/3.3_PixelaiLabs_Dataset_Prep_Joy_Caption.json` | Archived GGUF Joy Caption dataset prep walkthrough. | GGUF, JOY | no |
| `GGUF/Archived Lessons/4.2_Data_Prep_Finetune_Workflow.json` | Archived GGUF finetuning prep pipeline for reference. | ACE, GGUF, JOY | no |
| `GGUF/Archived Lessons/5 - Lora XY Plot (GGUF) Updated.json` | Archived GGUF LoRA XY plot utility for comparing checkpoint sweeps. | FLUX, GGUF | no |
| `HunyuanVideo/hunyuan video lora.json` | Hunyuan LoRA authoring graph that precomputes latents and scheduling for video finetunes. | FLUX, HUNYUAN | no |
| `Wan 2.2 Instagirl/wan2.2-instagirl (1).json` | Wan 2.2 Instagirl preset for generating consistent fashion datasets. | GGUF, HUNYUAN, WAN | no |

## Audio & Speech

Text-to-speech utilities and supporting audio generators.

| Workflow | Summary | Models | NSFW |
| --- | --- | --- | --- |
| `ft-tts/ft-tts-comfy.json` | FastTrack TTS graph generating narration-ready audio from text prompts. | TTS | no |
