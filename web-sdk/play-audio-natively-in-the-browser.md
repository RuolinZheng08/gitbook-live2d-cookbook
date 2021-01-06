# Play Audio Natively in the Browser

```javascript
/**
 * @param group : motion group name
 * @param no : index number inside the motion group
 */
// Play sound
const motionSoundFileName = this._modelSetting.getMotionSoundFileName(group, no);
const sound = new Audio(`${this._modelHomeDir}/${motionSoundFileName}`);
let promise = sound.play();
if (promise) {
  // Older browsers may not return a promise, according to the MDN website
  promise.catch(function (error) { console.error(error); });
}
```



