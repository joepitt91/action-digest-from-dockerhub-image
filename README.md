<!--
SPDX-FileCopyrightText: 2025 Joe Pitt

SPDX-License-Identifier: GPL-3.0-only
-->
# GitHub Action - Get Current Digest from Tagged DockerHub Image

Get the current digest of the given image tag on DockerHub.

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| dockerhub_username | The user to authenticate to the Docker Hub API as. | Yes |  |
| dockerhub_token | The token to authenticate to the Docker Hub API with (must have read access). | Yes |  |
| namespace | The namespace the repository is in. | No | library |
| repository | The repository to search tags for. | Yes |  |
| tag | The tag to look for.| No | latest |
| os | The OS platform to look for. | No | linux |
| arch | The architecture platform to look for. | No | amd64 |

## Outputs

| Output | Description | Example |
|--------|-------------|---------|
| digest | The digest of the current image matching the search. | sha256:97983fa8cc88343512862c62307159a82261c3528dc025f79e5a3f7af43e50b4 |

## Example

```yaml
      - name: Get Current Digest for Latest Nextcloud AIO
        id: version
        uses: joepitt91/action-digest-from-dockerhub-image@v1
        with:
          dockerhub_username: ${{ secrets.DOCKERHUB_USERNAME }}
          dockerhub_token: ${{ secrets.DOCKERHUB_TOKEN }}
          repository: nextcloud
```
