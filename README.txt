INFO6028 Graphics Project 3
Evan Sinasac - 1081418

Built and run in Visual Studios Community 2019 in Debug and Release in x64.

CONTROLS
WASD			- Move Camera
QE			- Raise/Lower Camera
Mouse			- Aim Camera
B			- Show Debug Triangles
M			- Show Wireframe
Shift + Arrow Up/Down	- Raise/Lower Blue spotlight
CTRL + Arrow Keys	- Move Blue spotlight

The purpose of Project 3 is to implement 2 enhancements to the previous project.  I decided to go with implementing the Ambient Occlusion map that came with the Dark Fantasy Kit I've been using as well as the texture based imposter effect.  Both were fairly simple to implement so I'm expecting to only receive the easy marks for this project.

The AO map is simple but powerful.  With it, certain parts of objects can become much shinier than others.  In particular, this effect can be seen with the torches and the chair included in the scene.  When drawing a pixel, the fragment shader looks at the AO map and adds the the shininess by multiplying the material colour by the red value at the matching point in the AO map.  More red means more shiny.  Less red means less shiny.  This ambient colour is then added with the material colour and the specular colour before being added to objects final colour.  Figured out the math from (https://learnopengl.com/Advanced-Lighting/SSAO)

The imposter texture effect I implemented is a slight variation to the one we did in class.  Essentially I made the engine thruster effect as an imposter texture, but then in the fragment shader, take the blue value of the texture and use it for the red, essentially turning the flame red instead of blue.  This would essentially allow me to reuse textures and objects in the future but declare some of them imposters and completely change the colour of the object, without having to make a brand new texture and/or model.  One boolean and a few lines in the fragment shader would be much cheaper than another set of textures.

MODELS
The models I used are from Runemark's Dark Fantasy Kit (https://assetstore.unity.com/packages/3d/environments/fantasy/dark-fantasy-kit-123894) and one of the ships from the ship pack we were given in class.

TEXTURES
I am using the textures from Runemark's Dark Fantasy Kit that go with the respective objects I converted, as well as some other textures we were give in class.  In particular for this project is the Long-blue_Jet_Flame.bmp which is being used as part of the imposter texture effect.

VIDEO
https://youtu.be/Yvv4rLfUoQ0