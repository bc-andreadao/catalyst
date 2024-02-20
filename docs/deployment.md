## Deploying a Catalyst storefront

> [!IMPORTANT]
> The following guides assume you have created a Catalyst storefront using the CLI or another entry point that results in your code directory containing only a single Next.js application, and not the monorepo present in the [Catalyst GitHub repository](https://github.com/bigcommerce/catalyst). These instructions may need to be modified for development on top of the monorepo. See [Monorepo](#monorepo) for more information.

### Deploying to Vercel from vercel.com
Your Catalyst storefront can be deployed to Vercel easily with just a source control repository and a few environment variables.

To deploy to Vercel using vercel.com, log into your Vercel account and select `Add New... > Project` from the top right of the Overview page.

Once here, point Vercel to a GitHub, GitLab, or Bitbucket source repository containing your Catalyst storefront's code and populate the required [Environment Variables](#environment-variables) to get started. In addition to the required variables, you should also populate `TURBO_REMOTE_CACHE_SIGNATURE_KEY` to have optimal build performance on Vercel.

Once the environment variables are correctly populated, just click "deploy".

To learn more about deploying to Vercel, consult the [Vercel documentation](https://vercel.com/docs/deployments/overview).


### Deploying to Vercel using the Vercel CLI

To deploy using the [Vercel CLI](https://vercel.com/docs/cli), navigate to a directory containing a Catalyst codebase and run `npm i` or `pnpm i` as appropriate to ensure all dependencies are up-to-date.

Ensure the required [Environment Variables](#environment-variables) are populated in `.env.local` and the storefront functions correctly with `npm run dev` or `pnpm run dev`.

If everything looks good, just run `vercel` to create a Preview Deployment or `vercel` --prod` to create a Production Deployment. If this is your first time using the Vercel CLI from this project, you will need to answer a few prompts to connect an existing Vercel project or create a new one.

If you are creating a new Vercel project through this flow, your first build will fail due to the lack of environment variables in your Vercel project. You can add those variables one at a time using [`vercel env add`](https://vercel.com/docs/cli/env), or log into vercel.com and paste the contents of your `.env.local` into the environment variables settings on your project.

For more information on the Vercel CLI, consult the [Vercel CLI Documentation](https://vercel.com/docs/cli).