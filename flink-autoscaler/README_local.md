+## Building image locally

```dockerfile
aws ecr-public get-login-password --region us-east-1 --profile brown | docker login --username AWS --password-stdin public.ecr.aws

docker buildx build \
    --platform linux/amd64 \
    --build-arg FLINK_VERSION=1.17.2 \
    -t public.ecr.aws/m5r4d3y5/flink-kubernetes-operator:testing-mar4-v1 \
    .  && docker push public.ecr.aws/m5r4d3y5/flink-kubernetes-operator:testing-mar4-v1
```