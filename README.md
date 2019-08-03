# cpp-sdl-side-scrolling


## AnimSpriteComponent
```
void AnimSpriteComponent::Update(float deltaTime)
{
   SpriteComponent::Update(deltaTime);
   if (mAnimTextures.size() > 0)
   {
      // Update the current frame based on frame rate
      // and delta time
      mCurrFrame += mAnimFPS * deltaTime;
     
      // Wrap current frame if needed
      while (mCurrFrame >= mAnimTextures.size())
      {
         mCurrFrame -= mAnimTextures.size();
      }
      // Set the current texture
      SetTexture(mAnimTextures[static_cast<int>(mCurrFrame)]);
   }
}
```

## Scrolling Backgrounds
The background is a generic Actor (not a subclass) that has two BGSpriteComponents. The different scroll speeds of these two backgrounds create a parallax effect. 

```
```
