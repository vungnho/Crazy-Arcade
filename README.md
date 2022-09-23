# Crazy-Arcade with SDL2

<h2>Screenshot</h2>

![alt text](https://i.imgur.com/F5fi84r.jpg)

![alt text](http://i.imgur.com/6nKz7ki.png)

<h2>Instruction</h2>
<p>1. Be sure you installed SDL2-SDL2_image-SDL2-mixer-SDL2-ttf</p>
<p>2. Run CrazyArcade.cbp from root source folder</p>
<p>3. Build the project and enjoy it</p>


Setup build (x64):
Property Pages -> Configuaration Properties -> C/C++ -> General -> Additional Include Directories:
$(ProjectDir)include\SDL2_image-2.6.2\include;$(ProjectDir)include\SDL2_mixer-2.6.2\include;$(
ProjectDir)include\SDL2_ttf-2.20.1\include;$(ProjectDir)include\SDL2-2.24.0\include;$(ProjectDir)
include\;%(AdditionalIncludeDirectories)

Property Pages -> Configuaration Properties -> Linker -> General -> Additional Library Directories:
$(ProjectDir)include\SDL2_image-2.6.2\lib\x64;$(ProjectDir)include\SDL2_mixer-2.6.2\lib\x64;$(
ProjectDir)include\SDL2_ttf-2.20.1\lib\x64;$(ProjectDir)include\SDL2-2.24.0\lib\x64

Property Pages -> Configuaration Properties -> Linker -> Input -> Additional Dependencies:
SDL2.lib;SDL2_ttf.lib;SDL2_mixer.lib;SDL2_image.lib;%(AdditionalDependencies)

Property Pages -> Configuaration Properties -> Build Events -> Post-Build Events -> Command Line:
xcopy /y /d "$(ProjectDir)include\SDL2-2.24.0\lib\x64\SDL2.dll" "$(OutDir)"
xcopy /y /d "$(ProjectDir)include\SDL2_ttf-2.20.1\lib\x64\SDL2_ttf.dll" "$(OutDir)"
xcopy /y /d "$(ProjectDir)include\SDL2_mixer-2.6.2\lib\x64\SDL2_mixer.dll" "$(OutDir)"
xcopy /y /d "$(ProjectDir)include\SDL2_image-2.6.2\lib\x64\SDL2_image.dll" "$(OutDir)"