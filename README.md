Every compositor is familiar with the ParticleEmitter node, you can attach any geometry to it and make it the source of your particles. You can emit from points, edges, faces, or the bounding box. But did you know that you can also emit particles from just the alpha channel?
All we need to do is to convert the alpha from a 2D image into a 3D point cloud. But how do we achieve that?

We can use an STMap to set the X and Y coordinates and then manually set the Z value to 0. Now you have a custom position pass for your 2D image. Just add a PositionToPoints node, connect your alpha and the custom P pass we created, and now you have a point cloud representing your alpha channel in 3D space.

To transform your point cloud, simply add a TransformGeo node, and that’s it! You can experiment with this technique to create a variety of cool effects. 

If you want to skip all those steps, I’ve created this simple Gizmo that does it all for you.
