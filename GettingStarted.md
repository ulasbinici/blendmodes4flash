# Getting Started with Blend Modes 4 Flash #

## Using the UltimateBlendModeShader SWC with CS4 ##

If you have Flash CS4 installed a SWC can be referenced from your FLA.
Go to File > Publish settings > Flash > Settings
Then choose the tab 'Library path' and click the plus icon and select the UltimateBlendModeShader.swc file.

## Applying custom blend modes with Actionscript to DisplayObjects ##
Once the UltimateBlendModeShader.swc is referenced in your FLA or your Flex Project you may apply custom blend modes in the following manners.

1) Using Static references to custom blend modes
```
import flash.display.BlendModeShader;

myDisplayObject.blendShader = BlendModeShader.SOFTLIGHT;
```

2) Using constructed instances of custom blend modes
```
import flash.display.BlendModeShader;
import flash.display.shaders.*;

myDisplayObject.blendShader = new BlendModeSoftlight();
```

3) Altering custom blend modes via multiplying and undoing
```
import flash.display.BlendModeShader;
import flash.display.shaders.*;

var customBlendMode: BlendModeSoftlight  = new BlendModeSoftlight();
customBlendMode.multiply = 2; //exaggerates the blendmode effect by double
customBlendMode.alpha = 0.5; // reverts the blendmode effect 50% back to the source blending layer

myDisplayObject.blendShader = customBlendMode;
```

## Altering custom blend modes with Actionscript ##
Custom blend modes have 2 parameters which you can tweak to get a desired result. These parameters are alpha and multiply.

### The alpha parameter ###
The alpha parameter undoes the blend shader to the source image where 0 is undone and 1 is the custom blend shader completely applied.

### The multiply parameter ###
The multiply parameter exaggerates the blend shader effect. This can be thought of as similar to a process you may consider doing via applying the same custom blend shader onto duplicates of the same DisplayObject.