# The-Quantum-Computing-Developmental-Activities.
The Quantum Computing and Artificial Intelligence Development's Code.
Describe the bug A clear and concise description of what the bug is, and which sample or samples you encountered the bug in.
To Reproduce Steps to reproduce the behavior:
1.	Go to '...'
2.	Click on '....'
3.	Scroll down to '....'
4.	See error
Expected behavior A clear and concise description of what you expected to happen.
Screenshots If applicable, add screenshots to help explain your problem.
System information
•	OS: [e.g. iOS]
•	Browser [e.g. chrome, safari]

**VS Code :**

{
	    "recommendations": [
	        "quantum.quantum-devkit-vscode",
	        "ms-dotnettools.csharp",
	        "ms-python.python",
	        "EditorConfig.EditorConfig",
	        "davidanson.vscode-markdownlint"
	    ]
	}



**Build :**

# Start from the IQ# base image. The definition for this image can be found at
	# https://github.com/microsoft/iqsharp/blob/main/images/iqsharp-base/Dockerfile.
	# As per Binder documentation, we choose to use an SHA sum here instead of a
	# tag.
	FROM mcr.microsoft.com/quantum/iqsharp-base:0.23.198514-beta
	

	# Mark that this Dockerfile is used with the samples repository.
	ENV IQSHARP_HOSTING_ENV=SAMPLES_DOCKERFILE
	

	# We need to do a few additional things as root here.
	USER root
	

	# Install additional system packages from apt.
	RUN apt-get -y update && \
	    apt-get -y install \
	               # For the Python interoperability sample, we require QuTiP,
	               # which in turn requires gcc's C++ support.
	               g++ \
	               # The version of Matplotlib we use also needs a couple header
	               # packages.
	               pkg-config \
	               libfreetype6-dev \
	               libpng-dev \
	               # iqsharp-base currently ships with .NET Core SDK 3.1, but
	               # we need .NET 6.0 to run dotnet-interactive.
	               dotnet-sdk-6.0 \
	               # Make sure to use the most up-to-date curl.
	               curl && \
	    # As per https://github.com/NuGet/Announcements/issues/49,
	    # we also need to update the ca-certificates package
	    # to use nuget restore from .NET 5.0.
	    # This requries enabling debian-unstable, so we do so as a
	    # separate command.


**Json**

// This configuration file sets options for spell-checking pull requests
	
	        {
	            "languageId": "qsharp",
	            "filename": "**/*.qs"
	        }
	    ],
	

	    // Define keywords on a per-language basis.
	    "languageSettings": [
	        {
	            "languageId": ["qsharp"],
	            // cspell:disable
	            "ignoreWords": [
	                "newtype"
	            ]
	            // cspell:enable
	        }
	    ]
      
