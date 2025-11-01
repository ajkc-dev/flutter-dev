---
description: >-
  Installing Flutter on an Ubuntu instance within Google Compute Engine involves
  several steps to set up the environment.
---

# Flutter on GCE

1\. Create a Google Compute Engine Instance:

* Navigate to the Google Cloud Console.
* Create a new Compute Engine VM instance, selecting Ubuntu as the operating system.
* Ensure the instance has sufficient resources (CPU, RAM) for development.

2\. Connect to the Instance:

* Use SSH to connect to your newly created Ubuntu instance. You can do this directly from the Google Cloud Console or using a local SSH client.

3\. Install Prerequisites:

* Update your package lists and upgrade existing packages:

Code

```
  sudo apt-get update -y && sudo apt-get upgrade -y
```

Install necessary tools for Flutter.

```
  sudo apt-get install -y curl git unzip xz-utils zip libglu1-mesa
```

4\. Download and Extract the Flutter SDK:

* Download the Flutter SDK from the official Flutter website. Use `curl` to download the latest stable release:

Code

```
  curl -O https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_3.22.0-stable.tar.xz # Replace with the latest stable version if different
```

Extract the downloaded archive.

```
  tar xf flutter_linux_3.22.0-stable.tar.xz # Replace with the correct filename
```

* Move the extracted `flutter` directory to a suitable location, such as your home directory:

Code

```
  mv flutter ~/
```

5\. Add Flutter to your PATH:

* Open your shell's configuration file (e.g., `~/.bashrc` or `~/.zshrc`):

Code

```
  nano ~/.bashrc
```

* Add the following line to the end of the file, replacing `~/flutter` with the actual path to your Flutter SDK:

Code

```
  export PATH="$PATH:~/flutter/bin"
```

* Save the file and apply the changes:

Code

```
  source ~/.bashrc
```

6\. Verify Flutter Installation:

* Run `flutter doctor` to check for any missing dependencies or configuration issues:

Code

```
  flutter doctor
```

* Address any reported issues by installing the recommended tools or packages.

7\. (Optional) Install an IDE/Editor:

* For a better development experience, consider installing an IDE like VS Code or Android Studio on your GCE instance. This might require additional setup for GUI environments or remote development tools.
