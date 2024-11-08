# Patches For Some React Native Packages Using patch-package

# I. Installation

### 1. Install using npm:
```bash
npm install --save-dev patch-package postinstall-postinstall
```

### 2. Install using yarn:
```bash
yarn add --dev patch-package postinstall-postinstall
```

# II. Usage

### 1. Download patches
Our patches are located in /packages folder. Just download what patch you need and move it to your patches folder.

### 2. Patch a package using patch-package
Run this command to apply a patch
```bash
npx patch-package <package-name>
```

For example
```bash
npx patch-package react-native-walkthrough-tooltip
```
Remember to add below script to your scripts in packages.json for applying your patches automatically after you install packages.
```bash
"postinstall": "npx patch-package"
```

### More details
You can visit below site for more information:

```bash
https://www.npmjs.com/package/patch-package
```
# III. Some Patches For React Native Packages
### 1. react-native-walkthrough-tooltip
Package:
```bash
react-native-walkthrough-tooltip
```

Error:
```bash
TypeError: _reactNative.Dimensions.removeEventListener is not a function. (In '_reactNative.Dimensions.removeEventListener('change', this.updateWindowDims)', '_reactNative.Dimensions.removeEventListener' is undefined)
```

Patch:
```bash
/patches/react-native-walkthrough-tooltip+1.1.7.patch
```

### 2. react-native-snap-carousel
Package:
```bash
react-native-snap-carousel
```

Error:
```bash
 undefined is not an object (evaluating '_reactNative.View.propTypes.style')
```
Patch:
```bash
/packages/react-native-snap-carousel+3.9.1.patch
```