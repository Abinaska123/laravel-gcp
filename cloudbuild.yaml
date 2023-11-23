steps:
  # Build the container image
  - name: 'gcr.io/cloud-builders/docker'
    # Specify the name of the image
    args: ['build', '-t', 'gcr.io/abinas-test-server/laravelapp:latest6', '.']
  
  # Push the container image to Container Registry
  - name: 'gcr.io/cloud-builders/docker'
    args: ['push', 'gcr.io/abinas-test-server/laravelapp:latest6']
  
  # Deploy container image to Cloud Run
  - name: 'gcr.io/google.com/cloudsdktool/cloud-sdk'
    entrypoint: 'gcloud'
    # Specify the service name, region, and other deployment options
    args: ['run', 'deploy', 'laravel', '--image', 'gcr.io/abinas-test-server/laravelapp:latest6', '--region', 'us-central1',         
           "--platform", "managed",
           "--port", "8000"]
    
images:
  - 'gcr.io/abinas-test-server/laravelapp:latest6'


