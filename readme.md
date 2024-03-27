# Docker Action

This composite action takes in the required inputs from your workflow, builds a docker image, pushes the image to your docker hub repository, 

## Required Inputs

- **DockerHub-username:** description: 'Docker Hub username' required: true
- **DockerHub-token:** description: 'Docker Hub password' required: true
- **dockerfile-path:** description: 'Path to Dockerfile' required: true
- **image-name:** description: 'Container Image Name' required: true
- **image-tag:** description: 'Container Image Tag' required: true

## Usage

```yml
 steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Build and push to docker hub
      uses: Makinates/eddy-gh-action@main
      with:
        docker-hub-username: ${{ secrets.DOCKERHUB_USERNAME }}
        docker-hub-password: ${{ secrets.DOCKERHUB_TOKEN }}
        dockerfile-path: ./path/to/Dockerfile
        image-name: ${{ env.image-name }}
        image-tag: ${{ github.sha }}
    

```