
aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin account-id.dkr.ecr.ap-south-1.amazonaws.com

docker buildx create --use

docker buildx build --platform linux/amd64,linux/arm64 -t account-id.dkr.ecr.ap-south-1.amazonaws.com/curefit/stage/cult-gpt:open-web-ui-base-image-0.5.20 --push .

docker buildx build --platform linux/amd64,linux/arm64 -t account-id.dkr.ecr.ap-south-1.amazonaws.com/curefit/prod/cult-gpt:open-web-ui-base-image-0.5.20 --push .