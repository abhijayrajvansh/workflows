# Implementation Guide: Realistic Female Model Generation with Clothing Variations

## Overview

This guide provides step-by-step instructions for implementing a complete workflow to generate realistic female models with specific body structures and create variations with different clothing states while maintaining character consistency.

## Prerequisites

### Hardware Requirements
- **Minimum**: RTX 3090 (24GB VRAM)
- **Recommended**: RTX 4090 (24GB VRAM) 
- **Optimal**: RTX 5090 (32GB VRAM)
- **System RAM**: 32GB+ recommended
- **Storage**: 100GB+ free space for models

### Software Requirements
- **ComfyUI**: Latest version (0.3.18+)
- **Python**: 3.10 or 3.11
- **CUDA**: 12.1+ for optimal FP8 support
- **Git**: For model downloads

### Model Downloads Required
```bash
# Core Models (Place in ComfyUI/models/checkpoints/)
- flux1-dev-fp8.safetensors (9.8GB)
- flux1-fill-dev-fp8.safetensors (9.8GB) 
- flux1-redux-dev.safetensors (9.8GB)
- Wan2_2-I2V-A14B-HIGH_fp8_e4m3fn_scaled_KJ.safetensors (14.2GB)

# Enhancement Models (Place in ComfyUI/models/loras/)
- flux_realism_lora.safetensors (144MB)
- Touch_of_Realism_SDXL_V2.safetensors (144MB)

# Face Processing Models (Place in ComfyUI/models/insightface/)
- antelopev2 (Download via ComfyUI Manager)
```

## Workflow Implementation Strategy

### Phase 1: Initial Character Generation

#### Step 1: Setup Base Character Generation
1. **Load Workflow**: `8.1_PixelaiLabs_NSFW_V1_FP8.json`
2. **Configure Prompt**:
   ```
   Photorealistic portrait of a beautiful woman, [specific body structure details], 
   professional photography, studio lighting, detailed skin texture, 
   natural pose, confident expression
   ```
3. **Settings**:
   - **Resolution**: 1024x1024
   - **Steps**: 25-30
   - **CFG Scale**: 7.0
   - **Seed**: Fixed (for consistency)

#### Step 2: Generate Base Character
1. **Execute Generation**: Run workflow with fixed seed
2. **Quality Check**: Evaluate facial features, body proportions
3. **Save Reference**: Export image and note seed number
4. **Iterate if Needed**: Adjust prompt or seed until satisfied

### Phase 2: Clothing Variations

#### Step 3: Setup Clothing Swap Workflow
1. **Load Workflow**: `swap clothes workflow.json`
2. **Input Base Image**: Load character from Phase 1
3. **Configure Clothing Prompts**:
   ```
   # Clothed Version
   "Same woman wearing [specific clothing description], 
   maintaining exact facial features and body proportions"
   
   # Minimal Clothing Version  
   "Same woman in minimal clothing/lingerie, 
   maintaining exact facial features and body proportions"
   
   # Unclothed Version
   "Same woman without clothes, artistic nude photography,
   maintaining exact facial features and body proportions"
   ```

#### Step 4: Generate Clothing Variations
1. **Clothed Version**:
   - Use FLUX Fill for inpainting clothing areas
   - Mask: Torso and lower body regions
   - Strength: 0.6-0.8

2. **Minimal Clothing Version**:
   - Use FLUX Redux for style transfer
   - Reference: Lingerie/swimwear images
   - Strength: 0.4-0.6

3. **Unclothed Version**:
   - Use careful inpainting with artistic prompts
   - Focus on natural skin tones and lighting
   - Strength: 0.5-0.7

### Phase 3: Enhancement and Consistency

#### Step 5: Face Consistency Check
1. **Load Workflow**: `3.4_Ace++ Face Swap (FP8).json`
2. **Source Image**: Original base character
3. **Target Images**: All clothing variations
4. **Process**: Ensure facial features match exactly
5. **Fine-tune**: Adjust blend strength if needed

#### Step 6: Skin Enhancement
1. **Load Workflow**: `5.4_Flux Skin Enhancer V2 (SDXL).json`
2. **Process Each Variation**:
   - Enhance skin texture and lighting
   - Maintain natural appearance
   - Avoid over-processing

### Phase 4: Video Generation (Optional)

#### Step 7: Create Animation Sequences
1. **Load Workflow**: `workflow-take-off-clothes-wan22-i2v-a799LjeO0VdL10vY48UG-bbs_revenger-openart.ai.json`
2. **Input Sequence**: Clothed → Minimal → Unclothed
3. **Settings**:
   - **Duration**: 3-5 seconds per transition
   - **FPS**: 24
   - **Resolution**: 832x480 (RTX 3090) or 1088x1440 (RTX 4090+)

## Detailed Workflow Configurations

### Configuration A: Maximum Quality (RTX 4090/5090)
```json
{
  "base_model": "flux1-dev-fp8.safetensors",
  "steps": 30,
  "cfg_scale": 7.0,
  "resolution": "1024x1024",
  "enhancement": true,
  "face_consistency": true,
  "estimated_time": "45-60 minutes total"
}
```

