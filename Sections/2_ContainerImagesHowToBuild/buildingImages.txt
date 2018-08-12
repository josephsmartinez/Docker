Building Docker Files

  By default Docker file are named 'Dockerfile'

  Using another file format
  # docker build -f [DockerFile]

  All images used are official images. This means that they're
  going to be up to date with the latest security patches.

  Images are light and thus may not have common software installed by
  default like you find on full image VMs. However, they all have
  package manager like: apt and yum.

Environment Variables
  One reason they were chosen as preferred way to inject key/value
  is they work everywhere, on every OD and config.

Building Images - Running Docker Builds

  Building an Image
  # docker image build -t [custom image name] .

  NOTE: The period after the common which specifies to build
  the image within the current directory.

Caching Change and Re-Building

    Docker will cache builds and only re-build what has been
    edited with the Dockerfile. The step and order is VERY important
    when building images.

    NOTE: Code development should not be at the top the file as
    building the image will cause a re-build of the entire image.
