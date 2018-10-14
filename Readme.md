gltf animation loader for assimp  
# interface  
Use aibone,aiAnimation.  
The animation stored in gltf is like this:  
Item: NodeName.(rotation | scale | position) keys values
And I covert them into aiAnimation(and channel,which is like):  
Item: NodeName rotationKeys ScalingKeys PositionKeys  
So a channel does not always contain the same amount of rotationKeys,scalingKeys and positionKeys.
Besides,the node an animation is targeting can be a dummy one.So the node's properties:translate,scale,rotate should be used during animation and rendering.  
And now I only consider one scene with one skeleton.If there exists more than one skeleton,only the 1st one will be loaded.
There can be some problems with aiBone's vertexWeight,as I am not sure whether I loaded the vertex bind buffer right.