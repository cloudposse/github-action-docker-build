<!-- markdownlint-disable -->

## Inputs

| Name | Description | Default | Required |
|------|-------------|---------|----------|
| allow | List of extra privileged entitlement (e.g., network.host,security.insecure) | N/A | false |
| binfmt-image | Binfmt image | public.ecr.aws/eks-distro-build-tooling/binfmt-misc:qemu-v7.0.0 | false |
| build-args | List of build-time variables | N/A | false |
| build-contexts | List of additional build contexts (e.g., name=path) | N/A | false |
| buildkitd-flags | BuildKit daemon flags | --allow-insecure-entitlement security.insecure --allow-insecure-entitlement network.host | false |
| cache-from | List of external cache sources for buildx (e.g., user/app:cache, type=local,src=path/to/dir) | type=gha | false |
| cache-to | List of cache export destinations for buildx (e.g., user/app:cache, type=local,dest=path/to/dir) | type=gha,mode=max | false |
| debug | Enable debug mode | false | false |
| docker-metadata-pr-head-sha | Set to `true` to tag images with the PR HEAD SHA instead of the merge commit SHA within pull requests. | false | false |
| driver-opts | List of additional driver-specific options. (eg. image=moby/buildkit:master) | image=public.ecr.aws/vend/moby/buildkit:buildx-stable-1 | false |
| file | Dockerfile name | Dockerfile | false |
| image\_name | Image name (excluding registry). Defaults to {{$organization/$repository}}. |  | false |
| login | Docker login |  | false |
| network | Set the networking mode for the RUN instructions during build | N/A | false |
| no-cache | Send the --no-cache flag to the docker build process | false | false |
| organization | Organization | N/A | true |
| password | Docker password |  | false |
| platforms | List of target platforms for build (e.g. linux/amd64,linux/arm64,linux/riscv64,linux/ppc64le,linux/s390x,etc) | linux/amd64 | false |
| provenance | Generate provenance attestation for the build | N/A | false |
| registry | Docker registry | N/A | true |
| repository | Repository | N/A | true |
| secret-files | List of secret files to expose to the build (e.g., key=filename, MY\_SECRET=./secret.txt) | N/A | false |
| secrets | List of secrets to expose to the build (e.g., key=string, GIT\_AUTH\_TOKEN=mytoken) | N/A | false |
| ssh | List of SSH agent socket or keys to expose to the build | N/A | false |
| tags | List of tags (supports https://github.com/docker/metadata-action#tags-input) | N/A | false |
| target | Sets the target stage to build |  | false |
| workdir | Working directory | ./ | false |


## Outputs

| Name | Description |
|------|-------------|
| image | Docker image name |
| metadata | Docker image metadata |
| tag | Docker image tag |
<!-- markdownlint-restore -->
