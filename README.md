# fangker/.github

公共 GitHub 资源仓,跨仓共享 reusable workflows。

## Reusable Workflows

- `.github/workflows/reusable-pages-deploy.yml`:Cloudflare Pages 部署复用工作流。

  调用方式示例:

  ```yaml
  jobs:
    deploy:
      uses: fangker/.github/.github/workflows/reusable-pages-deploy.yml@v1
      with:
        project_name: returnfast-admin-dev
        environment: dev
        pnpm_version: "11"
        node_version: "22.18"
        dist_path: apps/web-antd/dist
      secrets: inherit
  ```

  调用仓库需配置:
  - Repository Secrets:`CLOUDFLARE_API_TOKEN`、`CLOUDFLARE_ACCOUNT_ID`
  - 同名 GitHub Environment(`dev` 或 `prod`),内含 Variables `VITE_API_BASE` 与 `VITE_APP_TITLE`

## 版本

- `v1`: 初始 release。