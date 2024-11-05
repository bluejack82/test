# Use a base image with Java
FROM mcr.microsoft.com/devcontainers/java:0-17

# Install Android SDK and required build tools
RUN mkdir -p /usr/local/android-sdk-linux
RUN curl -o sdk-tools.zip https://dl.google.com/android/repository/commandlinetools-linux-8092744_latest.zip
RUN unzip sdk-tools.zip -d /usr/local/android-sdk-linux/cmdline-tools
RUN rm sdk-tools.zip

# Set up environment variables
ENV ANDROID_SDK_ROOT /usr/local/android-sdk-linux
ENV PATH $PATH:/usr/local/android-sdk-linux/cmdline-tools/tools/bin
ENV PATH $PATH:/usr/local/android-sdk-linux/platform-tools

# Install required packages
RUN yes | sdkmanager --licenses
RUN sdkmanager "platform-tools" "platforms;android-30" "build-tools;30.0.3"
