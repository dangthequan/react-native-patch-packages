# Patches For Some React Native Packages Using patch-package
Apply patches will resolve some issues for some react-native packages.

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
Our patches are located in /patches folder. Just download what patch you need and move it to your patches folder.

```bash
<your-root-project-folder>/patches <-- Copy our patches in /patches folder to this location.
```

### 2. Use our patches
First, copy our patches to your <root-project-folder>/patches folder (Just ignore this step if you have done it)

Second, add below script to scripts in your <root-project-folder>/package.json
```bash
"postinstall": "npx patch-package"
```
Done. Each time you install packages, the patches in <root-project-folder>/patches folder will be patched automatically.

### 3. Or create your own patch by using patch-package
#### 3.1 First, resolve issues by yourself
You must resolve all package's issues directly in node_modules folder by yourself.

#### 3.2 Second, create a patch
Run below command to create a patch:
```bash
npx patch-package <package-name>
```
A corresponding patched file will be created in <root-project-folder>/patches folder.

For example, when you execute below command:
```bash
npx patch-package react-native-walkthrough-tooltip
```

The corresponding patched will be created:
```bash
/packages/react-native-walkthrough-tooltip+1.1.7.patch
```

Also remember to add below script to your scripts in packages.json for applying your patches automatically after you install packages.
```bash
"postinstall": "npx patch-package"
```

*** Tips: The patched file will includes all changes in any files and folders, to avoid including changes in unnecessary files and folders, you can ignore thems by using --exclude param with pattern path look like below:
```bash
npx patch-package <package-name> --exclude 'android/build/|android/app/build/'
```

### More details
You can visit below site for more information:

```bash
https://www.npmjs.com/package/patch-package
```

# III. Some Patches For React Native Packages
### 1. react-native-walkthrough-tooltip

Issue:
```bash
TypeError: _reactNative.Dimensions.removeEventListener is not a function. (In '_reactNative.Dimensions.removeEventListener('change', this.updateWindowDims)', '_reactNative.Dimensions.removeEventListener' is undefined)
```

Patch:
```bash
/patches/react-native-walkthrough-tooltip+1.1.7.patch
```

### 2. react-native-snap-carousel

Issue:
```bash
 undefined is not an object (evaluating '_reactNative.View.propTypes.style')
```
Patch:
```bash
/packages/react-native-snap-carousel+3.9.1.patch
```

### 3. react-native-i18n

Issue:
```bash
A problem occurred evaluating project ':react-native-i18n'. > Could not find method compile() for arguments [com.facebook.react:react-native:+] on object of type org.gradle.api.internal.artifacts.dsl.dependencies.DefaultDependencyHandler
```

Patch:
```bash
/patches/react-native-i18n+2.0.15.patch
```

### 4. react-native-is-device-locked

Issue:
```bash
Could not find method compile() for arguments [com.facebook.react:react-native:0.20.+] on object of type org.gradle.api.internal.artifacts.dsl.dependencies.DefaultDependencyHandler.
```

Patch:
```bash
/patches/react-native-is-device-locked+2.0.5.patch
```

