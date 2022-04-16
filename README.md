# BestPermissionUtil

You can read the story from here https://hamurcuabi.medium.com/permissions-with-the-easiest-way-9c466ab1b2c1


## Prerequisites

Add this in your root `build.gradle` file (**not** your module `build.gradle` file):

```gradle
allprojects {
	repositories {
		...
		maven { url "https://jitpack.io" }
	}
}
```

## Dependency

Add this to your module's `build.gradle` file (make sure the version matches the JitPack badge above):

```gradle
dependencies {
	...
	 implementation 'com.github.hamurcuabi:BestPermissionUtil:1.0.2'
}
```

## Usage

    private val cameraPermission = registerPermission {
        onCameraPermissionResult(it)
    }

    private val storagePermission = registerPermission {
        onStoragePermissionResult(it)
    }
    
     private fun onStoragePermissionResult(state: PermissionUtil.PermissionState) {
        when (state) {
            Denied -> {
                TODO()
            }
            Granted -> {
                TODO()
            }
            PermanentlyDenied -> {
                TODO()
            }
        }
    }

    private fun onCameraPermissionResult(state: PermissionUtil.PermissionState) {
        when (state) {
            Denied -> {
                TODO()
            }
            Granted -> {
                TODO()
            }
            PermanentlyDenied -> {
                TODO()
            }
        }
    }
    
     cameraPermission.launchSinglePermission(android.Manifest.permission.CAMERA)

        storagePermission.launchMultiplePermission(
            arrayOf(
                android.Manifest.permission.WRITE_EXTERNAL_STORAGE,
                android.Manifest.permission.READ_EXTERNAL_STORAGE
            )
        )