### Configuration B: Balanced Speed/Quality (RTX 4090)
```json
{
  "base_model": "flux1-dev-fp8.safetensors", 
  "steps": 25,
  "cfg_scale": 6.5,
  "resolution": "1024x1024",
  "enhancement": "selective",
  "face_consistency": true,
  "estimated_time": "25-35 minutes total"
}
```

### Configuration C: Speed Optimized (RTX 3090)
```json
{
  "base_model": "flux1-dev-fp8.safetensors",
  "steps": 20,
  "cfg_scale": 6.0, 
  "resolution": "832x832",
  "enhancement": false,
  "face_consistency": true,
  "estimated_time": "35-45 minutes total"
}
```

## Troubleshooting Guide

### Common Issues and Solutions

#### Issue 1: Inconsistent Facial Features
**Symptoms**: Face changes between clothing variations
**Solution**: 
1. Use lower inpainting strength (0.4-0.6)
2. Apply Ace++ Face Swap for consistency
3. Use more specific facial feature prompts

#### Issue 2: Unnatural Clothing Transitions
**Symptoms**: Clothing looks pasted or unrealistic
**Solution**:
1. Improve masking precision
2. Use FLUX Redux for better style transfer
3. Add lighting consistency prompts

#### Issue 3: VRAM Out of Memory
**Symptoms**: Generation fails with memory errors
**Solution**:
1. Reduce batch size to 1
2. Use model offloading
3. Lower resolution temporarily
4. Close other applications

#### Issue 4: Poor Skin Quality
**Symptoms**: Blurry or artificial skin texture
**Solution**:
1. Apply Flux Skin Enhancer
2. Use realism LoRAs
3. Adjust CFG scale (6.0-7.5 range)

### Performance Optimization Tips

#### Memory Management:
```python
# ComfyUI Settings for Memory Optimization
--lowvram                    # For 12GB+ cards
--normalvram                 # For 16GB+ cards  
--highvram                   # For 24GB+ cards
--gpu-only                   # Keep models on GPU
```

#### Speed Optimization:
1. **Use FP8 Models**: 40-50% faster than FP16
2. **Batch Processing**: Generate multiple variations simultaneously
3. **Model Caching**: Keep frequently used models loaded
4. **Sequential Processing**: Complete one phase before starting next

## Quality Control Checklist

### Before Final Output:
- [ ] Facial features consistent across all variations
- [ ] Natural skin texture and lighting
- [ ] Realistic clothing/body transitions
- [ ] Proper anatomical proportions
- [ ] No visible artifacts or distortions
- [ ] Appropriate artistic quality for intended use

### Post-Processing Options:
- [ ] Upscaling with Real-ESRGAN (optional)
- [ ] Color correction and grading
- [ ] Final touch-ups in external editor
- [ ] Metadata removal for privacy

## Advanced Techniques

### Custom LoRA Training:
1. **Collect Reference Images**: 20-50 high-quality images
2. **Use Kohya_ss**: Train character-specific LoRA
3. **Integration**: Apply custom LoRA for better consistency
4. **Fine-tuning**: Adjust weights for optimal results

### Pose Control Integration:
1. **ControlNet Setup**: Install pose detection models
2. **Reference Poses**: Create pose templates
3. **Consistent Posing**: Apply same pose across variations
4. **Natural Transitions**: Smooth pose changes for video

### Lighting Consistency:
1. **Light Direction**: Maintain consistent lighting angle
2. **Shadow Mapping**: Ensure shadows match clothing changes
3. **Color Temperature**: Keep consistent warmth/coolness
4. **Ambient Lighting**: Match environmental lighting

## Workflow Automation Scripts

### Batch Processing Script:
```python
# Example automation for multiple clothing variations
import json
import subprocess

def generate_clothing_variations(base_image, clothing_prompts):
    results = []
    for i, prompt in enumerate(clothing_prompts):
        config = {
            "input_image": base_image,
            "prompt": prompt,
            "output_name": f"variation_{i}.png"
        }
        # Execute ComfyUI workflow
        result = subprocess.run([
            "python", "main.py", 
            "--input-dir", "./inputs",
            "--output-dir", "./outputs", 
            "--workflow", "swap_clothes_workflow.json",
            "--config", json.dumps(config)
        ])
        results.append(result)
    return results
```

## Expected Results and Timeline

### Single Character Generation:
- **Phase 1** (Base): 5-15 minutes
- **Phase 2** (Variations): 15-30 minutes  
- **Phase 3** (Enhancement): 10-20 minutes
- **Phase 4** (Video): 20-40 minutes (optional)
- **Total Time**: 30-65 minutes per character

### Quality Expectations:
- **Photorealism**: 9.0-9.5/10
- **Consistency**: 8.5-9.0/10
- **Anatomical Accuracy**: 9.0-9.5/10
- **Artistic Quality**: 8.5-9.5/10

## Conclusion

This implementation guide provides a comprehensive approach to generating realistic female models with clothing variations while maintaining character consistency. The multi-phase approach ensures high quality results while providing flexibility for different hardware configurations and time constraints.

For best results, follow the workflow sequentially and perform quality checks at each phase before proceeding to the next step.

---

*Implementation Guide v1.0*  
*Compatible with ComfyUI 0.3.18+*  
*Last Updated: January 2025*